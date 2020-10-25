# GCP Notes

Create a new gcloud configuration

```
gcloud config configurations create (CONFIG_NAME)
```

> (Note that creating a configuration will automatically activate it as well)

List all of your gcloud configurations

```
gcloud config configurations list
```

Activate another existing gcloud configuration

```
gcloud config configurations activate (CONFIG_NAME)
```

List the settings for your active configuration

```
gcloud config list
```

Assign a project to a configuration

```
gcloud config set project (PROJECT_ID)
```

Set account for your configuration

```
gcloud config set account (ACCOUNT_ID)
```

------

#### Working with Kubernetes Engine Resouces

```
gcloud Container CLusters resize NAME --size=SIZE [--async] [--node-pool=NODE_POOL] [--region=REGION | --zone=ZONE, -z ZONE] [GCLOUD_WIDE_FLAG ...]
```

To get info about pods and nodes 

```
kubectl get pods or kubectl get nodes
kubdectl describe pods or kubectl describe nodes
```

To run executable terminal in pods 

```
kubectl get pods // to get pod name
kubectl exec -it POD_NAME --/bin/bash
```

> Minimalistic pods cannot run bash binary so we use a different image as deployment

To create a new deployment

```
kubectl run demo --image=nginx --port 80
```

To run executable terminal in pods

```
kubectl get pods // to get pod name
kubectl exec -it POD_NAME --/bin/bash
```

------

#### Managing App Engine Resources

> By default all traffic is set to the new version when using app deploy command
>
> and in order to split traffic we use the following command

To get the versions name and traffic list 

```
gcloud app versions list
```

To split traffic to different versions

```
gcloud app services set-traffic default --splits=V1_name=0.5,V2_name=0.5
```

> by default it splits based on ip address 

To specify the split type

```
gcloud app services set-traffic default --splits=V1_name=0.5,V2_name=0.5 --split-by=random
```

------

#### Working with Cloud Storage

To create a cloud storage bucket

```
gsutil mb -c regional -l us-east1 gs://new-bucket/
```

**To create a life cycle rule**

> life cycle rule JSON file format is given below (*lifecycle.json*):

```json
{
    'lifecycle':{
        'rule':[
            {
                'action':{
                    'type':'SetStorageClass',
                    'storageClass': 'NEARLINE'
                },
                'condition':{
                    'age':2,
                    'matchesStorageClass':['REGIONAL']
                }
            }
        ]
    }
}
```

To view file in cmd

```
cat lifecycle.json
```

To set Lifecycle to the bucket

```
gsutil lifecycle set lifecycle.json gs://new-bucket/
```

To copy file to bucket

```
gsutil cp test.txt gs://new-bucket/
```

To move files from one bucket to another

```
gsutil mv gs://new-bucket/text.txt gs://second-new/
```

> To change all users to public by 

```
: icon -> permissions -> users:allUsers:viewAccess
```

To create a signed URL to access private websites for 3mins

```
gsutil signurl -d 3m key.json gs://second-new/test.txt
```

---

#### Managing Network Resources

> To reserve a static ip address for a vm network  u can reserve it under the static ip range section

---

#### Working With Snapshots Lab

# Working with Snapshots on Google Compute Engine

## Introduction

This hands-on lab will help to provide experience working with snapshots on Compute Engine, both in the web console and command line format, which we will interact with via Cloud Shell.

## Solution

