#安装JAVA
```
1)Remove OpenJDK first if installed by this command:

sudo apt-get purge openjdk*

2)add the Webupd8 Team PPA repository and then reload the packages:

sudo add-apt-repository ppa:webupd8team/java

sudo apt-get update

3)install Oracle Java:

sudo apt-get install oracle-java7-installer

Or, change the number 7 to 6 or 8 to install Java6 or Java8.

4) After installation, run command to check if it was successful:

java -version

It should return something like this:

java version "1.7.0_17"
Java(TM) SE Runtime Environment (build 1.7.0_17-b02)
Java HotSpot(TM) Client VM (build 23.7-b01, mixed mode)

5)(Optional) To remove Oracle Java, run this command in terminal (change the package name to yours):

sudo apt-get remove oracle-java7-installer
```
