---
title: Share your study
date: 2020-05-01
menu:
  main:
    weight: 5
---

<form name="contact" method="POST" data-netlify="true">
    <div class="row">
        <div class= "column medium-6">
            <h2>About you</h2>
            <p>
              <label>Your Name*: <input type="text" name="name" required/></label>   
            </p>
            <p>
              <label>Your Email*: <input type="email" name="email" required/></label>
            </p>
            <p>
              <label>Your Affiliation(s)*: <input type="text" name="affiliations" required/></label>
            </p>
            </div>
            <div class= "column medium-6">
                <h2>About the Study</h2>
                <p>
                    <label>Study name*: <input type="text" name="study_name" required/></label>
                </p>
                <p>
                  <label>Research question: <textarea name="research_question"></textarea></label>
                </p>
                <p>
                  <label>Methods used: <textarea name="research_methods"></textarea></label>
                </p>
                <p>
                  <label>Funding sources: <textarea name="funding_sources"></textarea></label>
                </p>
                </div>
    </div>
  <div class="row">
  <div class= "column medium-12">
  <h2>Share data</h2>
  <p>Share a link to where the file can be downloaded (preferable) or upload the files.</p>
    <div class="row">
  <div class= "column medium-6">
    <p>
    <label>Data URL: <input type="text" name="data_url"/></label>
  </p>
  <p>    <label>Data files: <input type="file" accept:".docx,application/msword,application/pdf,.pdf,.xlsx" name="data_files" multiple /></label>
  </p>
    </div>
  <div class= "column medium-6">
  <p>
    <label>Who this data can be shared with: <select name="role[]" multiple>
      <option value="everyone">Everyone</option>
      <option value="germany">Researchers in German institutions</option>
    </select></label>
  </p>
  </div>
  </div>
  <div class="row">
  <div class="column medium-12">
<p>  <input type="checkbox" id="authorisation" name="authorisation" required>
  <label for="authorisation">I confirm I have the authorisation to share the information and any data relating to this study*</label> </p>
  <p> 
    <button type="submit">Send</button>
  </p>
  </div>
    </div>
  </div>
</form>
</div>