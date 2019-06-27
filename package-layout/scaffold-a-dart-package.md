---
description: Kick start your Dart package development generated boilerplate
---

# Scaffold a Dart package

## Using Stagehand to generate boilerplate

[Stagehand](https://pub.dev/packages/stagehand) is a Dart project generator for scaffolding application, web, and library packages with conventional boilerplate.

### Install Stagehand

```text
pub global activate stagehand
```

### Scaffold a package

Run stagehand inside of an empty directory where you want to generate your app. Running it without options will display all the generators and options available.

* `package-simple` - boilerplate for a library package
* `console-full` - boilerplate for a command-line tool or application
* `web-simple` - boilerplate for a basic web app
* `flutter-web-preview` - boilerplate for a simple Flutter web app

### Test the generated package

After scaffolding a package, first run `pub get` to install package dependencies.

Next, for a **library package**, run either the generated test \(`pub run test`\) or the example \(`pub run example/simple_example.dart`\).

For an **application**, run either the generated test \(`pub run test`\) or the main app \(`pub run bin/main.dart`\).

For a **web app**, make sure you have installed webdev first for serving Dart web apps during development \(`pub global activate webdev`\). Then run `webdev serve`. Finally, open a web browser and navigate to `http://localhost:8080`.

## References

[Stagehand](https://pub.dev/packages/stagehand)

