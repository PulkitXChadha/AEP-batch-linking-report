# AEP Batch Linking Report

## Introduction

The collection shared in this repo allow you to report on system generated Identity Service and Profile Store batches related to the Data Lake batches you see in AEP's UI.

The report generated is in tabular form where each row correspond to the data lake batch. Relative columns for UPSBatch and UISBatch are populated where applicable.

## How to use the collection

1. Install the collections and environment into postman.

   - Step a: In Postman select Import
   - Step b; Select the three files in the [Postman Collection folder](Postman%20Collections) in this repo
   - Step c: Import the files into postman

   <img src="images/Step 1.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" /> &nbsp;&nbsp;

2. Add Integration details/environment parameters in postman

   - Step a: Select the Environment from the top right
   - Step b: Add the Adobe Console Integration details. You can get this from [Adobe Developer Console](https://console.adobe.io/)

   &nbsp;<img src="images/Step 2.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />&nbsp;&nbsp;

   _Note_: You will also need the private key associate with this integration.

3. Get Access Token

   - Step a: With the Environment selected, Hit the GET INIT: Load Crypto Library for RS256 call

     &nbsp;<img src="images/Step 3a.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" /> &nbsp;

   - Step b: Hit the POST IMS: JWT Generate + Auth to load the get the access token.
     &nbsp;<img src="images/Step 3b.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />&nbsp;

   _Note_ The access token will automatically be saved in the ACCESS_TOKEN environment variable

4. Get the Batch Linkage Report

   - Step a: Hit the GET AEP Batch Linking report call.
   - Step b: Go to the Visualize tab in the response section

   &nbsp;<img src="images/Step 4.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />&nbsp;

   _Note_

   - UPSBatch: Group of columns with details of the related Profile Store Batch
   - UISBatch: Group of columns with details of the related Identity Store Batch
   - You can add/modify parameters to filter the response based on a condition. Placeholder parameters are included in the API call

## Limitation:

The Batch API call only queries 100 batch at a time if the linked batches are not available within the 100 batches in the response the report wont show the linked entries.

![views](https://gpvc.arturio.dev/PulkitXChadha?v=3)
