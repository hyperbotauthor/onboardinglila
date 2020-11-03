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

install sbt ( https://www.techrepublic.com/article/how-to-install-sbt-on-ubuntu-for-scala-and-java-projects/ , https://www.scala-sbt.org/release/docs/Installing-sbt-on-Linux.html )

```
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install default-jdk -y
wget www.scala-lang.org/files/archive/scala-2.13.0.deb
sudo dpkg -i scala*.deb

echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
sudo apt-get update
sudo apt-get install sbt
sbt test
```
