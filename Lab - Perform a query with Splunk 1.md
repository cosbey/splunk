
## Activity Overview

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/J48S9QgEQrqf29BzF2Gvmw_7f3632c3b9ce43c0818870c60dc3e3f1_swHMknrH8EeYAq6ceF-lXek0EO2h6t9tMrAIZGXHXVk1zyA-BtNjYNdVc4OIMHSLOdR8JQC50BJBMa_ge2g-V63PB1xPZaJF3xTlWZ7x3KLy6U76ErL_QvDX5_7Gr_aooaGNdwgnnl7mwIENivcsDWZEqZl0rOYF1cVGOH7jpD6fbKF6TNcZxxurhnnvRg?expiry=1693526400000&hmac=fCRinu4RGM5W4XfScNW9tt0JZj9aE8VC35YJiJW7qrw)

In this activity, you'll be introduced to the Splunk platform. Then, you'll use Splunk Cloud to upload data, perform basic searches on the data, and answer a series of questions. Follow the instructions in the [Follow-along guide for Splunk sign-up](https://www.coursera.org/learn/detection-and-response/supplement/Wg478/follow-along-guide-for-splunk-sign-up) to complete the following before you begin using Splunk:

- Create a Splunk account
    
- Activate a free trial of Splunk Cloud
    
- Upload data into Splunk Cloud
    

**Please note that this activity is optional and will not affect your completion of the course.**

So far, you've learned that SIEM tools, such as Splunk, are an important part of a security analyst's toolbox because they provide a platform for storing, analyzing, and reporting on data from different sources. You also explored some basic searches using Splunk's querying language, called Search Processing Language (SPL), which included the use of pipes and wildcards.

Creating effective searches is an important skill because it enables you to quickly and accurately find the information you are looking for within a large amount of data. Quick and accurate searching is especially useful during incident response, because you might need to swiftly identify and address a security incident. Effective search techniques also help you efficiently identify patterns, trends, and anomalies within data.

## Scenario

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/sqDr4NgwS26nD0grrYah3A_b9b7a88fb81e4fb1bdf51557bf1f2cf1_Qq0HhAH9J5fZg6Rd1Ta4ML9tPRdsEdbMtFw2q65Jr2v4kavO6mJQA8xTHRHge9p3z5vSWdDXz2cdY97fdavi1_1DfZ4b6VUsk2zOIbp42eZEM6Lgc3aseyeEPgXO6B8Uo22KL2SfufCDlk04BYHdEC0?expiry=1693526400000&hmac=wcL3Tq4LBcDAohZd_OPtqLQl70RUXYUCm8OcCJK8yww)

Review the following scenario. Then complete the step-by-step instructions.

You are a security analyst working at the e-commerce store Buttercup Games. You've been tasked with identifying whether there are any possible security issues with the mail server. To do so, you must explore any failed SSH logins for the root account.  

_**Note**_: _Use the incident handler's journal you started in_ [_a previous activity_](https://www.coursera.org/learn/detection-and-response/exam/ghRgc/portfolio-activity-document-an-incident-with-an-incident-handlers-journal) _to take notes during the activity and keep track of your findings._

## Step-By-Step Instructions

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/sqDr4NgwS26nD0grrYah3A_b9b7a88fb81e4fb1bdf51557bf1f2cf1_Qq0HhAH9J5fZg6Rd1Ta4ML9tPRdsEdbMtFw2q65Jr2v4kavO6mJQA8xTHRHge9p3z5vSWdDXz2cdY97fdavi1_1DfZ4b6VUsk2zOIbp42eZEM6Lgc3aseyeEPgXO6B8Uo22KL2SfufCDlk04BYHdEC0?expiry=1693526400000&hmac=wcL3Tq4LBcDAohZd_OPtqLQl70RUXYUCm8OcCJK8yww)

Follow the instructions and answer the following questions to complete the activity.

## Step 1 : Access supporting materials

The following supporting materials will help you complete this activity. The data contains log and event information from Buttercup Games' mail servers and web accounts. This includes information like access and authentication logs, email logs, and more.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/nelHokyyRmiK209KviLzmg_38dcf9e4cb9b4d8492475a2588c484f1_F0rtw42sG9GUjH-ChB3mK9EaNXPqyLNmouTCXuWCuOXSSFN-AbMpwK2xRM5FuU7KfhnuzTGAc9Zqj9kb093dZlazeh0XbBahLI2vIq_8-bQeyUDH4PvrjcMQQ4wovVEG1YYDiWUe7Tm87KfPjRdqpCU?expiry=1693526400000&hmac=V9RIM4dgn_kI0DMnmmWO-r-O6oYTeb7AoPshmPEXCV8)

