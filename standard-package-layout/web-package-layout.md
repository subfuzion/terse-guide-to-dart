---
description: For web applications
---

# Web package layout

## A sample web [application package](https://dart.dev/tools/pub/glossary#application-package)

```text
foo/
  LICENSE
  README.md
  CHANGELOG.md
  pubspec.yaml
  pubspec.lock
  bin/
    server.dart
  lib/
    src/
  tool/
  web/
    index.html
    main.dart
    style.css
```

{% hint style="info" %}
Do commit the lockfile \(`pubspec.lock`\) to version control for a web application package.
{% endhint %}

The `web` directory is for the files used for a web package, including [entrypoint](https://dart.dev/tools/pub/glossary#entrypoint) scripts \(scripts with `main()`\)and supporting files \(e.g., HTML and CSS files\).

{% hint style="info" %}
Even for web packages...

* Library implementation code be placed under the`lib/src` directory.
* Image files and other similar static data resources should be placed under `lib` \(e.g., `lib/asset`, `lib/public`, `lib/web`, or similar\).
* Examples should be placed under `example`.
{% endhint %}

See [Application package layout](general-package-layout.md) for an explanation of the other directories.



## Reference

[Package layout conventions](https://dart.dev/tools/pub/package-layout)



