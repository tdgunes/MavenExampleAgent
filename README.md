
### ExampleAgent with Maven Dependencies

- For a starting point, download this project. 

- You need to execute a maven deploy command for every local dependencies (i.e. libraries that you only have the jar files. Optionally, place them to the `deps` folder.) For example, to have `SCPSolver.jar` in your agent (replace <ProjectDir> with a correct path of the repo folder):
```shell script
mvn deploy:deploy-file -Durl=file://<ProjectDir>/repo/ \
-Dfile=./deps/SCPSolver.jar -DgroupId=org.hplanatscher -DartifactId=scpsolver \
-Dversion=1.0 -Dpackaging=jar
```

- Regarding dependencies that can be found in Maven's central repository, you need to add them to pom.xml file. (For example, this project is using Google Common's package from the central repository.)

- Genius is added to the project a system dependency, which makes the jar package of Genius, not included to the final jar file.

- To create the final jar file, execute:

```shell script
mvn clean compile assembly:single
```

- The jar file of your agent will be placed in: `target/group1-final-jar-with-dependencies.jar`

- To double check, unzip your the final jar and have a look if the dependencies are copied correctly.