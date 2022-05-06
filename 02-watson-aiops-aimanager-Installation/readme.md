# Watson AIOps AI-Manager Installation

This article explains about how to install Watson AIOps AI-Manager on ROKS. The below sections describes that.

- Watson AIOps 3.3.0 installation and demo setup requirements.
- Installing Watson AIOps AI-Manager on ROKS

The article is based on the the following.

- RedHat OpenShift 4.8 on IBM Cloud (ROKS)
- Watson AIOps 3.3.0

## 1. Watson AIOps 3.3.0 installation and demo setup requirements.

This documentation explains about the Hardware and account requirements for Watson AIOps 3.3.0 installation and demo setup.


### 1.1. RedHat Openshift on IBM Cloud

A RedHat Openshift on IBM Cloud (ROKS) with the below configuration needed to install Watson AIOps 3.3.0

 - OCP Version : 4.8.18
 - 5 Nodes with b3c.16x64 flavour. (CPU 16 core, Memory 64 GB)
 - Classic Infrastructure

 Here is a reference values and steps for [install](../80-provisioning-redhat-openshift-in-ibmcloud).

### 1.2. Slack Account

SRE would be indicated about the incident through ChatOps such as Slack or Team. 

Slack account is required for the WAIOps demo setup.

The link [here](../32-integrations-slack) explains about account creation and integration with WAIOps.

The link [here](https://community.ibm.com/community/user/aiops/blogs/jeya-gandhi-rajan-m1/2021/12/27/waiops-v32-series-05-slack-account-creation-and-in
) explains about account creation and integration with WAIOps.


### 1.3. ServiceNow Account

A ServiceNow account is required or atleast Developer instance to be created using the below URL as part of the WAIOps demo setup..

https://developer.servicenow.com/dev.do#!/guides/rome/developer-program/pdi-guide/obtaining-a-pdi

Also refer the url : [Up and Running](https://pages.github.ibm.com/up-and-running/watson-aiops/3.3%20PoC%20Cookbooks/ServiceNow/)  (IBMers only)

Watson AIOps can create Incidents in ServiceNow apart from slack story. Also it can train the existing incidents from ServiceNow for identifying the Similar Incidents and to choose the next best action, in case of an incident.


## 2. Installing Watson AIOps AI-Manager on ROKS

This document explains about Installing IBM Watson AIOps AI Manager 3.3.0 on ROKS.

The script is based on the IBM Documentation https://www.ibm.com/docs/en/cloud-paks/cloud-pak-watson-aiops/3.3.1?topic=manager-starter-installation-cli

Installation script is available in [files/10-install.sh](./files/10-install.sh).

### 2.1. Update Properties

#### Update entitlement Keys

1. Get `IBM entitlement key` from https://myibm.ibm.com/products-services/containerlibrary

<img src="images/image0.png">

2. Replace the value of the `ENTITLEMENT_KEY` variable in `files/00-config.sh`

```
export ENTITLEMENT_KEY=ABCD
```

### 2.2. Install AI-Manager

#### 2.2.1. Login to OCP Cluster

Login to OCP cluster using  `oc login` command .

#### 2.2.2. Run the install script

Goto the `files` folder and Run the install script as like below.

```
cd files
sh 10-install.sh
```

- It would take around 1hr to complete the istallation. 
- By default the installation is done on the namespace `cp4waiops`
- Keep checking the logs for the status. 
- The same script can be run again and again if the install stopped for any reason.

#### 2.2.3. Output
 
The installation would be completed and the output could be like this.

```
=====================================================================================================
URL : https://cpd-cp4waiops.aaaaaaaa.ams03.containers.appdomain.cloud
USER: admin
PASSWORD: EpU2m........................jYUz
=====================================================================================================

```

You can use this to login into the WAIOps Console.

### 2.3. Printing URL, Usr and Pwd

To get the AIMgr URL, user and password anytime after AIMgr install, you can run the below command. This will print the output as like above.

```
cd files
sh 19-print-url-usr-pwd.sh
```

### 2.4. Cassandra Pods

If you have any probelm with the cassandra pods, run the below command

```
cd files
sh 11-install-sync-cassandra.sh
```