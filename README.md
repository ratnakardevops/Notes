# Notes

Maven installation On a RHEL 7 Server

https://www.tecmint.com/install-apache-maven-on-centos-7/	(Working one)

yum install -y java-1.8.0-openjdk-devel
java -version

cd /usr/local/src
wget http://www-us.apache.org/dist/maven/maven-3/3.5.4/binaries/apache-maven-3.5.4-bin.tar.gz
tar -xf apache-maven-3.5.4-bin.tar.gz
mv apache-maven-3.5.4/ apache-maven/ 
cd /etc/profile.d/
vi maven.sh
	# Apache Maven Environment Variables
	# MAVEN_HOME for Maven 1 - M2_HOME for Maven 2
	export M2_HOME=/usr/local/src/apache-maven
	export PATH=${M2_HOME}/bin:${PATH}
chmod +x maven.sh
source /etc/profile.d/maven.sh
mvn --version

================================================================================================

$mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
$cd my-app
$git init
$git add .
git config --global user.name ratnakar
git config --global user.email rgangapa@hotmail.com
git commit -m "first commit"
git push origin  master 
 It will fail because remote was not set yet
 So create one repo in GUI
git remote add origin https://github.com/ratnakardevops/my-app.git
git push origin master
 It will ask username and password
 We can congiure keys if we don't want to pass username and password
 $ssh-keygen
 copy the public key to GitHub(Settings -> SSH and GPG Keys -> paste public key in SSH Section


git remote add origin git@github.com:ratnakardevops/my-app.git
 it will fail because already remote was added
git remote -v
git remote rm origin
git remote add origin git@github.com:ratnakardevops/my-app.git
git push origin  master 
 It will fail if we have any files on remote GitHub like README.md file
 So we have pull those files
git pull git@github.com:ratnakardevops/my-app.git master
