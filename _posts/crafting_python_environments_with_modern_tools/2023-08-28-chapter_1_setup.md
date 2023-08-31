---
layout: post
title: "Chapter 1: Setup"
date: 2023-08-28 00:00:00
image: /assets/images/blog/crafting_python_environments_with_modern_tools/logo_1.jpg
tags: python poetry pyenv
description: This article is Crafting Python Environments with Modern Tools series! Let's get started with Chapter 1 - Setup!
permalink: /2023/08/28/chapter_1_setup.html
---

<article id="b62811a6-35d1-4247-a194-ef97ff15dedf" class="page sans"><header><h1 class="page-title">Chapter 1: Setup </h1><p class="page-description"></p></header><div class="page-body"><ul id="1c2355ff-b46a-4286-b86a-b29b47ce63d0" class="toggle"><li><details open=""><summary><strong>Getting Your GitHub Repository Ready</strong></summary><p id="409aa782-2a41-4dcd-ae0b-641bc9d27227" class="">For the purposes of this guide, <a href="https://github.com/">GitHub</a> is used to host the public git repository for your project. Create a repository, and populate it with <code>README.md</code> and <code>LICENSE</code> files. For this project, I will use the <a href="https://opensource.org/license/mit/">MIT license</a>, a simple permissive license.</p><p id="d1e30856-9332-40d0-8100-20047697493b" class="">In this section, we&#x27;ll kick off your project by setting up a repository on GitHub. This is where your project&#x27;s source code will live. Follow these steps:</p><ol type="1" id="33744ca1-2284-4bfb-8993-80a7af572c3d" class="numbered-list" start="1"><li>Create a new repository on GitHub. You can name it whatever you want.</li></ol><ol type="1" id="20750320-2478-49a8-8d67-c3a5884e4104" class="numbered-list" start="2"><li>Once your repository is created, add a <code><strong>README.md</strong></code> and <code><strong>LICENSE</strong></code> files. We&#x27;ll go with the simple and permissive  <a href="https://opensource.org/license/mit/">MIT license</a> for this project.</li></ol><ol type="1" id="fbc8e90c-89bb-476e-98b2-8a74269ed387" class="numbered-list" start="3"><li>Now, let&#x27;s bring the repository to your local machine. Open your terminal and run the following commands:</li></ol><pre id="4610dcd2-63ff-4257-a22d-ae582453babc" class="code code-wrap"><code>git clone git@github.com:&lt;your-username&gt;/&lt;your-repo&gt;.git
cd &lt;your-repo&gt;</code></pre><p id="26ccb23b-e027-4566-bf0f-ef62e5e1d95b" class="">Replace <code><strong>&lt;your-username&gt;</strong></code> with your GitHub username and <code><strong>&lt;your-repo&gt;</strong></code> with the repository&#x27;s name you created.</p><p id="ebf6d263-fa5d-45c3-8cf6-97a28b43879f" class="">With this groundwork laid, you&#x27;re ready to dive into building your Python project!</p></details></li></ul><ul id="061ec868-f111-4da4-9926-48a0f8076f99" class="toggle"><li><details open=""><summary><strong><strong><strong><strong>Setting Up Python Environment with pyenv</strong></strong></strong></strong></summary><p id="5e700384-b2c0-4e62-beca-0d9351fc0e68" class="">Now it&#x27;s time to set up your development environment. But forget about dealing with package managers or official binaries. We&#x27;re going to use the trusty <a href="https://web.archive.org/web/20221016175413/https://github.com/pyenv/pyenv"><strong>pyenv</strong></a> as our Python version manager. If you&#x27;re on Windows, you can use its version called <a href="https://github.com/pyenv-win/pyenv-win"><strong>pyenv-win</strong></a>.</p><p id="8fce86e6-89d7-4f44-89eb-c5c0b5cd0941" class="">Follow these steps to get your hands on the latest Python releases:</p><ol type="1" id="d6405a0f-41de-4194-b70e-02d8b0697659" class="numbered-list" start="1"><li>Head to the GitHub repository for pyenv or pyenv-win, and follow their detailed installation instructions.</li></ol><figure id="04226df5-c834-4a9b-8d6b-ee48830f12ab"><div class="source">https://github.com/pyenv/pyenv</div></figure><figure id="af28ef46-5601-43c6-b22b-66d171e5deec"><div class="source">https://github.com/pyenv-win/pyenv-win</div></figure><ol type="1" id="0db74872-fa87-42e3-aabe-b4824f91462c" class="numbered-list" start="2"><li>After getting pyenv up and running, confirm a successful installation by executing this command in your terminal:</li></ol><pre id="60fe3acd-8cb8-41c2-87f1-7e9fd18f684f" class="code"><code>$ pyenv --version
pyenv 3.1.1</code></pre><ol type="1" id="1f7a0af6-b0dd-4f1e-9df9-7d0dc7a17e3c" class="numbered-list" start="3"><li>With pyenv ready, let&#x27;s bring in the latest Python release. Open your command prompt and input:</li></ol><pre id="8cca3455-5841-4588-a926-22b65dac88b4" class="code code-wrap"><code>pyenv install 3.10.7
pyenv install 3.9.13</code></pre><p id="32402d61-dac6-489e-b340-2db34994c6fc" class="">This process might take a little while.</p><ol type="1" id="7fda83a9-3203-4ce3-a958-6ad1d91ef419" class="numbered-list" start="4"><li>Now, let&#x27;s make these fresh Python goodies accessible within your project repository:</li></ol><pre id="0afd436f-11e1-4527-ac68-791bd471adb1" class="code"><code>pyenv local 3.10.7 3.9.13</code></pre><p id="fb65f340-a184-42b0-a750-c3fc58340b87" class="">This will create the <code><strong>.python-version</strong></code> file in your repo folder.</p><ol type="1" id="de25dff9-0504-4162-a972-f34d835ee1b2" class="numbered-list" start="5"><li>Bravo! You&#x27;re now equipped with the newest and most fantastic version of Python. You should see:</li></ol><pre id="265f3e5c-8f48-4bf3-8522-105a55134822" class="code code-wrap"><code>$ python --version
Python 3.10.7

