## Non-modular Java Image Example

A small application that shows how to build a custom JRE image with non-modular application code
using SLF4J and LogBack Classic.

The plugin is configured in `build.gradle` as follows:

```
plugins {
    id 'org.beryx.runtime' version '1.12.5'
    ...
}

runtime {
    modules = ['java.naming', 'java.xml']
}
```

### Usage
**Running with gradle:**
```
./gradlew run
```

The following text should appear on your screen:
```
LOG: Hello, from non-modular image
```


**Creating and executing a custom runtime image:**
```
./gradlew runtime
./build/image/bin/template-gradle-jlink
```

The following text should appear on your screen:
```
LOG: Hello, from non-modular image
```