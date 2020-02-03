# Whole Whale GTM Basic Formula

The file is meant to be a ready-set starting point to set basic analytics tracking on your site through Google Tag Manager
   
## Formula Contents

### Variables

* Google Analytics Settings: 
You will need to add your Google Analytics property ID. Already connected to the currently existing tags, it is a reusable option to not have to rewrite any general settings that your tag would share with others
* PII Scrubber:
You will need to edit the code by replacing in `?!youremail\.com` and `?youremail\.com`the domain name of your sites email (make sure to keep the back slash before the dot)
to use this variable, edit the Google Analytics Settings variable. Under "more settings" > "fields to set" add a field and fill in `customTask` under name, and `{{PII Scrubber}}`under value

### Triggers
If not very acquainted with GTM. Triggers are like sensors (commonly called "listeners")whose solely job is to check if an action has been performed on the page by a visitor and let GTM know that the tags related to it can be executed. Each Trigger relates to an action and it contains certain requirements for it to accept it (called "rules").

* 15 Second Timer: It checks if a visitor has been on the site for 15 seconds
* All Clicks: It checks if anything on the page has been clicked
* All LinksL: It checks if any links have been clicked
* All Outbound Links: it checks if any links outside of the site (AKA that have a different hostname)
* Form Submissions: it checks if a form has been filled and sent
* PDF Click: Checks on clicks to PDF downloadable content
* Scroll Depth: It listents for difenrent percentage ranges that the user had scrolled through the page

### Tags
* Adjusted Bounce Rate
`Category: visit
Action: 15 Seconds
Label: {{Page Path}}`
* All Link Tracking
`Category: Link Clicks
Action: Page: {{Page URL}}
Label: Link: {{Click URL}} - {{Click Text}}`
* Click Tracking
`Category: All Clicks
Action: Text: {{Click Text}}
Label: Link: Page: {{Page URL}}`

* Google Analytics Pageview

* Outbound Links
`Category: Outbound Links
Action: Click
Label: {{Click URL}}`
* PDF Downloads
`Category: Download
Action: PDF
Label: {{Click URL}}`
* Scroll Depth 
`Category: Scroll Depth
Action: Percentage: {{Scroll Depth Threshold}}
Label: Page URL: {{Page URL}}`

## Installation

After downloading the .json file, under the Admin tab within the GTM container, click `Import Container`, click `Choose Container File` and grab the .json file, then select `existing`, select your default works space, and keep `merge` as the option checked, select rename conflicting tags if your container is not empty and click confirm.

You are now ready to use the tags. Preview and edit as needed. 
