---
title: Schema
layout:  null
tab: true
order: 1
tags: scan_it
---

##  The Format

The file ("scan_it.yaml") is a YAML configuration file that will contain the necessary specification and configuration to facilitate your application consumption by both the security team and/or the security automation tools. In this document, we intend to cover:
 
1.  Why YAML
    
2.  The Configuration File
    
3.  Reference
    
4.  Examples
    
 
By the end of this document, we are hoping you can easily understand and create the simple but useful scan_it file for your application. Below a sample scan_it.yaml file:
 
```
 
version: 0.1
about:
 generic:
  name: "super_uber_app"
  id: 123456
 stack:
  languages:
   - "python:3.7"
   - "pl/sql"

source:
 type: "git"
 repo: "https://github.com/OWASP/www-project-scan-it"
 repo_user: $SVC_USER_NAME 
 repo_pwd: $SVC_PWD #never add your creds here, just a placeholder
 paths:
  - 
   path: '*'
   ignore: 
    - '*.xml'
    - '*.dll'
    - 'test*.py'
    - '/src/test'
   contact:
    - email: team_manager@company_example.com
   ticket:
    type: 
     - email
     - jira

  - 
   path: '/src/apps'
   ignore: this_file.py
  
  - 
   path: '/src/apps/super_awesomeCode/bpmEdit.py'
   contact:
      - email: amazing_dev@company_example.com
 
 ```
 
  
 
## Why YAML
 
  
 
YAML (YAML Ain’t Markup Language) is a user friendly syntax for writing software configuration and specifications. There is a lot of internet content over the pros and cons on the most widespread configuration file formats such as XML, JSON and YAML. Some of the main reasons why we selected the YAML file for this project are:
 
-   YAML is user friendly - easy to read and understand by humans
    
-   Very widespread and good programming language support.
    
-   Support for comments - which is not valid in JSON
 
