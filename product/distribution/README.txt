WSO2 Analytics Hub Server, 2.0.0
================================

14 Feb 2017

Welcome to the WSO2 Analytics Hub Server, 2.0.0 release.

The WSO2 Analytics Hub version 2.0.0 is the first version of WSO2 Analytics Hub for WSO2Telco Internal Gateway

Features
========

	- Traffic Report analytics support

	- Transaction Report analytics support

	- Customer Care Report analytics support

	- Response Time Report analytics support


Installation & Running
======================
1. Download the analytics distribution ZIP file and extract the .ZIP file.
2. The path to this folder will be referred to as <ANALYTICS_HOME> throughout the documentation.
3. To start the server, go to <ANALYTICS_HOME>/bin folder and run the script as ./wso2server.sh -DportOffset=1 to start with port offset 1.
4. Wait until you see "Mgt Console URL  : https://<ANALYTICS-HOST>:<PORT>/carbon/".

For more details, see the Installation Guide

System Requirements
===================

1. Minimum memory - 2 GB
2. The Management Console requires full Javascript enablement of the Web browser

For more details see the Installation guide or,
https://docs.wso2.com/display/DAS310/Installation+Prerequisites

Including External Dependencies
===============================
For a complete guide on adding external dependencies to WSO2 Data Analytics Server & other carbon related products refer to the article:
http://wso2.org/library/knowledgebase/add-external-jar-libraries-wso2-carbon-based-products

WSO2 Analytics Hub Server Binary Distribution Directory Structure
=================================================================
     CARBON_HOME
        |-- bin <directory>
        |-- dbscripts <directory>
        |-- lib <directory>
        |-- samples <directory>
        |   |-- toolboxes <directory>
        |-- repository <directory>
        |   |-- carbonapps <directory>
        |   |-- components <directory>
        |   |-- conf <directory>
        |   |-- data <directory>
        |   |-- database <directory>
        |   |-- deployment <directory>
        |   |-- logs <directory>
        |   |-- resources <directory>
        |   |   `-- security <directory>
        |   `-- tenants <directory>
        |-- tmp <directory>
	    |-- webapp-mode <directory>
        |-- LICENSE.txt <file>
        |-- README.txt <file>
        |-- INSTALL.txt <file>
        `-- release-notes.html <file>

    - bin
      Contains various scripts .sh & .bat scripts.

    - dbscripts
      Contains the database creation & seed data population SQL scripts for
      various supported databases.

    - lib
      Contains the basic set of libraries required to startup Application Server
      in standalone mode

    - repository
      The repository where Carbon artifacts & Axis2 services and
      modules deployed in WSO2 Carbon are stored.
      In addition to this other custom deployers such as
      dataservices and axis1services are also stored.

        - carbonapps
          Carbon Application hot deployment directory.

    	- components
          Contains all OSGi related libraries and configurations.

        - conf
          Contains server configuration files. Ex: axis2.xml, carbon.xml

        - data
          Contains internal LDAP related data.

        - database
          Contains the WSO2 Registry & User Manager database.

        - deployment
          Contains server side and client side Axis2 repositories.
	      All deployment artifacts should go into this directory.

        - logs
          Contains all log files created during execution.

        - resources
          Contains additional resources that may be required.

	- tenants
	  Directory will contain relevant tenant artifacts
	  in the case of a multitenant deployment.

	- samples
          Contains the samples which describes the usage and fetures of 
	  WSO2 Data Analytics Server. This includes four samples: 

		- toolboxes
		  Complete toolboxes containing artifacts for the use cases of DAS

    - tmp
      Used for storing temporary files, and is pointed to by the
      java.io.tmpdir System property.

    - webapp-mode
      The user has the option of running WSO2 Carbon in webapp mode (hosted as a web-app in an application server).
      This directory contains files required to run Carbon in webapp mode.

    - LICENSE.txt
      Apache License 2.0 under which WSO2 Carbon is distributed.

    - README.txt
      This document.

    - INSTALL.txt
      This document contains information on installing WSO2 Application Server.

    - release-notes.html
      Release information for WSO2 Data Analytics Server 3.1.0

Secure sensitive information in carbon configuration files
==========================================================

There are sensitive information such as passwords in the carbon configuration.
You can secure them by using secure vault. Please go through following steps to
secure them with default mode.

1. Configure secure vault with default configurations by running ciphertool
	script from bin directory.

> ciphertool.sh -Dconfigure   (in UNIX)

This script would do following configurations that you need to do by manually

(i) Replaces sensitive elements in configuration files,  that have been defined in
		 cipher-tool.properties, with alias token values.
(ii) Encrypts plain text password which is defined in cipher-text.properties file.
(iii) Updates secret-conf.properties file with default keystore and callback class.

cipher-tool.properties, cipher-text.properties and secret-conf.properties files
			can be found at repository/conf/security directory.

2. Start server by running wso2server script from bin directory

> wso2server.sh   (in UNIX)

By default mode, it would ask you to enter the master password
(By default, master password is the password of carbon keystore and private key)

3. Change any password by running ciphertool script from bin directory.

> ciphertool -Dchange  (in UNIX)

For more details see
https://docs.wso2.com/display/Carbon445/Securing+Passwords+in+Configuration+Files


Training
========

WSO2.Telco Inc. offers a variety of professional Training Programs, including
training on general Web services as well as WSO2 Data Analytics Server and number of 
other products.

For additional support information please refer to
http://wso2.com/training/


Support
=======

We are committed to ensuring that your enterprise middleware deployment is completely supported
from evaluation to production. Our unique approach ensures that all support leverages our open
development methodology and is provided by the very same engineers who build the technology.

For additional support information please refer to http://wso2.com/support/

For more information on WSO2 Application Server, visit the WSO2 Oxygen Tank (http://wso2.org)

Crypto Notice
=============

   This distribution includes cryptographic software.  The country in
   which you currently reside may have restrictions on the import,
   possession, use, and/or re-export to another country, of
   encryption software.  BEFORE using any encryption software, please
   check your country's laws, regulations and policies concerning the
   import, possession, or use, and re-export of encryption software, to
   see if this is permitted.  See <http://www.wassenaar.org/> for more
   information.

   The U.S. Government Department of Commerce, Bureau of Industry and
   Security (BIS), has classified this software as Export Commodity
   Control Number (ECCN) 5D002.C.1, which includes information security
   software using or performing cryptographic functions with asymmetric
   algorithms.  The form and manner of this Apache Software Foundation
   distribution makes it eligible for export under the License Exception
   ENC Technology Software Unrestricted (TSU) exception (see the BIS
   Export Administration Regulations, Section 740.13) for both object
   code and source code.

   The following provides more details on the included cryptographic
   software:

   Apacge Rampart   : http://ws.apache.org/rampart/
   Apache WSS4J     : http://ws.apache.org/wss4j/
   Apache Santuario : http://santuario.apache.org/
   Bouncycastle     : http://www.bouncycastle.org/

For further details, see the WSO2 Carbon documentation at
http://docs.wso2telco.com/display/HG/Analytics+-+Internal+Gateway

---------------------------------------------------------------------------
(c)  2017, WSO2.Telco Inc.

README.txt
Displaying README.txt.