$ python310 --version
Python 3.10.7

$ python39 --version
Python 3.9.13</code></pre><p id="fbf2cac7-1b3a-4842-8fbb-e38403e36c54" class="">Feel the excitement as you&#x27;re ready to code away!</p></details></li></ul><ul id="2597d612-3817-4f16-96c5-be602368fe69" class="toggle"><li><details open=""><summary><strong>Creating a Package using the src Layout</strong></summary><p id="71591515-0d99-48f2-82d4-0d18a2294641" class="">Let&#x27;s construct the foundation of our package by setting up its initial structure.</p><p id="15bade24-21b9-4606-bfe2-322e5ab5cab9" class="">Begin by organizing your files like this:</p><pre id="becca515-90cc-4272-8e14-1eba162455c3" class="code code-wrap"><code>.
└── src
    └── &lt;your_package_name&gt;
        └── __init__.py
├── .gitignore
├── .python-version
├── LICENSE
├── README.md</code></pre><p id="e2b2dfcd-5763-4254-aad3-d621e3bdf0cd" class="">The <code><strong>__init__.py</strong></code> file within the package directory contains a simple version declaration for your package:</p><pre id="12ba0727-bd33-4410-8372-2e9cc279247b" class="code code-wrap"><code># src/&lt;your_package_name&gt;/__init__.py
__version__ = &quot;0.1.0&quot;</code></pre><figure class="block-color-gray_background callout" style="white-space:pre-wrap;display:flex" id="3b00dcdc-49a4-4469-b6ab-f32898aaf2d7"><div style="font-size:1.5em"><span class="icon">💡</span></div><div style="width:100%">Use <a href="https://web.archive.org/web/20221016175413/https://en.wikipedia.org/wiki/Snake_case">snake case</a> for the package name <code>example_name</code>, as opposed to the <a href="https://web.archive.org/web/20221016175413/https://en.wiktionary.org/wiki/kebab_case">kebab case</a> used for the repository name <code>example-name</code>. In other words, name the package after your repository, replacing hyphens by underscores.</div></figure></details></li></ul><ul id="08fc6104-11b6-45df-bbac-f3691deb2c9a" class="toggle"><li><details open=""><summary><strong><strong>Setting up a Python project using Poetry</strong></strong></summary><p id="4078a882-7aad-4b41-b62b-d5f9de5f433b" class=""><a href="https://python-poetry.org/docs/"><strong>Poetry</strong></a> represents a versatile solution for handling Python&#x27;s <strong>dependency management</strong> and <strong>packaging</strong> needs. Moreover, Poetry seamlessly integrates project-specific <strong>virtual environments</strong> as a core aspect of its functionality.</p><p id="6274b307-f6e9-4932-aa72-84ebc0d275e5" class="">Its user-friendly interface and alignment with contemporary workflows position it as the natural successor to the time-honored <a href="https://pypi.org/project/setuptools/"><strong>setuptools</strong></a>. You can explore its documentation and installation instructions via the link below:</p><figure id="ec794562-ffba-4cb0-858c-d2fc36e0a1b5"><a href="https://python-poetry.org/docs/#installation" class="bookmark source"><div class="bookmark-info"><div class="bookmark-text"><div class="bookmark-title">Introduction | Documentation | Poetry - Python dependency management and packaging made easy</div><div class="bookmark-description">Introduction Poetry is a tool for dependency management and packaging in Python. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you. Poetry offers a lockfile to ensure repeatable installs, and can build your project for distribution. System requirements Poetry requires Python 3.7+. It is multi-platform and the goal is to make it work equally well on Linux, macOS and Windows.</div></div><div class="bookmark-href"><img src="https://python-poetry.org/images/favicon-origami-32.png" class="icon bookmark-icon"/>https://python-poetry.org/docs/#installation</div></div></a></figure><p id="6438603c-c056-4be6-9f2f-eb14099acee8" class="">After getting poetry installed, confirm a successful installation by executing this command in your terminal:</p><pre id="fd518773-3fc0-45fa-b3e8-dcd53da9f54b" class="code"><code>$ poetry --version
Poetry (version 1.5.1)</code></pre><p id="6409fdd0-038a-4e9e-8f64-f5a134fea88c" class="">Let&#x27;s kickstart your Python project with these steps:</p><ol type="1" id="4af7a9ac-536d-47b7-b500-66809155fdb3" class="numbered-list" start="1"><li>Initialize your project by running:</li></ol><pre id="ecce2b9b-5a2d-4248-a2bb-5b116f2e7ab5" class="code"><code>$ poetry init --no-interaction</code></pre><p id="130d36b7-1897-4514-b94d-534ad40e0bcb" class="">This command generates a <code><strong>pyproject.toml</strong></code> file, a modern Python package configuration file as outlined in <a href="https://www.python.org/dev/peps/pep-0517/"><strong>PEP 517</strong></a> and <a href="https://www.python.org/dev/peps/pep-0518/"><strong>518</strong></a>. Your <code><strong>pyproject.toml</strong></code> might look like this:</p><pre id="99bbb091-88f3-41af-95e0-670570f8b5cc" class="code code-wrap"><code>[tool.poetry]
name = &quot;your-repo-name&quot;
version = &quot;0.1.0&quot;
description = &quot;&quot;
authors = [&quot;Your Name &lt;you@example.com&gt;&quot;]
readme = &quot;README.md&quot;
packages = [{include = &quot;your_package&quot;}]

