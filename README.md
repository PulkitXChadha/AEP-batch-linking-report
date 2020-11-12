# AEP-batch-linking-report

## Introduction

The collection shared in this repo allow you to report on system generated Identity Service and Profile Store batches related to the Data Lake batches you see in AEP's UI.

The report generated is in tabular form where each row correspond to the data lake batch. Relative columns for UPSBatch and UISBatch are populated where applicable.

## How to use the collection

1. Install the collections and environment into postman.

   - Step a: In Postman select Import
   - Step b; Select the three files in the Postman folder on this repo
   - Step c: Import the files into postman

   <img src="images/Step 1.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />

2. Add Integration details/environment parameters in postman

   - Step a: Select the Environment from the top right
   - Step b: Add the Adobe Console Integration details. You can get this from [Adobe Developer Console](https://console.adobe.io/)

   <img src="images/Step 2.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />

   _Note_: You will also need the private key associate with this integration.

3. Get Access Token

   - Step a: With the Environment selected, Hit the GET INIT: Load Crypto Library for RS256 call
   - Step b: Hit the POST IMS: JWT Generate + Auth to load the get the access token.

   <img src="images/Step 3a.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />

   _Note_ The access token will automatically be saved in the ACCESS_TOKEN environment variable

4. Get the Batch Linkage Report

   - Step a: Hit the GET AEP Batch Linking report call.
   - Step b: Go to the Visualize tab in the response section

   <img src="images/Step 4.png" alt="Markdown Monster icon" style="float: left; margin-right: 10px;" />

   _Note_

   - UPSBatch: Group of columns with details of the related Profile Store Batch
   - UISBatch: Group of columns with details of the related Identity Store Batch

## Limitation:

The Batch API call only queries 100 batch at a time if the linked batches are not available within the 100 batches in the response the report wont show the linked entries.
