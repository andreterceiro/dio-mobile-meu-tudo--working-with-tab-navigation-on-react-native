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

**OBS:** you need to run this command inside the created app directory.

As you can see in the first demo app, the bottom tabs navigation was created on this app, but it wasn't me that created this navigation on the app. It was the command `npx create-expo-app botttom-tabs`.

At least initially I did not understand the example because as you can see in some demo code of the [documentation page](https://reactnavigation.org/docs/bottom-tab-navigator/), the constant "MyTabs" seems not be used, see:

```typescript
import { View, Platform } from 'react-native';
import { useLinkBuilder, useTheme } from '@react-navigation/native';
import { Text, PlatformPressable } from '@react-navigation/elements';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';

function MyTabBar({ state, descriptors, navigation }) {
  const { colors } = useTheme();
  const { buildHref } = useLinkBuilder();

  return (
    <View style={{ flexDirection: 'row' }}>
      {state.routes.map((route, index) => {
        const { options } = descriptors[route.key];
        const label =
          options.tabBarLabel !== undefined
            ? options.tabBarLabel
            : options.title !== undefined
              ? options.title
              : route.name;

        const isFocused = state.index === index;

        const onPress = () => {
          const event = navigation.emit({
            type: 'tabPress',
            target: route.key,
            canPreventDefault: true,
          });

          if (!isFocused && !event.defaultPrevented) {
            navigation.navigate(route.name, route.params);
          }
        };

        const onLongPress = () => {
          navigation.emit({
            type: 'tabLongPress',
            target: route.key,
          });
        };

        return (
          <PlatformPressable
            href={buildHref(route.name, route.params)}
            accessibilityState={isFocused ? { selected: true } : {}}
            accessibilityLabel={options.tabBarAccessibilityLabel}
            testID={options.tabBarButtonTestID}
            onPress={onPress}
            onLongPress={onLongPress}
            style={{ flex: 1 }}
          >
            <Text style={{ color: isFocused ? colors.primary : colors.text }}>
              {label}
            </Text>
          </PlatformPressable>
        );
      })}
    </View>
  );
}

const MyTabs = createBottomTabNavigator({
  tabBar: (props) => <MyTabBar {...props} />,
  screens: {
    Home: HomeScreen,
    Profile: ProfileScreen,
  },
});
```

Teacher did a very small example. He did not create the screens (we already have the screens from the code we developed [when studied stack navigation](https://github.com/andreterceiro/dio-mobile-meu-tudo--working-with-stack-navigation-in-react-native/)).

First, he created a file src/routes/bottom-tabs.routes.tsx:

![bottom-tabs.routes.tsx](images/bottom-tabs-routes-tsx.png)

Second, he created a file src/routes/index.tsx. The app changed from:

![calling stack.routes.tsx from index.tsx](images/calling-stack-routes-tsx-from-index-tsx.png)

To:

![calling bottom.tabs.routes.tsx from index.tsx](images/calling-bottom-tabs-routes-tsx-from-index-tsx.png)

**OBS:** both files commented above are stored inside the directory "src/routes" in the Teacher's example.


# Destrucuring the value returned by the function creatingBottomTabNavgator()

Teacher change a code from:

![destructuring - before](images/destructuring-before_.png)

To:

![destructuring - after](images/destructuring-after_.png)

**Please pay attention to the line 6.**


# Personalizing the icons

Teacher find in the documentation by **@expo/vector-icons**:

![vector icons in the documentation](images/vector-icons-in-the-documentation.png)


## Finding for an icon in the documentation

Teacher sais that you can find for an icon in the documentation:

![finding for an icon in the documentation](images/finding-for-an-icon-in-the-documentation.png)

A comment: teacher showed that you can see the right link finding in Google by "expo icons".


## Installation

Teacher said that you don't need to install anything, but if the code don't work you can try to install `@expo/vector-icons`.


## Importing

You will need to make an import. As you can see in the next image, VSCode will show a lot of components when destructuring on importing:

![destructuring on importing](images/destructuring-on-importing.png)

Teacher selected (used inside the braces on line 5) **"Material Community Icons"**.


## Ways to personalize the icon in the bottom bar

Teacher personalized this way:

![personalizing the icons - teacher way](images/personalizing-the-icons--teacher-way.png)

After, he showed a way that he got from the documentation:

![personalizing the icons - documentation way](images/personalizing-the-icons--documentation-way.png)

**A comment: in the last case teacher needed to restart the app, closing the app and ran it again with the command `npm run start`**


## Different types of icons in the documentation

You can find for an icon package and after for an specific icon in the documentation.

![finding for an icon package in the documentation](images/finding-for-an-icon-package-in-the-documentation.png)

After, when you explore the documentation of the icon package, locate the icon and click on it, you will see how to import it on the application.

![importing an icon family](images/importing-an-icon-family.png)

And in the second instruction in the image we can see how to use the icon.

Inside the sabe library of icons (vector icons) you can use different types of icons packages.

Teacher said that we instruct us to avoid this pratice, but if you want you can do this.


# Teacher hints

- Put focus on golden actions, avoid excess of navigation options;
- The total of maximun recommended golden actions by the teacher is 5 or 6 golden actions;



# Repository related to the classes

[Link](https://github.com/digitalinnovationone/trilha-react-native-navigation-tabs)


# Official tutorial

[Link](https://reactnavigation.org/docs/tab-based-navigation/)