To download this data, click the link then click the download icon.

Link to supporting materials: [tutorialdata.zip](https://drive.google.com/file/d/1nDz_DZB4ADbD4tvaDa54_l1FoT_jtVy4/view?usp=share_link) file

## Step 2 : Create a Splunk Cloud account 

To use Splunk Cloud, you must create an account. Follow _Part 1 - Create a Splunk Cloud_ _account_ and _Part 2 - Verify your email_ in the [Follow-along guide for Splunk sign-up](https://www.coursera.org/learn/detection-and-response/supplement/Wg478/follow-along-guide-for-splunk-sign-up) to create an account.

## Step 3 : Sign up for a free Splunk Cloud trial

After you've created your Splunk account, you'll need to sign up for a free Splunk Cloud trial. Follow _Part 3 - Activate a Splunk Cloud trial_ in the [Follow-along guide for Splunk sign-up](https://www.coursera.org/learn/detection-and-response/supplement/Wg478/follow-along-guide-for-splunk-sign-up).

_**Note**__: If you experience any issues activating your Splunk Cloud trial please check out the_ [_Splunk cloud tutorial video_](https://www.youtube.com/watch?v=5W7mzW8GATs).

## Step 4 : Upload data into Splunk

To operate effectively, it's essential that SIEM tools ingest and index data. SIEM tools collect and process data so that it becomes searchable events that can be queried, viewed, and analyzed.

So far, you've created a Splunk account and activated and accessed the Splunk Cloud free trial, but your Splunk Cloud instance does not contain any data. Next, you'll need to upload data into Splunk to start querying. Complete the following steps to upload data into Splunk:

1. If you haven't already, download the data file from Step 1:  [tutorialdata.zip](https://drive.google.com/file/d/1nDz_DZB4ADbD4tvaDa54_l1FoT_jtVy4/view). Click the link then click the download icon. Do not uncompress the file.
    
2. Navigate to Splunk Home from your Splunk Cloud free trial instance. You might need to log in again using your credentials from Step 3.
    
3. On the Splunk bar, click **Settings.** Then click the **Add Data** icon.
    
4. Click **Upload**.
    
5. Click the **Select** **File** button.
    
6. Upload the tutorialdata.zip file, and click **Open**.
    
7. Click the **Next** button to continue to **Input** **Settings**.
    
8. By the **Host** section, select **Segment in path** and enter **1** as the segment number.
    
9. Click the **Review** button and review the details of the upload before you submit. The details should be as follows: Input Type: Uploaded File File Name: tutorialdata.zip Source Type: Automatic Host: Source path segment number: 1 Index: Default
    
10. Click **Submit**. Once Splunk has ingested the data, you will receive confirmation that the file was successfully uploaded.
    

_**Note**__: If you are experiencing issues uploading data into Splunk, refer to the_ [_Splunk Search Tutorial_](https://docs.splunk.com/Documentation/SplunkCloud/9.0.2209/SearchTutorial/GetthetutorialdataintoSplunk) _guide for help._


## Step 5 : Perform a basic search 

Take a moment to examine the Splunk Cloud interface by locating the app panel, the Explore Splunk panel, and the Splunk bar.

![The Splunk home page for Splunk Cloud Platform displays the Apps panel, the Splunk bar and the Explore Splunk panel](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/cc9oz1SmRCK3pfm87DcKZQ_dcda39fb68f147469c41a6b9fcb3cbf1_CS_SRQ-006_homepage-with-labels.png?expiry=1693526400000&hmac=G9yQz39__0o0XcoKZtGJbIYpCXthoHUbB3X3Z5oI4aY)

Now that you've uploaded the data into Splunk, perform your first query to confirm that the data has been ingested, indexed, and is searchable. Follow these steps to perform a query:

1. Navigate to Splunk Home. (To return to Splunk Home, click the Splunk Cloud logo on the Splunk Cloud page.)
    
2. Click **Search & Reporting**. You may close any pop ups that appear.
    
3. In the search bar,  enter your search query: `index=main` This search term specifies the index. An **index** is a repository for data. Here, the index is a single dataset containing events from an index named main.
    
4. Select **All Time** from the time range dropdown to search for all the events across all time.
    
5. Click the search button. Note that the search button is represented by the magnifying glass icon. Your search should retrieve thousands of events.
    

![The Splunk Cloud search page displays the search bar and the time range drop down](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/t-w-qDeCQmOMDMXZRUz8Lw_8ceeb7ac61d7471c9ead6a03d17e5cf1_CS_SRQ-006_search.png?expiry=1693526400000&hmac=VdOtJsIK54RPj3jGIt9flcITwqVvHytMTDLvzyzo8u0)

_**Pro tip**__: It's a best practice to use short time ranges in your searches because a shorter time range returns results faster and uses fewer resources. Adjust the time using the time range dropdown or by using_ [_time modifiers_](https://docs.splunk.com/Documentation/SCS/current/Search/Timemodifiers) _in your search._

![[Pasted image 20230829222746.png]]



## Step 6 : Evaluate the fields

When Splunk indexes data, it attaches fields to each event. These fields become part of the searchable index event data. This helps security analysts easily search for and find the specific data they need. Now that you've run your first query, examine the search results and the fields.

For each event the fields are host, source, and sourcetype. Under **SELECTED FIELDS**, examine the same fields.

![Splunk search results with the host, source, and sourcetype fields highlighted in red box](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/b-LM5OKBQRecaBKlhE8u4A_10aa13c3ffe64074b8fc019a33cd2cf1_8I5gN09dzpvkvx9AjDfkxZmJ62cOmcJyN4F-fxT0XfU3fHWId7Sf5HLokjN5n8vdQSxBLPvzQmk24uXoj-5T_Egb2EwAgAhY4dpRhRvoUy5D0x7gcfLb7SMpx9aBWso7RW8xG3tl0Jge_VMBuesFp7bPkB3dCqBm1N9Z36HCce21zwEvvdNyxNfgo-U1QQ?expiry=1693526400000&hmac=lPF6k9XqCRLTNtshuI1SoANNDpOaSagK3QSQtMfDQtQ)

Examine the field values by clicking on the field under **SELECTED FIELDS**. You should observe the following:

- **host**: The host field specifies the name of the network host from which the event originated. In this search there are five hosts:
    
    - mailsv - Buttercup Games' mail server. Examine events generated from this host.
        
    - www1 - This is one of Buttercup Games' web applications.
        
    - www2 - This is one of Buttercup Games' web applications.
        
    - www3 - This is one of Buttercup Games' web applications.
        
    - vendor_sales - Information about Buttercup Games' retail sales.
![[Pasted image 20230829223756.png]]
        
- **source**: The source field indicates the file name from which the event originates. You should identify eight sources. Notice /mailsv/secure.log, which is a log file that contains information related to authentication and authorization attempts on the mail server.

![[Pasted image 20230829223826.png]]
    
- **sourcetype**: The sourcetype determines how data is formatted. You should observe three sourcetypes. Examine secure-2.

![[Pasted image 20230829223906.png]]

## Step 7: Narrow your search 


Because you've been tasked with exploring any failed SSH logins for the root account on the mail server, you'll need to narrow the search results for events from the mail server.

Under **SELECTED FIELDS**, click **host** and click **mailsv**.

Notice that a new term has been added to the search bar: index=main host=mailsv. The search results have narrowed to over 9000 events that are generated by the mail server.

## Step 8: Search for a failed login for root

Now that you've narrowed your search results to events generated by the mail server, continue to narrow the search to locate any failed SSH logins for the root account. 

1. Clear the search bar.
    
2. Enter `index=main host=mailsv fail*` root into the search bar. This search expands on the search from the previous task and searches for the keyword fail*. The wildcard tells Splunk to expand the search term to find other terms that contain the word _fail_ such as _failure_, _failed_, etc. Lastly, the keyword root searches for any event that contains the term root.
    
3. Click **search**.




## Step 9: Evaluate the search results

Your search from the previous task should have retrieved search results for over 300 events. Navigate to other pages of the search results to observe the events not listed on the first page of results.

_**Pro tip**__: Splunk highlights search terms in search results to make it easier to identify where the search terms appear in the data._

![[Pasted image 20230829225249.png]]

## Step 10: Answer questions about the search results



**Question 1: How many events are contained in the main index across all time?**



10-99

10,000

`Over 100,000`

100-1,000



**Question 2: Which field identifies the name of a network device or system from which an event originates?**



`source`

index

host

sourcetype



**Question 3: Which of the following hosts used by Buttercup Games contains log information relevant to financial transactions?**



`vendor_sales`

www1

www2

www3


**Question 4: How many failed SSH logins are there for the root account on the mail server?**



`More than 100`

One

100

None

## Key takeaways

In this activity, you used Splunk Cloud to perform a search and investigation. Using Splunk Cloud, you were able to:

- Upload sample log data 
    
- Search through indexed data
    
- Evaluate search results
    
- Identify different data sources 
    
- Locate failed SSH login(s) for the root account
    

If you would like to challenge yourself and explore more simulated incident investigations using Splunk, log in to Splunk and visit [Splunk Boss of the SOC](https://bots.splunk.com/).