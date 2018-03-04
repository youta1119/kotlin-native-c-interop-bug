# kotlin-native-c-interop-stub-bug
example project that kotlin-native generate invalid clang stub

## What's the problem?
if `pkgName` contains invalid identifier for clang, compile fail with an error.

## How to reproduce?
First, try `cinterop -def examplelib.def`. This will succeed.

Next, try `cinterop -def example-lib.def`.This will fail with an error like this. 

```
build/invalid-build/kotlin/example-lib/example-lib.kt:3:16: error: expecting a top level declaration
package example-lib
               ^
build/invalid-build/kotlin/example-lib/example-lib.kt:3:17: error: expecting a top level declaration
package example-lib
                ^
build/invalid-build/kotlin/example-lib/example-lib.kt:5:1: error: expecting a top level declaration
import konan.SymbolName
```

## Environment
- kotlin-native 0.6
- macOS 10.13.3