[tool.poetry.dependencies]
python = &quot;^3.10&quot;


[build-system]
requires = [&quot;poetry-core&quot;]
build-backend = &quot;poetry.core.masonry.api&quot;</code></pre><ol type="1" id="934a8e81-e5a7-4ae8-b673-1b590718a486" class="numbered-list" start="2"><li>Now, let&#x27;s enrich the file with essential package metadata while adjusting the Python version dependency to match your project&#x27;s requirements:</li></ol><pre id="34ec9201-aed5-4c04-bec2-d079a2e129fc" class="code"><code>[tool.poetry]
name = &quot;your_package_name&quot;
version = &quot;0.1.0&quot;
description = &quot;A powerful tutorial meticulously crafted repo to breathe life into your Python repository.&quot;
authors = [&quot;Your Name &lt;you@example.com&gt;&quot;]
readme = &quot;README.md&quot;
packages = [{include = &quot;your_package&quot;, from = &quot;src&quot;}]
license = &quot;MIT&quot;
homepage = &quot;https://github.com/&lt;your-username&gt;/&lt;your-repo&gt;&quot;
repository = &quot;https://github.com/&lt;your-username&gt;/&lt;your-repo&gt;&quot;
keywords = [&quot;&lt;your-repo&gt;&quot;]

[tool.poetry.dependencies]
python = &quot;^3.9&quot;


