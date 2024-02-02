---
Tags: Note
Date: 2021-11-30
---
# Jira Google Forms automation (Code)
og Code by [[Duncan Middlebrook]], documented [here](https://woolworths-agile.atlassian.net/wiki/spaces/DAI/pages/4221404693/Google+Forms+Jira+Integration)
To be customised per project
I've added additional //comments to make it easier going forward

## To Do
- [x] Additional Formatting and Commenting to make it super easy, barely an inconvenience to implement #task ✅ 2022-01-17

## OG Code 

// This script takes the user inputs from the Google Form, and will create a JIRA issue when the form is submitted via the REST API
// Takes user input info, and passes it into an event parameter "e"

// Requirements before beginning
//    - JIRA Project Key
//    - JIRA User ID (available from [here](https://woolworths-agile.atlassian.net/jira/people/me))
//    - Google Account to send emails from (AppScript MUST be setup from that account)
//    - JIRA API Key (Get API Key from [here](https://id.atlassian.com/manage-profile/security/api-tokens), then encode it in the format of emailaddress:apikey by going [here](https://www.base64encode.org/) and record the result)

function createIssue(e){
// Assign variables to the form data submitted by the requestor from the spreadsheet associated with the Google form.
// NOTE: Update the [n] to the cell value in your spreadsheet.
  var reporter = e.values[5];
  var email = e.values[6];
  var summary = e.values[2] + " - " + e.values[4];

  var url = "https://woolworths-agile.atlassian.net/rest/api/2/issue";
 
 // NOTE: Field Names can be whatever you want.
  var longdescription = "Requestor Name Email: " + e.values[5] + " ("+ e.values[6] + ") \n\n" +
                        "Business Area: " + e.values[1] + "\n\n" +
                        "Business Request: " + e.values[2] + "\n\n" +
                        "Business problem: " + e.values[4] + "\n\n" +
                        "Urgency: " + e.values[3];
  
// The POST data for the JIRA API call
  var data = {
    "fields": {
      "project":{
        "key": "B2CF" // JIRA Project Key
      },
      "summary": summary,
      "description": longdescription,
      "reporter": {"id":"5fbb510d0d2f61006f41d619"}, // JIRA User
      "issuetype":{"name": "Task"}
    }
  };
//
// Turn all the post data into a JSON string to be send to the API
//
  var payload = JSON.stringify(data);
  var headers = {
    "content-type": "application/json",
    "Accept": "application/json",
    "authorization": "Basic cHNuZWRkZW5AYmlndy5jb206Zm5OUWpIcnhYU1g2dEw2Y1BUWk9FMDQz=="
  };  // JIRA API Key from base64encode.org
 
// A final few options to complete the JSON string
  var options = {
    "content-type": "application/json",
    "method": "POST",
    "headers": headers,
    "payload": payload
  };
//
// Make the HTTP call to the JIRA API
//
  var response = UrlFetchApp.fetch(url, options);
  Logger.log(response.getContentText());
//
// Parse the JSON response to use the Issue Key returned by the API in the email
//
  var dataAll = JSON.parse(response.getContentText());
  var issueKey = dataAll.key
  Logger.log(dataAll)
//
// Assign variables for the email reposnse
//
  var emailSubject = "Your request no. " + issueKey + " has been created";
  var emailBody = "Thank you for your ticket submission." + "\n\n" +
    "Your request has been created, your reference is " + issueKey + " which can be accessed via the following link to the JIRA system:" + "\n\n" +
      "https://woolworths-agile.atlassian.net/browse/"+ issueKey + "\n\n" +
       "Your eCom Finance Partner will be in touch soon to discuss your ticket submission.  "
//
// Send an email to the requestor
//
MailApp.sendEmail(email, emailSubject, emailBody,)
 }
 ```