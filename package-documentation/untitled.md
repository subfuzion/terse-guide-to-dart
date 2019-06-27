---
description: Use dartdoc to generate HTML docs for your package API
---

# The dartdoc tool

## About dartdoc

The `dartdoc` tool that comes with the Dart SDK generates HTML documentation for Dart packages.

This documentation can be viewed locally or you can host it online. The generated documentation looks just like the official [Dart SDK documentation](https://api.dart.dev/).

## Doc comments

The comments that dartdoc processes are called [doc comments](https://dart.dev/guides/language/effective-dart/documentation#doc-comments). These are comments that appear before declarations and use three slashes \(`///`\) instead of the normal two for comments in Dart code.

Prefer writing doc comments for public APIs and consider writing library-level comments \(just before the `library` directive\). See [Effective Dart: Documentation](https://dart.dev/guides/language/effective-dart/documentation) for more guidance.

## Generate docs

To generate documentation for your package, run `dartdoc` from the package root directory.

The generated HTML documentation will be written to `doc/api`.

## View docs locally

Open `doc/api/index.html` in your browser.

However, If you want to use the search function, you will need to load the docs with an HTTP server. For example:

```bash
$ pub global activate dhttpd
$ dhttpd --path doc/api
```

## References

[dartdoc](https://pub.dev/packages/dartdoc)  
[Effective Dart: Documentation](https://dart.dev/guides/language/effective-dart/documentation)





