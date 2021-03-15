---
title: "Cloud Foundry"
menuTitle: Cloud Foundry
weight: 1
---

- How to login to CF using cli : `cf login -a <https://api.address> -u <username> -p <password>`

  - To bypass ssl validation during login : `cf login -a <https://api.address> -u <username> -p <password> --skip-ssl-validation`
  
- For switching between space and organization : 

  ```
  cf target -s <space-name>
  cf target -o <organization-name>
  ```

- To review current target configuration : `cf target`

- How to push an application to cf
  - Navigate to code directory and execute : 
  `cf push <app name> --random-route --no-start -m <memory allocation> -i <number of instances>`
  - This will push an app with given name and memory on a random route and scale app to `i` instances
  - __NOTE__ : `--no-start` can be added when app should just be packaged and not started. This is especially usefull when app is required to be bound to services for it to work properly. This way a restage or restart of app is not required
  - `-p <path to jar>` can be added to push a specific jar as app
  - For starting application: `cf start <app name>`

- How to view events : `cf events <appname>`

- For Tailing logs : `cf logs <app name>`
  - add `--recent` for most recent logs


- For getting all detailed configuration of apps deployed in cf space and org 
  - Target the space and org
  - `cf curl "v2/apps"`
  - `cf curl "v2/apps/<app metadata.guid>/stats` For detailed stats of the app
  - For more details : http://apidocs.cloudfoundry.org 

- For scaling application : `cf scale <appname> -m <memory allocation> -i <integer - number of instances>` 
  - scaling memory requires restart of application and hence can cause downtime
  - scaling instance doesnt require restart
  - _PCF_ auto recovers failing instances of an application


- For creating new service from Marketplace: 
  ```
  cf marketplace
  cf create-service <marketplace place service name> <plan> <user service name>  
  cf bind-service <appaname> <user service name>
  cf restart <appname>
  ```

- Converting the app into user provided service : `cf create-user-provided-service <service name/app name> -p <uri>`

- Manifest can be used to define the bound services, memory, instances, package path location etc 
  - For creating a manifest from cf cli: `cf create-app-manifest <app name> -p <file name >` 
  - sample filename = ./manifest.yml
  
- For creating log drain service, we need the log drain url of service being used, like splunk, papertrail or any logging service
  - to bind a log drain service `cf create-user-provided-service <log drain service name> -l syslog://<log drain url>`
  
- Blue-Green Deployments
  - For finding the correct routes of app `cf routes`
  - Push the app with different name and different subdomain : `cf push <name v2> -p <package path> -m<memory> -n<subdomain different than current prod> --no-start`
  - bind to required services
  - map new route `cf map-route <name v2> <domain> -n <subdomain prod one>`
  - For removing old version : `cf unmap-route <name v1> <domaine> -n <subdomain>`


__PCF NOTE__
```
Metrics : http://docs.pivotal.io/pcf-metrics/1-3/using.html```

*To provide particular buildpack during push* 
cf push <appname> -p <package location> -b <buildpack location>

*For setting JRE version* 
cf set-env <appname> JBP_CONFIG_OPEN_JDK_JRE "<jre: < version: 1.8.0_45 >>"
We need to restage app after this change 
cf restage <appname>

*For pushing service broker* 
cf push <app name> ... 

cf set-env <app name> SERVICE_ID <unique id>
cf set-env <app name> SERVICE_NAME <unique Name>
cf set-env <app name> PLAN_ID <plan name>


Start app 
Register the service broker
cf create-service-broker <unique broker name> <username> <passowrd> <url> --space-scoper



*******************************************************************
```Cloud Metrics 

cf list-plugin-repos 
--> to List the available plugins - CF-Community should come up 

to install cf TOP plugin - powerful tool for health monitoring. 
cf install-plugin -r CF-Community "top" 
```

## CF Plugins 

[do-all](https://github.com/ECSTeam/do-all)
```
This plugin can run any cli command for all apps deployed in the particular targetted space.
To install : cf install-plugin do-all -r "CF-Community" 
To run : cf do-all COMMAND ARGS (example : cf do-all restage <> - where <> signifies all applications in targetted space)
```

[top](https://github.com/ECSTeam/cloudfoundry-top-plugin)
```
The best monitoring plugin out there. Shows an interactive view to monitor complete health of Cloud Foundry orgs,space,apps and routes
To install : cf install-plugin -r CF-Community "top"
To run : cf top
```
