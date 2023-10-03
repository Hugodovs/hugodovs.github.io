---
layout: post
title: "Chapter 2: Testing"
date: 2023-10-02 00:00:00
image: /assets/images/blog/crafting_python_environments_with_modern_tools/logo_2.jpg
tags: python poetry pyenv
description: This article is Crafting Python Environments with Modern Tools series! Let's get started with Chapter 2 - Testing!
permalink: /2023/08/28/chapter_1_testing.html
---

<article id="177f3ef8-8a4b-4091-8dda-27eb69933c9f" class="page sans"><header><h1 class="page-title"><strong><strong>Chapter 2: Testing</strong></strong></h1><p class="page-description"></p></header><div class="page-body"><ul id="cf630fc0-5016-4221-ae90-647ef2c73459" class="toggle"><li><details open=""><summary><strong>Getting Started with Pytest</strong></summary><p id="10be8f8b-a7ab-45ce-a310-539e83dedb43" class="">To kickstart your testing journey with <a href="https://docs.pytest.org/en/7.4.x/"><strong>Pytest</strong></a> as a development dependency using Poetry, check the following steps.</p><p id="5659e54b-5099-4451-91fe-74a111cf5771" class="">Add Pytest as a development dependency using Poetry with this command:</p><pre id="ec0452f3-ee0a-4615-908d-32f3c5b83ffa" class="code"><code>poetry add --group dev pytest</code></pre><p id="1d393d5c-efca-4acd-892e-3ea6bc4b7e1a" class="">To keep your project structured and maintainable, organize your test files in a separate directory adjacent to your &#x27;src&#x27; directory. Conventionally, this directory is named &#x27;tests&#x27;. Here&#x27;s what the directory structure should look like:</p><pre id="1b2ead10-4f7b-461c-a66f-72ff4323130d" class="code"><code>.
├── src
└── tests
    ├── __init__.py
    └── test_game.py</code></pre><p id="41ca639e-60dc-48d1-a248-3bf8d235fde8" class="">Within the &#x27;tests&#x27; directory, you can create individual test files. Consider the example of <code>test_game.py</code>, which contains test cases for the <code>game.py</code> module. In this file, we check the game can run properly during 10 frames. We need to make a small adjustment in game.py file:</p><pre id="97071c4e-eef4-4d02-867d-eea2a46884de" class="code"><code># game.py
def post_quit_event():
    pygame.event.post(pygame.event.Event(pygame.QUIT))

def main(total_frames=-1):

    pygame.init()
    display = pygame.display.set_mode((400, 300))

    fps = FPS()

    running = True
    while running:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                running = False

        if not running:
            break

        display.fill((0, 0, 0))

        fps.render(display)

        pygame.display.update()
        fps.clock.tick(60)

        total_frames -= 1
        if total_frames == 0:
            post_quit_event()

    pygame.quit()
    sys.exit()</code></pre><p id="e29e2443-0c92-42eb-b28f-09cb0fa79f8c" class="">Here&#x27;s what <code>test_game.py</code> should look like: </p><pre id="36868296-6d1c-4d7e-990c-363ed346aa8f" class="code"><code># tests/test_game.py
import pytest
from dungeons_and_clicks import game

def test_main_some_frames():
    total_frames = 10
    with pytest.raises(SystemExit):
        game.main(total_frames)</code></pre><p id="a85a9ca0-9608-4d68-a777-d97d21e4c83d" class="">Consider adding this to your <code>pyproject.toml</code> to suppress pygame&#x27;s DeprecationWarnings:</p><pre id="2424fcf9-36dc-4eb9-a2c6-66c0cabd9fad" class="code"><code>[tool.pytest.ini_options]
filterwarnings = &quot;ignore::DeprecationWarning:pygame.pkgdata&quot;</code></pre><p id="720f8dbe-aa12-4a62-8fff-76508000e9a3" class="">Finally, you can execute Poetry and run Pytest to test your code:</p><pre id="416cd0c9-df03-41e6-874b-794fca503034" class="code"><code>poetry run pytest

======================================= test session starts =======================================
platform win32 -- Python 3.10.7, pytest-7.4.2, pluggy-1.3.0
rootdir: C:&lt;dir&gt;\&lt;your-repo-name&gt;
configfile: pyproject.toml
collected 2 items

tests\test_game.py ..                                                                        [100%]

