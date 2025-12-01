# Introduction

Teacher said that tab navigation is similar to stack navigation.


# Bottom tabs navigation


## Material bottom

![material bottom tabs navigation - illustration](images/material-bottom-tabs-navigation--illustration.png)


# Material top

![material top tabs navigation - illustration](images/material-bottom-tabs-navigation--illustration.png)


# Installation

Teacher instructed us to run the following command **after** initialized an application (to install the navigation **bottom**-tabs):

```
npm install @react-navigation/botton-tabs
```

To setup an application please see [this repository](https://github.com/andreterceiro/dio-mobile-meu-tudo--working-with-stack-navigation-in-react-native).

Teacher said that he do slightly different from the documentation. From the documentation:

![part of the documentation - bottom tabs](images/part-of-the-documentation--bottom-tabs.png)

Teacher created a file routes/bottom-tabs-routes.tsx (with a slightly typo - botom).


# Most simple example

Teacher said that this is the most simple example of this type of navigation:

![simplest example](images/simplest-example.png)


# Test apps

I also explored [the documentation](https://reactnavigation.org/docs/bottom-tab-navigator/) and created 2 test apps. First, tests/01/botton-tabs, I created with the command:

```
npx create-expo-app botttom-tabs
```

For the second app (tests/02/bottom), I used the parameter -t and selected the template "blank (Typescript)":

```
npx create-expo-app botttom -t
```

You can run the app with the apps Vysor (to see the app in the PC) and Expo through this commmand:

```
npm run android
```