leveldb_dart
=======

<img alt="LevelDB Logo" height="100" src="http://leveldb.org/img/logo.svg">

**Fast & simple storage - a Dart LevelDB wrapper**

Introduction
------------

**[LevelDB](https://github.com/google/leveldb)** is a simple key/value data store built by Google, inspired by BigTable. It's used in Google Chrome and many other products. LevelDB supports arbitrary byte arrays as both keys and values, singular *get*, *put* and *delete* operations, *batched put and delete*, bi-directional iterators and simple compression using the very fast [Snappy](http://google.github.io/snappy/) algorithm.

**leveldb_dart** aims to expose the features of LevelDB in a **Dart-friendly way**.

LevelDB stores entries **sorted lexicographically by keys**. This makes leveldb_darts's <code>getItems</code> interface a very powerful query mechanism.

Platform Support
----------------

Only linux amd64 platform is supported.

Basic usage
-----------

Add `leveldb` to your `pubspec.yaml` file.

```
name: myproject
dependencies:
  leveldb:
```

Open a database and read/write some files.

```
import 'dart:async';
import 'package:leveldb/leveldb.dart';

Future main() async {
  LevelDB db = await LevelDB.open("/tmp/testdb1");
  db.put("abc", "def");
  String value = db.get("abc");
  print("value is $value"); // value2 is def
}
```
Check out [example/main.dart](example/main.dart) for more example code.