======================================== 2 passed in 1.36s ========================================</code></pre></details></li></ul><ul id="ba2c4ee9-075a-4554-9294-633a8c31aba5" class="toggle"><li><details open=""><summary><strong><strong>Code coverage with Coverage.py</strong></strong></summary><p id="ae431f75-f4c3-4793-86b0-a7ad2778cf2c" class=""><strong>Code coverage</strong> measures the extent to which your program&#x27;s source code is executed when running its test suite. For Python programs, you can determine code coverage using a powerful tool called <strong>Coverage.py</strong>. To seamlessly integrate Coverage.py with <code><strong>pytest</strong></code>, you can install it along with the <code><strong>pytest-cov</strong></code> plugin using the following command:</p><pre id="33972dbe-0fe6-4349-a7ce-2b8c10391889" class="code"><code>poetry add --group dev coverage[toml] pytest-cov</code></pre><p id="1d096923-a3e4-40b9-8c51-aaf365b4bf81" class="">After installing Coverage.py, you need to configure it to work with your project. The <code><strong>pyproject.toml</strong></code> configuration file is where you&#x27;ll specify your package name and the layout of your source tree. Additionally, you can enable branch analysis and instruct Coverage.py to display line numbers for uncovered code. Here&#x27;s an example configuration snippet:</p><pre id="1e98ddec-c48b-49c3-916d-b4b314e6a131" class="code code-wrap"><code>[tool.coverage.paths]
source = [&quot;src&quot;, &quot;*/site-packages&quot;]

[tool.coverage.run]
branch = true
source = [&quot;&lt;your_package_name&gt;&quot;]

[tool.coverage.report]
show_missing = true
fail_under = 80</code></pre><figure class="block-color-gray_background callout" style="white-space:pre-wrap;display:flex" id="82091293-9a06-4cf6-875d-5892c7942976"><div style="font-size:1.5em"><span class="icon">💡</span></div><div style="width:100%">You can customize the coverage requirement using the <code><strong>fail_under</strong></code> option. In our example, we&#x27;ve set it to 80%.</div></figure><p id="48eefff4-a17d-47c2-bdbc-002929d3d574" class="">To enable coverage reporting, run your tests with the <strong><code>pytest --cov</code></strong> option:</p><pre id="662facc8-e27b-47ca-8a63-3f448eddac7f" class="code"><code>poetry run pytest --cov</code></pre><p id="041b3b4a-e877-470c-81f2-5f4f8ce142a0" class="">You&#x27;ll see output similar to the following:</p><pre id="61a0213c-e954-4ea8-9567-23f9c1e24db4" class="code"><code>poetry run pytest --cov

======================================= test session starts =======================================
platform win32 -- Python 3.10.7, pytest-7.4.2, pluggy-1.3.0
rootdir: C:&lt;dir&gt;\&lt;your-repo-name&gt;
configfile: pyproject.toml
plugins: cov-4.1.0
collected 2 items

tests\test_game.py .                                                                                             [100%]

---------- coverage: platform win32, python 3.10.7-final-0 -----------
Name                                  Stmts   Miss Branch BrPart  Cover   Missing
---------------------------------------------------------------------------------
src\&lt;your_package_name&gt;\__init__.py       1      0      0      0   100%
src\&lt;your_package_name&gt;\game.py          34      0     10      1    98%   29-&gt;48
---------------------------------------------------------------------------------
TOTAL                                    35      0     10      1    98%

Required test coverage of 80.0% reached. Total coverage: 97.78%

