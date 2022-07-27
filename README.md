```shell
➜  gradleissue16756 gradle wrapper --gradle-version 6.7.1
> Task :wrapper
> Task :lib:wrapper

BUILD SUCCESSFUL in 328ms
2 actionable tasks: 2 executed


➜  gradleissue16756 ./gradlew testissuetask --console plain
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:compileJava
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:processResources NO-SOURCE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:classes
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:jar
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:assemble
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:check
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:build
> Task :lib:testissuetask

BUILD SUCCESSFUL in 415ms
1 actionable task: 1 executed
 -----------------------------------------------------------------------
➜  gradleissue16756 git:(master) ✗ gradle wrapper --gradle-version 6.8    
> Task :wrapper
> Task :lib:wrapper

BUILD SUCCESSFUL in 563ms
2 actionable tasks: 2 executed

➜  gradleissue16756 git:(master) ✗ ./gradlew testissuetask --console plain
Starting a Gradle Daemon (subsequent builds will be faster)
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:compileJava
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:processResources NO-SOURCE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:classes
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:jar
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:assemble
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:compileTestJava NO-SOURCE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:processTestResources NO-SOURCE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:testClasses UP-TO-DATE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:test NO-SOURCE
// ^ this should not happen. the test task was excluded
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:check UP-TO-DATE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:build
> Task :lib:testissuetask

BUILD SUCCESSFUL in 33s
1 actionable task: 1 executed
➜  gradleissue16756 git:(master) ✗ gradle wrapper --gradle-version 6.7.1
> Task :wrapper
> Task :lib:wrapper

BUILD SUCCESSFUL in 411ms
2 actionable tasks: 2 executed

 -----------------------------------------------------------------------
➜  gradleissue16756 gradle wrapper --gradle-version 7.5
> Task :wrapper UP-TO-DATE
> Task :lib:wrapper UP-TO-DATE

BUILD SUCCESSFUL in 449ms
2 actionable tasks: 2 up-to-date


➜  gradleissue16756 ./gradlew testissuetask --console plain
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:compileJava
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:processResources NO-SOURCE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:classes
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:jar
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:assemble
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:compileTestJava NO-SOURCE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:processTestResources NO-SOURCE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:testClasses UP-TO-DATE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:test NO-SOURCE
// ^ this should not happen. the test task was excluded
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:check UP-TO-DATE
> Task :/{path_of_project}/opensoucetests/gradleissue16756/lib/lib/build.gradle:lib:build
> Task :lib:testissuetask

BUILD SUCCESSFUL in 412ms
1 actionable task: 1 executed
```