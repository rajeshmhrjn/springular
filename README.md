# springular
Spring Boot and Angular Integration(running on the same server)

This project was developed on a machine with:
JDK 11, Node v14.17.6, npm 6.14.15, Gradle 7, IntelliJ IDEA 2021.1.2 (Community Edition)

After you've imported the project in your IDE refresh the gradle project to download the required dependencies

##### FOR DEVELOPMENT

1) Set the following property in application.properties
**spring.profiles.active=dev**

2) In application-dev.properties
set the property **spring.resources.static-locations** to the "absolute path of the directory where angular creates the build files"
Example- spring.resources.static-locations=file:///C:/practice_projects/springular/webModule/dist/webModule

3) Run the angular build in **watch** mode so that any UI file changes are immediately build by angular and available on the browser with a page refresh
To do this execute "**npm run watch**" from the directory(springular/webModule) where your package.json resides

4) To debug the java app, debug the **bootRun** gradle task under springular/Tasks/application/bootRun task from your gradle tab in IntelliJ

##### TO CREATE AN EXECUTABLE JAR OF THIS PROJECT

1) Set the **spring.profiles.active** to your desired environment in your **application.properties**

2) Execute "**gradlew clean build**" from the root directory(springular/). This will:
    
    a) trigger angular build which will create the **springular/webModule/dist/webModule** directory and copy the build files there.
    
    b) delete the contents of static directory in **springular/appModule/src/main/resources/static**.
    
    c) copy the content of "**springular/webModule/dist/webModule**" To **springular/appModule/src/main/resources/static**
    
    d) create the jar file with the static files under springular/appModule/build/libs





