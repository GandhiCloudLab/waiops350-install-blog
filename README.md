# IBM Cloud Pak for Watson AIOps 3.5.0 Installation

This document explains about Installing IBM Watson AIOps 3.5.0 on IBM ROKS by using the installation scripts. 

The following 3 deployments are possible using this script and to be installed in different clusters.

- IBM Cloud Pak for Watson AIOps AI Manager 3.5.0
- IBM Cloud Pak for Watson AIOps Event Manager 1.6.6 (powered by IBM® Netcool® Operations Insight®)
- IBM Cloud Pak for Watson AIOps Infrastructure Automation 3.5.0

Installation scripts are available [here](.). Download and keep the files local.

This script uses `ibmc-file-gold-gid` strorage class available in ROKS as a storage option. By changing the storage-class in the `00-config.sh` file, the same script can be used to install on other Openshift as well.

## 1. Installing AI Manager

Installation scripts are available here [01-install-aimgr-on-roks/files](./01-install-aimgr-on-roks/files).

### 1.1 Update Properties

Update the below properties in `01-install-aimgr-on-roks/files/00-config.sh` file .

#### Entitlement Key
```
export ENTITLEMENT_KEY=eyJhbG...........................e4Zog
```

#### Storage Class (if required)
```
export AI_MANAGER_STORAGE_CLASS=ibmc-file-gold-gid
export AI_MANAGER_STORAGE_CLASS_LARGE_BLOCK=ibmc-file-gold-gid
```

### 1.2. Login to OCP Cluster

Login to OCP cluster using  `oc login` command .

### 1.3. Run the install script

Goto the `01-install-aimgr-on-roks/files` folder and Run the install script as like below.

```
cd 01-install-aimgr-on-roks/files
sh 10-install.sh
```

- It would take around 1hr to complete the istallation. 
- By default the installation is done on the namespace `cp4waiops`
- Keep checking the logs for the status. 
- The same script can be run again and again if the install stopped for any reason.

### 1.4. Output
 
The installation would be completed and the output could be like this.

```
=====================================================================================================
URL : https://cpd-cp4waiops.aaaaaaaa.ams03.containers.appdomain.cloud
USER: admin
PASSWORD: EpU2m........................jYUz
=====================================================================================================

```

You can use this to login into the WAIOps Console.

### 1.5. Printing URL, Usr and Pwd

To get the AIMgr URL, user and password anytime after AIMgr install, you can run the below command. This will print the output as like above.

```
cd 01-install-aimgr-on-roks/files
sh 19-print-url-usr-pwd.sh
```

### Reference

The script is based out of https://www.ibm.com/docs/en/cloud-paks/cloud-pak-watson-aiops/3.5.0?topic=manager-starter-installation-cli


### 2. Installing Event Manager

Installation scripts are available here [02-install-eventmgr-on-roks/files](./02-install-eventmgr-on-roks/files).

### 2.1 Update Properties

Update the below properties in `02-install-eventmgr-on-roks/files/00-config.sh` file .

#### Entitlement Key
```
export ENTITLEMENT_KEY=eyJhbG...........................e4Zog
```

#### Storage Class (if required)
```
export EVENT_MANAGER_STORAGE_CLASS=ibmc-file-gold-gid
```

### 2.2. Login to OCP Cluster

Login to OCP cluster using  `oc login` command .

### 2.3. Run the install script

Goto the `02-install-eventmgr-on-roks/files` folder and Run the install script as like below.

```
cd 02-install-eventmgr-on-roks/files
sh 10-install.sh
```

- It would take around 30 to 50 minutes to complete the istallation. 
- By default the installation is done on the namespace `cp4waiops-emgr`
- Keep checking the logs for the status. 
- The same script can be run again and again if the install stopped for any reason.

### 1.4. Output
 
The installation would be completed and the output could be like this.

```
=====================================================================================================
URL : https://netcool-evtmanager.aaaaaaaa.appdomain.cloud
USER: smadmin
PASSWORD: rJ........u
=====================================================================================================

```

You can use this to login into the WAIOps Console.

### 1.5. Printing URL, Usr and Pwd

To get the EventManager URL, user and password anytime after EventManager install, you can run the below command. This will print the output as like above.

```
cd 02-install-eventmgr-on-roks/files
sh 19-print-url-usr-pwd.sh
```

### Reference

The script is based out of https://www.ibm.com/docs/en/cloud-paks/cloud-pak-watson-aiops/3.5.0?topic=em-starter-installation-cli


### 3.Installing Infra Automation


Installation scripts are available here [03-install-infra-automation-on-roks/files](./03-install-infra-automation-on-roks/files).

### 3.1 Update Properties

Update the below properties in `03-install-infra-automation-on-roks/files/00-config.sh` file .

#### Entitlement Key
```
export ENTITLEMENT_KEY=eyJhbG...........................e4Zog
```

#### LDAP User Group
```
export YOUR_LDAP_USER_GROUP=IM_GROUP
```

#### Storage Class (if required)
```
export AI_MANAGER_STORAGE_CLASS=ibmc-file-gold-gid
export AI_MANAGER_STORAGE_CLASS_LARGE_BLOCK=ibmc-file-gold-gid
```

### 3.2. Login to OCP Cluster

Login to OCP cluster using  `oc login` command .

### 3.3. Run the install script

Goto the `03-install-infra-automation-on-roks/files` folder and Run the install script as like below.

```
cd 03-install-infra-automation-on-roks/files
sh 10-install.sh
```

- It would take around 1hr to complete the istallation. 
- By default the installation is done on the namespace `cp4waiops`
- Keep checking the logs for the status. 
- The same script can be run again and again if the install stopped for any reason.

### 3.4. Output
 
The installation would be completed and the output could be like this.

```
=====================================================================================================
URL : https://cpd-cp4waiops.aaaaaaaa.ams03.containers.appdomain.cloud
USER: admin
PASSWORD: EpU2m........................jYUz
=====================================================================================================

```

You can use this to login into the WAIOps Console.

### 3.5. Printing URL, Usr and Pwd

To get the Infra Automation URL, user and password anytime after Infra Automation install, you can run the below command. This will print the output as like above.

```
cd 03-install-infra-automation-on-roks/files
sh 19-print-url-usr-pwd.sh
```

### Reference

- Online installation of Infrastructure Automation
https://www.ibm.com/docs/en/cloud-paks/cloud-pak-watson-aiops/3.5.0?topic=automation-online-installation
## Note

This script can be installed on top existing IBM Watson AIOps AI Manager 3.5.0 instance.

