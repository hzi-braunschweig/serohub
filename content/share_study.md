---
title: Share your study
date: 2020-05-01
menu:
  main:
    weight: 5
---

## Share a study
To add your study, use our [study management interface](http://localhost:1313/admin/#). Note, this requires a [GitHub](https://github.com/) account to be able to login. 

We will review the provided information and publish the study.

{{< video "/videos/HowToAddAStudy.mp4">}}

## Share study data
We are also working on a database of study-related data to support meta-analysis and more.

If you'd like to share some data with us, please fill out this form:
<form name="contact" method="POST" data-netlify="true">
    <div class="row">
        <div class= "column medium-6">
            <h2>Information</h2>
            <p>
              <label>Your Name*: <input type="text" name="name" required/></label>   
            </p>
            <p>
              <label>Your Email*: <input type="email" name="email" required/></label>
            </p>
            <p>
              <label>Your Affiliation(s)*: <input type="text" name="affiliations" required/></label>
            </p>
                <p>
                    <label>Study name*: <input type="text" name="study_name" required/></label>
                </p>

  </div>
  <div class= "column medium-6">
  <h2>Data</h2>
  <p>Share a link to where the file can be downloaded (preferable) or upload the files.</p>
    <p>
    <label>Data URL: <input type="text" name="data_url"/></label>
  </p>
  <p>    <label>Data files: <input type="file" accept:".docx,application/msword,application/pdf,.pdf,.xlsx" name="data_files" multiple /></label>
  </p>
  <p>
    <label>Who this data can be shared with: <select name="role[]" multiple>
      <option value="everyone">Everyone</option>
      <option value="germany">Researchers in German institutions</option>
    </select></label>
  </p>
<p>  <input type="checkbox" id="authorisation" name="authorisation" required>
  <label for="authorisation">I confirm I have the authorisation to share the information and any data relating to this study*</label> </p>
  <p> 
    <button type="submit">Send</button>
  </p>
  </div>
    </div>
</form>