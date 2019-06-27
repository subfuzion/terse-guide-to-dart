---
description: For packages that will be imported by other packages
---

# Library package layout

## A sample [library package](https://dart.dev/tools/pub/glossary#library-package)

```text
foo/
  LICENSE
  README.md
  CHANGELOG.md
  pubspec.yaml
  doc/
    foo_guide.md
  example/
    lib/
      foo_example.dart
  lib/
    resource/
      icon.png
      style.css
    foo.dart
    src/
      bar.dart
      baz.dart
  test/
    foo_test.dart
```

{% hint style="info" %}
**Don't** commit `pubspec.lock` to version control for a library package.
{% endhint %}

See [Application package layout](general-package-layout.md) for an explanation of these directories, specifically for the [lib](general-package-layout.md#the-lib-directory) directory details.

{% hint style="info" %}
Just to drive home the point about assets, if this package needs to make resources public so they can be imported by other packages, they need to be under the `lib` directory.

Shown in the sample above,  there are resources under`lib/resource` that consumers of the foo package can reference using the [resource package](https://github.com/dart-lang/resource).
{% endhint %}

## Reference

[Package layout conventions](https://dart.dev/tools/pub/package-layout)



