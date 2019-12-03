
```shell script
mvn deploy:deploy-file -Durl=file:///home/tdgunes/IdeaProjects/group1/repo/ \
-Dfile=./deps/SCPSolver.jar -DgroupId=org.hplanatscher -DartifactId=scpsolver \
-Dversion=1.0 -Dpackaging=jar
```