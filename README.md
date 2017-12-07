# Jenkins Job DSL Rest Example 

An example [Job DSL](https://github.com/jenkinsci/job-dsl-plugin) project that shows how to make Job DSL updates via the Jenkins REST API. 

The project layout is based on the [Job DSL Gradle Example](https://github.com/sheehan/job-dsl-gradle-example).

## REST API Runner

Note: the REST API Runner does not work with [Automatically Generated DSL](https://github.com/jenkinsci/job-dsl-plugin/wiki/Automatically-Generated-DSL). 

A gradle task is configured that can be used to create/update jobs via the Jenkins REST API, if desired. Normally
a seed job is used to keep jobs in sync with the DSL, but this runner might be useful if you'd rather process the
DSL outside of the Jenkins environment or if you want to create the seed job from a DSL script.

```./gradlew rest -Dpattern=<pattern> -DbaseUrl=<baseUrl> [-Dusername=<username>] [-Dpassword=<password>]```

* `pattern` - ant-style path pattern of files to include. E.g. `src/jobs/*.groovy`
* `baseUrl` - base URL of Jenkins server
* `username` - Jenkins username, if secured
* `password` - Jenkins password or token, if secured
