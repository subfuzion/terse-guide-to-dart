---
description: What is a Dart package?
---

# Understanding Dart Packages

## The pubspec

The fundamental unit for sharing software, such as libraries and applications, within the Dart ecosystem is a _package_.

A package is a directory contains that as a minimum at least a [pubspec file](https://dart.dev/tools/pub/pubspec), which contains metadata about the package. The pubspec is a named `pubspec.yaml` that's written in [YAML](http://www.yaml.org/).

For personal packages, the only required field is `name`. For packages you intend to share with the world by publishing to the Pub site, you will also need to provide `version`, `description`, and `environment` fields.

* **name** - all lowercase with underscores to separate words \(`[a-z0-9_]`\).
* **version** - follow [semantic versioning](http://semver.org/spec/v2.0.0-rc.1.html).
* **description** - brief, plain text description of the package.
* **environment** - SDK [version constraint](https://dart.dev/tools/pub/dependencies#version-constraints).

If you use Stagehand \(discussed [here](../standard-package-layout/scaffold-a-dart-package.md)\) to scaffold a package, a pubspec with various fields will be created for you.

### Package dependencies

In addition to providing information that helps others to discover your package, the pubspec also identifies your package's dependencies on other packages and the required version of the Dart runtime environment for your package.

* **dependencies**
* **dev\_dependencies**
* **dependency\_overrides**

Because packages are not published with their dependencies, these dependencies need to be identified in the pubspec. These dependencies are fetched separately using either `dart pub get` or `dart pub upgrade`.

### dart pub get

When you run `dart pub get` in your own package directory, the command will inspect your `dependencies` and `dev-dependencies` fields and fetch all the packages your package requires, installing them in a central [system cache](https://dart.dev/tools/pub/glossary#system-cache). It will also create a `.packages` file in your package's top directory that maps each of your package dependencies to the corresponding package in the system cache.

### dart pub upgrade

Use the pub upgrade command to fetch the latest versions of all dependencies, including [transitive dependencies](https://dart.dev/tools/pub/glossary#transitive-dependency), by ignoring `pubspec.lock`. This command will write \(or overwrite an existing\) `pubspec.lock;` this lockfile should be checked into version control for application packages.

### dart pub run

After running `dart pub get` to fetch all of your package dependencies, you can run `pub run <path>/<to>/<file>.dart`, where path should be `bin`, `example`, or `tool`. Note that specifying the `.dart` extension isn't necessary.

If the file under `bin` has the same name as the package, then you don't need to specify the path, but you do need to specify the extension. For example, for package `foo`, this will work: `pub run foo.dart`.

### dart pub publish

When you are ready to share a package with the rest of the world, use the `dart pub publish`.

The first person to publish a package becomes the only person who can publish new versions of that package. To add or remove other people who can publish updates, use the `dart pub uploader` command.

The default is to publish to the Pub site. The `publish_to` field in the pubspec can be used to specify a custom server or to specify `none` to prevent accidental publishing of private packages.

{% hint style="info" %}
For publishing to the [Pub site](https://pub.dev/), all uploaders must have a Gmail or Google Apps email address.
{% endhint %}

## Resources

[Dart packages on Pub](https://pub.dev/)  
[How to use packages](https://dart.dev/guides/packages)  
[Publishing packages](https://dart.dev/tools/pub/publishing)  
[pub get](https://dart.dev/tools/pub/cmd/pub-get)  
[pub publish](https://dart.dev/tools/pub/cmd/pub-lish)  
[pub run](https://dart.dev/tools/pub/cmd/pub-run)  
[pub uploader](https://dart.dev/tools/pub/cmd/pub-uploader)  
[pub upgrade](https://dart.dev/tools/pub/cmd/pub-upgrade)  
[The pubspec file](https://dart.dev/tools/pub/pubspec)