================================================== 1 passed in 0.76s ==================================================</code></pre><p id="e6fdc183-7c28-4663-8593-f9919c534a98" class="">In this output:</p><ul id="995dc4da-e222-47d7-93f1-c97f2b43c1e8" class="bulleted-list"><li style="list-style-type:disc">The reported code coverage is 97.78%, which means that nearly 98% of your code has been executed during testing.</li></ul><ul id="05c0937f-7050-4dcc-b679-e8366a08198a" class="bulleted-list"><li style="list-style-type:disc">However, achieving high code coverage does not guarantee the correctness or effectiveness of your test cases. It merely indicates that your tests have exercised all lines and branches in your code. Be sure to verify that your tests also thoroughly validate your program&#x27;s functionality, not just its execution paths.</li></ul></details></li></ul><ul id="5b7aecf8-ce9c-4612-895f-0ceb19a8ad10" class="toggle"><li><details open=""><summary><strong><strong>Test automation with Nox</strong></strong></summary><p id="4dd29d5b-7aad-4112-adec-9e1e86a53d10" class="">Now it is time to automate testing in multiple python environments. <a href="https://nox.thea.codes/en/stable/">Nox </a>is a versatile tool designed for automating testing in multiple Python environments. It takes the complexity out of managing different environments and ensures that only the necessary dependencies are installed for each testing scenario.</p><p id="0c85d9df-f1cd-49b8-aeeb-beb9dfb008af" class="">First things first, you need to install Nox using pip. Open your terminal and run the following command:</p><pre id="2560fcdb-6899-43fd-b42b-409e41088e95" class="code"><code>pip install --user --upgrade nox</code></pre><figure class="block-color-gray_background callout" style="white-space:pre-wrap;display:flex" id="6c4ba329-cafb-4a7b-b2c2-b0b34f408d8b"><div style="font-size:1.5em"><span class="icon">💡</span></div><div style="width:100%">Nox is an integral part of your developer toolkit, just like Poetry and pyenv. Be mindful when installing Nox alongside Poetry, as things can get a bit complex. Nox may need to invoke Poetry, potentially leading to situations where Nox installs itself into the environments it manages. This can be tricky to debug when issues arise. Consider this when incorporating Nox into your existing Python development environment.</div></figure><p id="0d41b16d-459b-40c4-aa3a-97fc6d393f05" class="">To begin using Nox for test automation, you&#x27;ll need to define a configuration file named <code><strong>noxfile.py</strong></code> in the root folder of your project. This file specifies the Python versions you want to test against and the commands to execute.</p><pre id="79bb8de8-939d-43c2-adeb-26e19c564c2d" class="code"><code># noxfile.py
import nox


@nox.session(python=[&quot;3.10.7&quot;, &quot;3.9.13&quot;])
def tests(session):
    session.run(&quot;poetry&quot;, &quot;install&quot;, external=True)
    session.run(&quot;pytest&quot;, &quot;--cov&quot;)</code></pre><p id="e16a33b0-825d-445e-9a87-5550467a06f2" class="">In this configuration, we&#x27;ve defined a session named <code><strong>tests</strong></code>. This session does two key tasks:</p><ol type="1" id="7f9e63ea-5639-4636-b15c-96e6c6a89495" class="numbered-list" start="1"><li>Installs project dependencies using <code><strong>poetry install</strong></code>.</li></ol><ol type="1" id="21190677-42ff-4101-ba00-ad42f46917c2" class="numbered-list" start="2"><li>Runs the test suite using <code><strong>pytest</strong></code> with coverage.</li></ol><p id="20fe3ab0-037b-4607-8fc2-e7a027bb0311" class="">Note the use of <code><strong>external=True</strong></code> when running <code><strong>poetry install</strong></code>. This tells Nox that Poetry is an external command and should not be treated as part of the isolated test environment.</p><p id="d9990cdb-2230-4e61-ac56-e3ded43f2e9c" class="">
</p><p id="23697126-175f-4db8-a9e7-1764ff032440" class="">With your <code><strong>noxfile.py</strong></code> in place, Nox can now create virtual environments for the specified Python versions (in this case, Python 3.10.7 and Python 3.9.13) and execute the <code><strong>tests</strong></code> session inside each environment.</p><p id="18d5e4fa-9230-4c00-a54e-ddd8593a9199" class="">To run the tests, use the following command:</p><pre id="d832be3d-7cde-4046-8b99-94b138dc1b8b" class="code"><code>python -m nox -r</code></pre><p id="f182f0b6-3456-4a7a-ad90-0aa494482a02" class="">Sometimes, you may need to pass additional options to <code><strong>pytest</strong></code>, such as selecting specific test cases or configuring test behavior. You can modify your <code><strong>noxfile.py</strong></code> to allow overriding these options via the <code><strong>session.posargs</strong></code> variable:</p><pre id="f37cb752-e5bb-4ec5-b9a2-8e4f7a5e9855" class="code"><code># noxfile.py
import nox


@nox.session(python=[&quot;3.10.7&quot;, &quot;3.9.13&quot;])
def tests(session):
    args = session.posargs or [&quot;--cov&quot;]
    session.run(&quot;poetry&quot;, &quot;install&quot;, external=True)
    session.run(&quot;pytest&quot;, *args)</code></pre><p id="5a047178-6892-49df-ad23-29614614fa16" class="">Now, when you run Nox, you can pass additional options to <code><strong>pytest</strong></code> like this:</p><pre id="d08a41ae-35ca-4016-aa48-3fa578ec377d" class="code"><code>python -m nox -r -- tests/test_game.py</code></pre><p id="008c1725-aada-4c5c-9539-397f8045c203" class="">This command will run the tests in the specified module, allowing you to customize the testing process as needed.</p></details></li></ul></div></article>