[build-system]
requires = [&quot;poetry-core&quot;]
build-backend = &quot;poetry.core.masonry.api&quot;</code></pre></details></li></ul><ul id="c806b36b-4c66-48e0-b46b-fbea51a97a47" class="toggle"><li><details open=""><summary><strong><strong>Managing virtual environments with Poetry</strong></strong></summary><p id="9babb964-3eda-4137-98db-74be61f94e4d" class="">Poetry places a strong emphasis on isolating project environments to ensure stability.</p><p id="71652078-8f7d-498d-b735-6c63c09303be" class="">A <a href="https://docs.python.org/3/tutorial/venv.html"><strong>virtual environment</strong></a> provides your project with a self-contained runtime environment, housing a specific Python version along with a distinct set of installed Python packages. This separation prevents the dependencies of your ongoing project from interfering with the broader system-wide Python installation or other concurrent projects you might be engaged in.</p><p id="be3f8131-ed7a-4abb-abd5-765e8785d2c4" class="">To establish the virtual environment and install your package, utilize this command:</p><pre id="bd78e076-2861-4422-931b-b5ae619e58bd" class="code"><code>poetry install</code></pre><p id="e21c8a9d-4cc0-4be9-bcec-af6640e1eb0f" class="">Upon execution, you&#x27;ll observe an output akin to this:</p><pre id="fa335ae7-3b55-4cce-975b-03f6b5cce87f" class="code"><code>Creating virtualenv example-XeP1QyQd-py3.10 in C:\Users\&lt;username&gt;\AppData\Local\pypoetry\Cache\virtualenvs
Updating dependencies
Resolving dependencies...

Writing lock file

Installing the current project: example (0.1.0)</code></pre><p id="bb05b50d-d9f5-496b-bacc-61834324686a" class="">By default, Poetry establishes the virtual environment within <code><strong>{cache-dir}/virtualenvs</strong></code>, with <code><strong>cache-dir</strong></code> adapting to your specific platform. For instance, on Windows, it might be located at C:\Users&lt;username&gt;\AppData\Local\pypoetry\Cache\virtualenvs.</p><p id="e1bdd48d-cc7a-4be6-abeb-5a7c134fd5b3" class="">With this, Poetry has successfully set up a virtual environment tailored for your project, and it has incorporated your initial package into it. As a result, a lock file named <code><strong>poetry.lock</strong></code> emerges in your project&#x27;s root directory.</p><p id="bdf23048-8c3a-40a2-bad1-f9b397d01f0a" class="">To ensure the success of this process, you can verify by executing:</p><pre id="a60bca2c-6a44-4d83-a3c3-b0c2dcc84b4f" class="code code-wrap"><code>poetry run python

Python 3.10.7 (tags/v3.10.7:6cc6b13, Sep  5 2022, 14:08:36) [MSC v.1933 64 bit (AMD64)] on win32
Type &quot;help&quot;, &quot;copyright&quot;, &quot;credits&quot; or &quot;license&quot; for more information.
&gt;&gt;&gt; import example
&gt;&gt;&gt; example.__version__
&#x27;0.1.0&#x27;
&gt;&gt;&gt;</code></pre></details></li></ul><ul id="a810486e-56c9-4546-82bc-d3a5397ff216" class="toggle"><li><details open=""><summary><strong><strong>Managing dependencies with Poetry</strong></strong></summary><p id="b2d223b0-a23a-41fb-8cf5-4eed38ad4afd" class="">Time to introduce our first dependency—<a href="https://www.pygame.org/news"><strong>pygame</strong></a>. Pygame, a Free and Open Source library, empowers you to create multimedia applications like games.</p><p id="e743e657-9112-4d29-9662-4c4ec4cfbf30" class="">Let&#x27;s get started by installing the package:</p><pre id="3e0948d3-6669-441d-a796-6e62ae4dba04" class="code code-wrap"><code>$ poetry add pygame
Using version ^2.5.1 for pygame

Updating dependencies
Resolving dependencies...

Package operations: 1 install, 0 updates, 0 removals

  • Installing pygame (2.5.1)

