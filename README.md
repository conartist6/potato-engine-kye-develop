## Potato Engine Kye Develop

This project makes it possible to develop the kye game engine concurrently with the Kye game. You need this project ONLY if you are planning to work on developing potato-engine.

It works correctly only when you check out those two repositories into folders in the root directory of this repository.

To use this repository correctly, here are the basic commands. **Note that if you probably do not want to run these commands exactly:** You will save time by forking potato-engine and kye first, and using the forked respository's cloning URL (it probably starts with `git:`) with the clone command in order to check out your copy of the sources you plan to change.

```
git clone https://github.com/conartist6/potato-engine-kye-develop.git

cd potato-engine-kye-develop

git clone https://github.com/conartist6/kye.git

git clone https://github.com/conartist6/potato-engine.git
```

### What's going on

This repository exists so that those two pieces of software can be developed in tandem. It is its own repository to capture the root yarn.lock file which allows yarn to avoid certain classes of errors or mistakes during development. It also serves to host scripts and documentation about how to do such development.

This project tricks a create-react-app project (Kye) into think it's part of a monorepo which also includes the potato-engine. In fact more than one repository is involved.

The monorepo trick is critical because create-react-app treats monorepos very specially, by treating code in other monorepo packages as if it were in-project code, meaning that in addition to being bundled like all package code, it will be transpiled, linted, and watched as if it were project sources. You also get error messages in your development server if (when) you foul up any of the engine sources.
