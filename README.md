# onboardinglila

https://github.com/ornicar/lila/wiki/Lichess-Development-Onboarding

sign up to https://www.goorm.io/

starting from a Scala container and trying to update Ubuntu ( https://www.cyberciti.biz/faq/upgrade-ubuntu-18-04-to-20-04-lts-using-command-line/ ) like

```
sudo apt update && sudo apt upgrade -y
sudo reboot command
sudo apt --purge autoremove
sudo apt install update-manager-core
sudo do-release-upgrade
lsb_release -a
```

won't work

instead create a Node.js container, which comes with the right Ubuntu version

update Node.js version

```
npm cache clean -f
npm install -g n
n latest
node -v
```

install yarn ( https://linuxize.com/post/how-to-install-yarn-on-ubuntu-18-04/ ):

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update
sudo apt install yarn
yarn --version
```

clone the repo ( https://github.com/ornicar/lila )

```
git clone --recursive https://github.com/ornicar/lila.git
```

build the ui

```
cd lila
./ui/build # builds the CSS and JS
```

install sbt ( http://www.codebind.com/linux-tutorials/install-scala-sbt-java-ubuntu-18-04-lts-linux/ )

```
sudo add-apt-repository ppa:webupd8team/java
sudo apt update
sudo apt install oracle-java8-installer
sudo apt install oracle-java8-set-default
javac -version
echo "export PATH=/usr/local/anaconda2/bin:$PATH" >> /etc/bash.bashrc
echo "export JAVA_HOME=/usr/lib/jvm/java-8-oracle/" >> /etc/bash.bashrc
echo "export PATH=$PATH:$JAVA_HOME/bin" >> /etc/bash.bashrc
sudo apt-get remove scala-library scala
sudo wget www.scala-lang.org/files/archive/scala-2.11.8.deb
sudo dpkg -i scala-2.11.8.deb
scala -version
echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
sudo apt-get update
sudo apt-get install sbt
```
