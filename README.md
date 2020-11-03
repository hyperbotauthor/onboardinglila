# onboardinglila

onboarding lila ( https://github.com/ornicar/lila , https://github.com/ornicar/lila/wiki/Lichess-Development-Onboarding )

sign up to https://www.goorm.io/

update Ubuntu

```
sudo apt update && sudo apt upgrade -y
```

create a Scala container

install yarn ( https://linuxize.com/post/how-to-install-yarn-on-ubuntu-18-04/ ):

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update
sudo apt install yarn
yarn --version
```

clone lila and build the ui

```
git clone --recursive https://github.com/ornicar/lila.git
cd lila
./ui/build # builds the CSS and JS
```
