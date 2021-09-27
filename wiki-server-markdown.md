# Serve markdown files as a web site

## Using Raneto

```console
# setup server
cd $APPS
git clone git@github.com:gilbitron/Raneto.git wiki.gists
cd wiki.gists
mv ./example/content ./example/content.old
git clone git@github.com:mpab/gists.git ./example/content
yarn install

```

```console
# run server
cd $APPS
cd ./wiki.gists
pushd ./example/content
git pull
popd
yarn start_win

```

## Using Gollum (TODO)
