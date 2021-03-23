# Setup guide

## nvm

- install

```bash
wget -O install_nvm.sh https://raw.githubusercontent.com/creationix/nvm/master/install.sh
bash install_nvm.sh
```

## nvm __windows__

<https://github.com/coreybutler/nvm-windows#node-version-manager-nvm-for-windows>

There is an install script, but there are only a few relevant settings

- install

```cmd
setx NVM_HOME "D:\Apps\nvm"
setx NVM_SYMLINK "D:\Apps\nodejs"
setx PATH "%PATH%;%NVM_HOME%;%NVM_SYMLINK%"
```

**PREREQUISITE** install node from an elevated command prompt (also works in bash)

- version

```bash
node --version
```

- test

```bash
command -v node
```

- test fail

if the nvm setting changes do not work, add the following line after the NVM section in $HOME/.$SHELLrc

```bash
export NVM_DIR="$HOME/.nvm"
...
...
. $NVM_DIR/nvm.sh
```

## node (and npm)

- install node (stable)

```bash
nvm install stable
```

- test node

```bash
command -v node
```

- test npm

```bash
command -v npm
```

- list nvm installations

```bash
nvm list
```

- select nvm stable version

```bash
nvm use stable
```

- upgrade npm for current version

```bash
cd ~/.nvm/versions/node/$(node -v)/lib && npm install npm
```

## yarn

**PREREQUISITE** install node and nvm

- install

```console
npm install -g yarn
yarn set version latest
```

## create applications from templates

- react with typescript

```bash
npx create-react-app my-app --template typescript
# OR
yarn create react-app my-app --template typescript
```

- react native with typescript

```bash
npx react-native init my-app --template react-native-template-typescript
npx create-react-native-app my-app --template-with-typescript <-->
```

- add windows target & run

```bash
npx react-native-windows-init --overwrite
npx react-native run-windows
```

- list of templates

<https://www.npmjs.com/search?q=cra-template-*>
