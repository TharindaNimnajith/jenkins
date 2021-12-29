In the Jenkins web interface, go to:

`Manage Jenkins` -> `Global Tool Configuration` -> `Maven installations` -> `Add Maven`.

Give your Maven installation a name and check the option to `Install automatically`.

## Setting up the Jenkins Job
Create a freestyle job and configure it as follows:

1. Under `Source Code Management`, select `Git` and enter the following URL:
    ```
    https://github.com/managedkaos/apache-maven-hello-world
    ```
2. **MAKE SURE TO SET THE `Branch Specifier` to `*/03_01`**.
3. Add a build step using `Invoke Top-Level Maven Target`.
4. Select the Maven version you configured in the previous step.
5. For the goal, enter `package`.
6. MacOS/Linux: Add a build step using the `Execute shell` build step and enter:  
    ```
    java -cp target/hello-1.0-SNAPSHOT.jar com.learningjenkins.App
    ```
   Windows: Add a new build step using the `Execute Windows batch command` and enter:
    ```
    java -cp target/hello-1.0-SNAPSHOT.jar com.learningjenkins.App
    ```
7. Save the job and start the build.
