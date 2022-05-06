# Create AI-Model Definition

This article explains about how create to AI-Model Definition for the following in Watson AIOps.

- Log Anomaly detection
- Similar Incidents
- Similar Incidents
- Enabling Story Creation Policy

The article is based on the the following

- RedHat OpenShift 4.8 on IBM Cloud (ROKS)
- Watson AIOps 3.3.0


## 1. Create AI-Model Definition for log anomaly

1. Click on `AI Model Management` link

<img src="images/log-00001.png">

2. Click on `Configure` link in `Log anomaly detection - natural language` card

<img src="images/log-00002.png">

3. Click on `Next` 

<img src="images/log-00003.png">

4. Enter the below field values

- Configuration Name 
- Configuration Description 

5. Click on `Next` 

<img src="images/log-00004.png">

4. Enter the below field values

- Custom : On
- Start Date: Yesterday date
- End Date: Tomorrow date

(While training, the logs date should fall under this date range)

5. Click on `Next` 

<img src="images/log-00005.png">

5. Click on `Next` 

<img src="images/log-00006.png">

5. Click on `Next` 

<img src="images/log-00007.png">

4. Enter the below field values

- Deployment Type : On Completion

5. Click on `Done` 

<img src="images/log-00008.png">

5. See the status as `Configured` 

<img src="images/log-00009.png">

9. Click on `Manage` tab.

The Log Anomaly model training definition is displayed.

<img src="images/log-00010.png">


## 2. Create AI-Model Definition for Similar Incidents


1. Goto the page `AI Model Management`

<img src="images/similar-00001.png">

2. Click on `Configure` link in `Similar Incidents` card

![ServiceNow](./images/similar-00002.png)

3. Click on `Next`

![ServiceNow](./images/similar-00003.png)

4. Enter the below field values

- Configuration Name 
- Configuration Description 

5. Click on `Next` 

![ServiceNow](./images/similar-00004.png)

6. Click on `Next` 

![ServiceNow](./images/similar-00005.png)

7. Click on `Done` 

8. Similar incidents training definition is created

![ServiceNow](./images/similar-00006.png)

9. Click on `Manage` tab.

The Similar incidents  training definition is displayed.

![ServiceNow](./images/similar-00007.png)

## 3. Enabling Story Creation Policy

This section about how to enable a `Default story creation policy for high severity alerts` in Watson AIOps. 

1. Goto `Automation > Policies`

2. Click on  `Disabled` for the policy `Default story creation policy for high severity alerts`

This will enable the policy.

<img src="images/enable-story-creating-1.png">

3. The policy is enabled

<img src="images/enable-story-creating-2.png">