Be sure to launch the lab in incognito mode (or your browser's 'private browsing' function) to avoid cached login issues. You will already have a GCE instance in your lab that we will use for the demonstration.

### Create snapshot using web console

1. Go to the top-left menu > **Compute Engine** > **Snapshots**
2. Click **Create snapshot**
3. Name snapshot "web-backup-v1"
4. In *Source Disk* dropdown menu, select **website**
5. Click **Create**

### Make instance change - update website to VERSION 2

1. Connect to the

    

   website

    

   instance using SSH from the

    

   Compute Engine

    

   web console

   - Navigate to **Computer Engine** in the menu on the top-left
   - Click **SSH** to the right of the VM Instance

2. Enter the following command to replace index page with 'VERSION 2' instead of 'VERSION 1':

   ```
    sudo sed -i 's/VERSION 1/VERSION 2/' /var/www/html/index.html
   ```

3. Exit SSH session

### Create new snapshot using the Cloud Shell

1. Open Cloud Shell and enter following command:

   ```
    gcloud compute disks snapshot website --snapshot-names web-backup-v2 --zone us-central1-a
   ```

2. Verify snapshots using web console and Cloud Shell. Notice the size of the second snapshot compared to first:

   ```
    gcloud compute snapshots list
   ```

   ```
    gcloud compute snapshots describe web-backup-v2
   ```

### Restore first snapshot using web console in new zone

1. Go to top left menu > **Compute Engine**
2. Click **CREATE INSTANCE**
3. Name instance "website-restore-1"
4. Choose a region/zone
5. Change boot disk:
   - Select **Snapshots**
   - Select **web-backup-v1**
   - Click **Select** at the bottom
6. Select box to allow HTTP traffic
7. Click **Create**

### Restore second snapshot using command line

1. Navigate to Cloud Shell

2. Create disk from snapshot:

   ```
    gcloud compute disks create website-restore-2 --source-snapshot web-backup-v2 --zone us-central1-a
   ```

3. Create new instance from disk:

   ```
    gcloud compute instances create website-restore-2 --disk name=website-restore-2,boot=yes --zone us-central1-a --tags=http-server
   ```

## Conclusion

Congratulations, you've completed this hands-on lab!

---

# Creating and Deploying a Google Kubernetes Engine Cluster

## Introduction

In this hands-on lab, we’ll use the Cloud Shell command line from start to finish: first containerizing an app and then deploying and exposing it.

## Solution

On the lab page, right-click **Open GCP Console** and select the option to open it in a new private browser window (this option will read differently depending on your browser — e.g., in Chrome, it says "Open Link in Incognito Window"). Then, sign in to Google Cloud Platform using the credentials provided on the lab page.

On the *Welcome to your new account* screen, review the text, and click **Accept**. In the "Welcome L.A.!" pop-up once you're signed in, check to agree to the terms of service, choose your country of residence, and click **Agree and Continue**.

### Enable the Kubernetes Engine API

1. From the main Google Cloud console navigation menu, choose **APIs & Services** > **Library**.
2. Search for "Kubernetes", and enable the Kubernetes Engine API.

### Clone the Repo to Access the Files

1. Activate the Cloud Shell by clicking the icon in the top row.

2. Clone the GitHub repository:

   ```
   git clone https://github.com/linuxacademy/content-gc-essentials
   ```

3. Change directory:

   ```
   cd content-gc-essentials/gke-lab-01
   ```

### Create the Docker Image

1. Still in the Cloud Shell, build the Docker image:

   ```
   docker build -t la-container-image .
   ```

2. Configure the Docker command line to authenticate to Container Registry:

   ```
   gcloud auth configure-docker
   ```

3. Tag the registry image (you can replace your project ID where indicated by highlighting the code in yellow in the Cloud Shell, which will automatically add it to your clipboard):

   ```
   docker tag la-container-image gcr.io/<PROJECT_ID>/la-container-image:v1
   ```

4. Push the image forward (substituting your project ID where indicated):

   ```
   docker push gcr.io/<PROJECT_ID>/la-container-image:v1
   ```

### Create the Kubernetes Engine Cluster

1. Configure the zone:

   ```
   gcloud config set compute/zone us-central1-a
   ```

2. Create the clusters:

   ```
   gcloud container clusters create la-gke-1 --num-nodes=4
   ```

3. Get authentication credentials:

   ```
   gcloud container clusters get-credentials la-gke-1
   ```

4. Deploy the app (substituting your project ID where indicated):

   ```
   kubectl create deployment la-greetings --image=gcr.io/<PROJECT_ID>/la-container-image:v1
   ```

### Expose the Deployed Workload

1. Expose the deployment:

   ```
   kubectl expose deployment la-greetings --type=LoadBalancer --name=la-greetings-service --port=80 --target-port=80
   ```

2. Check its status:

   ```
   kubectl get services la-greetings-service
   ```

3. When an external IP address has been generated, copy it and paste it into a new browser tab. It should result in our application.

## Conclusion

Congratulations on completing this hands-on lab!



##   Exploring Cloud Shell

> linux cmd : pwd - to check current directory
>
> cd .. - to move to root directory
>
> clear - to clear clous shell

**To read the README-cloudshell.txt**

```
cat README-cloudshell.txt
```

**To download any files**

```
del README-cloudshell.txt
```

**To see difference between two files**

```
diff hello.js hello-html.js
```

**To run a nodejs file use** 

```
node hello.js
```

> use web preview to view the local web pages 

> Node  doesnt automatically update file changes so we use nodemon

```
nodemon hello.js
```

## Update Course Lab files

> to update git hub files to the most recent updates select update.sh and run cmd

```
chmod +x update.sh
./update.sh
```

## Gsuitl Commands

##### **To list the buckets**

```
gsutil ls
```

**To list all files in bucket**

```
gsutil ls gs://new-app-bucket/
```

**To list all the primary and secondary files in bucket**

```
gsutil ls gs://new-app-bucket/**
```

**To create a bucket in a particular location**

```
gsutil mb -l northamerica-northeast1 gs://storage-lab-cli
```

**To get labels about a particular bucket**

```
gsutil label get gs://new-app-bucket/
```

**To save label JSON in a particular file**

```
gsutil label get gs://new-app-bucket/ >bucketlabel.json
cat bucketlabel.json #gives the json objects of the bucket stored in file
```

**To set label to a newly created bucket**

```
gsutil label set bucketlabel.json gs://new-app-bucket/ 
```

**To set more label to a Bucket**

```
gsutil label ch -l 'extralabel:extravalue'
```

**To turn on and off the bucket versioning**

```
gsutil versioning get gs://new-bukt0/  #to get the current state of bukt
gsutil versioning set on gs://new-bukt0/ # to set versioning on
gsutil versioning get gs://new-bukt0/ #checking
```

**Check the versioning of objects**

```
gsutil cp README-cloudshell.txt gs://new-bukt0 #copy reaadme to bucket
gsutil ls gs://new-bukt0 # to list all files
gsutil ls -a gs://new-bukt0 #to list all versioned files
gsutil rm gs://new-bukt0/README-cloudshelltxt #to remove the file
gsutil ls gs://new-bukt0 #shows nothing
gsutil ls -a gs://new-bukt0 # shows a file version is available
```

**Copying all the files from one bucket to another**

```
gsutil cp gs://app-web-bucket/** gs://new-bukt0/ #copies files inside folders too but shows no files
```

**Sharing the objects in the new bucket**

```
gsutil acl ch -u AllUsers:R gs://new-bukt0/update.sh #to set file to private
```

### Google Compute Engine Setup

**List all the available Services**

```
gcloud services list 
gcloud services list -h #to get shorter version of the help
gcloud services list --enabled #to get all the enabled services
```

**Check if the compute API is enabled**

```
gcloud services list --available | grep compute #passes values on left to check in compute
gcloud services -h #toget help on the available services
```

**Create  a Vm instance**

```
gcloud compute instances create my-vm --zone=us-west1-a
```

##### Basic Syntax of Gcloud Commands

```
gcloud <global flags> <service/product> <group/area><commands> <flags> <parameters>
```

#####  Global Flags

```
--help or -h 
--project <ProjectID>
--account <Account>
--filter use a fiter
--format can choose JSON,YAML,CSV,etc
--quiet (or -q)
--zone 
--region
```

##### TO set a config Property

```
gcloud config set <property>
gcloud config get-value <property> #check the property value
gcloud config unset <property> # to unset a property
```

##### Configurations

```
can maintain a group of settings and switch between them
Most useful when using multiple projects

gcloud init #interactive workflow to set common properties in a config with 
gcloud config list #List all properties in a configuration
gcloud config configurations list #List all configurations
   IS_ACTIVE column shows which one is currently being used
   other columns list account, project, region, zone and name of the project
   
gcloud config configurations create ITS_NAME #to create a new configuration
gcloud config configurations activate ITS_NAME #to activate

	OR use for just one command with --configuration=ITS_NAME
```

#### Configuration Analogy

| **Action**      | Directory    | Configuration                                                |
| --------------- | ------------ | ------------------------------------------------------------ |
| Make New        | mkdir newdir | gcloud config configurations create <new_config>             |
| Switch To       | cd newdir    | gcloud config configurations activate <new_config>           |
| List Contents   | ls           | gcloud config list                                           |
| List Non-Active | ls ~/newdir  | gcloud --configuration=new_config or     gcloud config configurations describe <new_config> |

#### GCE In and Out

```
whoami #to return the user name
```

#### find the Host name

```
hostname #returns the host name
```

##### Return the Ip address we are using

```
curl api.ipify.org #returns the ip address of the system we are logged in
```

##### Find the machine type we need using filter

```
gcloud compute  machine-types list --filter="NAME:f1-micro AND ZONE~us-west"
```

> to get the f1 machines that are present in the us-west1 region

##### To set default region and zone

```
gcloud config set compute/zone us-west1-b
gcloud config set compute/region us-west1
```

##### Creating a new Machine type

```
gcloud compute instances create --machine-type f1-micro my-vm
```

##### Verifying the Connection to the Vm

```
ping -c 3 104.199.115.225 #external ip address
```

##### Parameters to Check

```
whoami #returns project_id
hostname #returns my-vm <vm_name>
curl api.ipify.org #returns new ip address
exit #to log out of the my-vm secure shell
```

##### Check the Public and Private keys

```
 cd .ssh #to move to ssh dir
 ls #to list all files
 cat google_compute_engine.pub #show the public keys
  head -n 10 google_compute_engine #show the private keys  
```

> the directory .ssh consists of the private key to login to the ssh but there is no private key inside, consists only of public keys. 

```
curl metadata.google.internal/computeMetadata/v1/
```

> shows missing meta data and to use the values crctly

```
curl -H "Metadata-Flavor:Google" metadata.google.internal/computeMetadata/v1/
```

##### To find the ssh keys

```
curl -H "Metadata-Flavor:Google" metadata.google.internal/computeMetadata/v1/project/attributes/ssh
```

##### To find the service accounts

```markdown
curl -H "Metadata-Flavor:Google" metadata.google.internal/computeMetadata/v1/instance/service-accounts/default/email
```

![Screenshot (454)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (454).png)

## GCE via Console Lab

> Creating a compute engine instance adding stackdriver logging to it and exporting it to 
>
> cloud storage.

#### Actions to be taken

1. Retrieve and review startup script

2. Make a new project

3.  Make logs desstination bucket

4. Enable GCE API

5. Create new GCE instance

   a. Enable scope to write to GCS

   b. Set labels (optional)

   c. set startup script

   d. Set metadata to point to logs destination bucket

6. Monitor progress

   a. check stackdriver logs

   b.check CPU graph

   c. check logs bucket

##### Worker-startup-script.sh

```bash
#! /bin/bash

#
# Echo commands as they are run, to make debugging easier.
# GCE startup script output shows up in "/var/log/syslog" .
#
set -x


#
# Stop apt-get calls from trying to bring up UI.
#
export DEBIAN_FRONTEND=noninteractive


#
# Make sure installed packages are up to date with all security patches.
#
apt-get -yq update
apt-get -yq upgrade


#
# Install Google's Stackdriver logging agent, as per
# https://cloud.google.com/logging/docs/agent/installation
#
curl -sSO https://dl.google.com/cloudagents/install-logging-agent.sh
bash install-logging-agent.sh


#
# Install and run the "stress" tool to max the CPU load for a while.
#
apt-get -yq install stress
stress -c 8 -t 120


#
# Report that we're done.
#

# Metadata should be set in the "lab-logs-bucket" attribute using the "gs://mybucketname/" format.
log_bucket_metadata_name=lab-logs-bucket
log_bucket_metadata_url="http://metadata.google.internal/computeMetadata/v1/instance/attributes/${log_bucket_metadata_name}"
worker_log_bucket=$(curl -H "Metadata-Flavor: Google" "${log_bucket_metadata_url}")

# We write a file named after this machine.
worker_log_file="machine-$(hostname)-finished.txt"
echo "Phew!  Work completed at $(date)" >"${worker_log_file}"

# And we copy that file to the bucket specified in the metadata.
echo "Copying the log file to the bucket..."
gsutil cp "${worker_log_file}" "${worker_log_bucket}"
```

##### To create the same using CMD 

```
gcloud compute instances create myvm --scopes="storage-rw,pubsub,service-control,service-management,logging-write,monitoring-write,trace" --machine-type f1-micro --zone us-east1-b --metadata startup-script-url=https://raw.githubusercontent.com/ACloudGuru/gcp-cloud-engineer/master/compute-labs/worker-startup-script.sh,lab-logs-bucket=gs://lab-logs-bucket-challenge
```

![Screenshot (453)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (453).png)

![Screenshot (455)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (455).png)

## Security

> Security by its def means ensuring proper data flow

![Screenshot (456)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (456).png)

Three kinds of security ara AuthN, AuthZ, ACC

| AuthN    | gsuite,identity,service account          |
| -------- | ---------------------------------------- |
| AuthZ    | identity hierarchy or scopes of identity |
| Accounts | stackdriver, logging, activity, bQ, GCS  |

![Screenshot (457)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (457).png)

![Screenshot (458)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (458).png)

##### Permissions

- allows u to perform a certain actions
- Each one follows the form Service.Resource.verb
- Usually corresponds to REST API methods
- Examples:
  -   pubsub.subscriptions.consume
  - pubsub.topics.publish

![Screenshot (459)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (459).png)

##### IAM Breakdown - Members & Groups

![Screenshot (460)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (460).png)

---

### IAM Policies and Permissions

![Screenshot (462)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (462).png)

---

#### Billing Account Control

![Screenshot (463)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (463).png)

---

#### Billing Account user

![Screenshot (464)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (464).png)

---

#### Billing Account Roles

![Screenshot (465)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (465).png)

---

#### SMB Centralized and delegated

![Screenshot (466)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (466).png)

![Screenshot (467)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (467).png)

---

#### CIDR Ranges

![Screenshot (468)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (468).png)

---

#### Cloud CDN

![Screenshot (469)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (469).png)

---

#### Dedicated Interconnect

![Screenshot (471)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (471).png)

---

####  CDN Interconnect

![Screenshot (472)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (472).png)

---

### AI  & Machine  Learning

#### Cloud Machine LearningEngine

![Screenshot (473)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (473).png)

---

#### Cloud Vision API

![Screenshot (474)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (474).png)

---

#### Cloud Speech API

![Screenshot (475)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (475).png)

---

#### Cloud Natural Language API

![Screenshot (476)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (476).png)



---

#### Cloud Translation API

![Screenshot (478)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (478).png)

---

#### Dialogflow

![Screenshot (479)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (479).png)

---

#### Cloud Video Intellegence API

![Screenshot (480)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (480).png)

---

#### Cloud Job Discovery

![Screenshot (481)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (481).png)

---

### Big Data

#### Big Data Lifecycle

![Screenshot (482)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (482).png)

---

#### Cloud IOT Core

![Screenshot (483)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (483).png)

---

![Screenshot (484)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (484).png)

---

#### Cloud PubSub

![Screenshot (485)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (485).png)

---

![Screenshot (486)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (486).png)

---

![Screenshot (488)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (488).png)

---

#### Cloud Dataprep

![Screenshot (489)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (489).png)

---

![Screenshot (490)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (490).png)

---

#### Cloud Dataproc

![Screenshot (491)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (491).png)

---

#### Cloud Dataflow

![Screenshot (492)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (492).png)

---

![Screenshot (493)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (493).png)

---

#### Cloud Datalab

![Screenshot (494)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (494).png)

---

#### Cloud data Studio

![Screenshot (495)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (495).png)

---



![Screenshot (497)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (497).png)

---

#### Cloud Genomics

![Screenshot (498)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (498).png)

---

![Screenshot (499)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (499).png)

---

### Identity and Access - Core Security

#### Cloud Identity & Aware Proxy

![Screenshot (500)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (500).png)

---

![Screenshot (501)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (501).png)

---

![Screenshot (502)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (502).png)

---

#### Cloud Audit Logging

![Screenshot (503)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (503).png)

---

![Screenshot (504)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (504).png)

---

### Security Monitoring - (Management & Response)

#### Cloud Armour

![Screenshot (506)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (506).png)

---

![Screenshot (507)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (507).png)

---

#### Cloud Security Scanner

![Screenshot (508)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (508).png)

---

![Screenshot (509)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (509).png)

---

#### Cloud Data Loss Prevention API (DLP)

![Screenshot (511)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (511).png)

---

![Screenshot (512)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (512).png)

---

#### Event Threat Detection (ETD)

![Screenshot (513)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (513).png)

---

![Screenshot (514)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (514).png)

---

#### Cloud Security Command Center

![Screenshot (515)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (515).png)

---

![Screenshot (516)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (516).png)

---

### Encryption Keys

#### Cloud Key Management Service(KMS)

![Screenshot (517)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (517).png)

---

![Screenshot (518)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (518).png)

---

#### Cloud hardware Security Module (HSM)

![Screenshot (519)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (519).png)

---

![Screenshot (520)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (520).png)

---

### Operations and Management

#### Google Stackdriver

![Screenshot (521)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (521).png)

---

![Screenshot (522)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (522).png)

---

#### Stackdriver Monitoring

![Screenshot (523)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (523).png)

---

![Screenshot (524)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (524).png)

---

#### Stackdriver Logging

![Screenshot (526)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (526).png)

---

![Screenshot (527)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (527).png)

---

#### Stackdriver Error Reporting

![Screenshot (528)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (528).png)

---

#### Stackdriver Trace

![Screenshot (529)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (529).png)

---

![Screenshot (530)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (530).png)

---

#### Stackdriver Debugger

![Screenshot (531)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (531).png)

---

#### Stackdriver Profiler

![Screenshot (532)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (532).png)

---

#### Cloud Deployment Manager

![Screenshot (533)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (533).png)

---

![Screenshot (534)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (534).png)

---

#### Cloud Billing API

![Screenshot (535)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (535).png)

---

![Screenshot (536)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (536).png)

---

### Development & API

#### Cloud Source Repo

![Screenshot (537)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (537).png)

---

![Screenshot (538)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (538).png)

---

#### Cloud Build

![Screenshot (539)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (539).png)

---

![Screenshot (540)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (540).png)

---

#### Container Registry (GCR)

![Screenshot (541)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (541).png)

---

![Screenshot (542)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (542).png)

---

#### Cloud Endpoints

![Screenshot (543)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (543).png)

---

![Screenshot (544)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (544).png)

---

#### Cloud Endpoints

![Screenshot (545)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (545).png)

---

#### Apigee API Platform

![Screenshot (547)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (547).png)

---

![Screenshot (548)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (548).png)

---

#### Test Lab for Android

![Screenshot (549)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (549).png)

---

![Screenshot (550)](C:\Users\Vasikrish\Pictures\Screenshots\Screenshot (550).png)

---

