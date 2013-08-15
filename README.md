# Gradle 1.7 OpenShift Quickstart #

This currently does not work because of http://issues.gradle.org/browse/GRADLE-2871. Gradle 1.6 works fine on OpenShift and you can use this repository https://github.com/shekhargulati/gradle-openshift-quickstart. I have also written detailed blog on this as well https://www.openshift.com/blogs/run-gradle-builds-on-openshift.

To reproduce the issue follow following steps mentioned below.


## Step 1 : Create OpenShift Tomcat 7 application #

```
$ rhc app create gradledemo tomcat-7
```

## Step 2: Pull the source code form github##

```
$ cd gradledemo
$ git rm -rf src/ pom.xml
$ git commit -am "deleted template source code"
$ git remote add upstream -m master https://github.com/shekhargulati/gradle-1.7-openshift-quickstart.git
$ git pull -s recursive -X theirs upstream master
```

## Step 3 : Push the source code ##

```
$ git push
```
