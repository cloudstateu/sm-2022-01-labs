# What is Azure App Service?
Azure provides Azure App Service as a platform as a service (PaaS) for running Tomcat. It features a Windows and Linux environment, security, load balancing, autoscaling, and DevOps integration. You can leave the OS and Tomcat management to Azure and concentrate on building applications.

## Get sample JSF applications
To deploy a Java web application, you can get a PrimeFaces JavaServer Faces (JSF) web application from GitHub as shown here.

` git clone https://github.com/yoshioterada/Deploy-PrimeFaces-JSF-Web-App-on-Tomcat-9.0 `

## Maven Plugin for Azure App Service
Microsoft provides the Maven Plugin for Azure App Service to make it easier for Java developers to deploy applications to Azure. By using this plug-in, you can easily configure and deploy your application to Azure. Execute the following command to use Maven Plugin for Azure App Service.

Configure the Maven Plugin for Azure App Service
To configure the Maven Plugin for Azure App Service, execute the following command:

` mvn com.microsoft.azure:azure-webapp-maven-plugin:1.12.0:config `

After the command, some questions will appear at the prompt, so enter and select the appropriate items and set them. Enter the following options:

` Item:       Input value `

`Subscription: Choose the right subscription `

`Define value for OS	1:              Linux`

`Define value for pricing tier:	P1v2`

`Define value for Java version	1: Java 8 or 2: Java 11 `

`Define value for runtime stack	3: TOMCAT 9.0`

`Confirm (Y/N):	Y `

You'll see a new section in the <plugins> section in your pom.xml file.

If you want to change the resource group name, instance name, and deployment location, change [resourceGroup], [appName], and [region].

# Compile and deploy to Azure App Service
Now that the settings for deploying to Azure App Service are complete, compile the source code again.   

`mvn clean package`

Once compiled, use the Maven Plugin for Azure Web Apps command to deploy your application. Execute the following command:

`mvn azure-webapp:deploy`

The public URL of the deployed application is displayed in Successfully deployed the artifact to. Access your URL with a browser.

`https://azure-javaweb-app-1601463451101.azurewebsites.net`

# Confirm the log stream from the command line
To access the log stream, execute the following CLI command:

`az webapp log tail -g azure-javaweb-app -n azure-javaweb-app-1601463451101`
