 CI/CD Pipeline with GitHub, Jenkins, Maven, and Tomcat

Files:
`pom.xml` → Maven build configuration
 `Jenkinsfile` → Jenkins pipeline definition
 `src/main/webapp/index.jsp` → Sample Java web app

Steps to Run:
1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/devops_projects.git
   cd devops_projects/cicd_project
   ```

2. Build with Maven:
   ```bash
   mvn clean package
   ```

3. Deploy WAR file manually to Tomcat:
   Copy `target/demo-app.war` to Tomcat's `webapps/` folder.

4. Jenkins Pipeline:
   - Configure Maven & JDK in Jenkins Global Tools.
   - Set up a Jenkins pipeline using the `Jenkinsfile`.
   - Trigger build on GitHub commits (enable Webhooks).

