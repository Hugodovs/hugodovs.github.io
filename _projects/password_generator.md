---
title: project-password_generator
topic: miscellaneous
layout: only_header_and_footer_with_pyscript
permalink: /projects/password_generator/
---

<div class="section" id="about">
  <div class="container">
    <div class="tab-content gallery mt-5">
      <div class="tab-pane active" id="miscellaneous1">
        <div class="ml-auto mr-auto">
          <div class="row">
            <div class="col-md-6">
              <form onsubmit="return false">
                  <br>
                  <label for="masterPassword">Master Password:</label>
                  <input type="text" id="masterPassword" name="masterPassword" value="">
                  <br>
                  <br>
                  <span for="website">Website:</span>
                  <input type="text" id="website" value="" list="websiteOptionList" />
                  <datalist id="websiteOptionList">
                      <option value="www.facebook.com.br"></option>
                      <option value="www.github.com.br"></option>
                      <option value="Strawberry"></option>
                  </datalist>
                  <br><br>
                  <input pys-onClick="get_password" type="submit" id="btn-form" value="Generate Password!">
              </form> 
            </div>
            <div class="col-md-6">
              <span id = 'output'></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