Writing lock file</code></pre><p id="504395ce-7c6a-4ea2-9a8a-38f7f8a2a55d" class="">Upon execution, the package is swiftly downloaded and incorporated into your virtual environment. The version you&#x27;ve installed is recorded in the <code><strong>poetry.lock</strong></code> file, and a broader version constraint is appended to your <code><strong>pyproject.toml</strong></code> file.</p><figure class="block-color-gray_background callout" style="white-space:pre-wrap;display:flex" id="e7717350-2bf3-4c92-b5e2-e3fc0e7964bf"><div style="font-size:1.5em"><span class="icon">💡</span></div><div style="width:100%">Make sure to include <code><strong>poetry.lock</strong></code> in your version control system. This file holds the precise version of <code><strong>pygame</strong></code> installed in your virtual environment. This practice ensures uniformity across your team, fostering similar development and production environments.</div></figure><p id="ae787dc4-76e8-4184-b9ee-248e443534ac" class="">To upgrade the dependency to a more recent release, use the following command:</p><pre id="de075d50-9323-4c92-a66d-200d8b36b6b0" class="code"><code>$ poetry update pygame</code></pre><p id="09472b4a-d9bf-485f-bb68-2e5d5c3e51a0" class="">Executing this command initiates the process of updating the dependency to the latest compatible version while ensuring your project&#x27;s stability. Remember that you can always refer to your <code><strong>pyproject.toml</strong></code> and <code><strong>poetry.lock</strong></code> files to track the precise versions of dependencies your project relies on.</p><p id="c5b6d92b-b168-41b0-ae56-ff9e3d5412cb" class="">With <code><strong>pygame</strong></code> now installed and your environment set up to evolve with your project&#x27;s needs, you&#x27;re ready to infuse creativity and functionality into your Python project!</p></details></li></ul><ul id="1558907a-1d25-4d87-a109-70213521af70" class="toggle"><li><details open=""><summary><strong>Example: Displaying a FPS Window with Pygame</strong></summary><p id="30a85942-9100-44a9-9098-99777a15d5ca" class="">It&#x27;s time to dive into some coding and inject a small example into our package. We&#x27;ll craft a simple window that showcases the frames per second on the screen.</p><pre id="a0255bb8-ac52-443a-8d1d-e1751b6cebef" class="code"><code>#src\your_package_name\game.py
import pygame
import sys

BLACK = (255, 255, 255)

class FPS:
    def __init__(self):
        self.clock = pygame.time.Clock()
        self.font = pygame.font.SysFont(&quot;Verdana&quot;, 20)
        self.text = self.font.render(str(self.clock.get_fps()), True, BLACK)

    def render(self, display):
        self.text = self.font.render(str(round(self.clock.get_fps(),2)), True, BLACK)
        display.blit(self.text, (200, 150))

def main():
    pygame.init()
    display = pygame.display.set_mode((400, 300))
    
    fps = FPS()   

    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        display.fill((0, 0, 0))

        fps.render(display)

        pygame.display.update()
        fps.clock.tick(60)</code></pre><p id="3f95fd70-495c-4ab3-9305-391734c20243" class="">Now, navigate to your <code><strong>pyproject.toml</strong></code> and incorporate this line:</p><pre id="9746646a-a05b-434d-81b6-c20327ad3daf" class="code code-wrap"><code>[tool.poetry.scripts]
&lt;your-repo-name&gt; = &quot;&lt;your_package_name&gt;.game:main&quot;</code></pre><p id="4ece0ca8-ef66-4e74-b530-e312531a0783" class="">To finalize, install the package into your virtual environment:</p><pre id="e4aa2ef7-20b4-4cb3-a962-36a76f2d4bc4" class="code"><code>$ poetry install</code></pre><p id="9a514ad9-7d2d-467c-ae34-df216633e372" class="">At this point, you&#x27;re all set to execute the script using the following command:</p><pre id="fbf649c8-7000-47a0-a524-a13f1b4a9fc1" class="code"><code>$ poetry run &lt;your-repo-name&gt;</code></pre><p id="727b53a9-8a6c-44bb-9478-9d79833691b5" class="">You&#x27;ll be greeted with the delightful result. Your package is now up and running, creating a visual spectacle as depicted in the image below:</p><figure id="0c359543-a33a-41a9-8ef9-160554d1aefd" class="image" style="text-align:center"><a href="/assets/images/blog/crafting_python_environments_with_modern_tools/chapter_1_pygame_screenshot.png"><img style="width:409px" src="/assets/images/blog/crafting_python_environments_with_modern_tools/chapter_1_pygame_screenshot.png"/></a><figcaption><strong>Pygame screen displaying the FPS</strong></figcaption></figure></details></li></ul><p id="5c4f2b3e-0d0f-4a3f-be22-e15f55a3cb4f" class="">
</p></div></article>