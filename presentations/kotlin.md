## Kotlin through the Java lens

### Impressions
 - streams and lambdas everywhere
 - more concise
 - more syntactic sugar
 - tries to live without null


### Goal of the creators (at JetBrains):
https://blog.jetbrains.com/kotlin/2011/08/why-jetbrains-needs-kotlin/
- increase internal productivity while
  - gradually switching to a more expressive language
  - keeping interoperability with existing codebase
- drive IntelliJ IDEA sales
- build community

### Basic syntax
- similarities
  - `package`, `import`
- `main` function:
  ~~~
  fun main(args: Array<String>) {
    println("Hello World!")
  }
  ~~~
- variables
  - var:
  - val: immutable
- types
  - kinda the same, but in Kotlin, everything is an object
  - but primitives can be represented as such at runtime
- fun
- Unit: the return type for `void` methods
- Any: the root of the Kotlin class hierarchy (java.lang.Object)
- Nothing: marks unreachable places
~~~
fun fail(message: String): Nothing {
    throw IllegalArgumentException(message)
}
~~~

### Syntactic sugar
- smart casts
  - the compiler deduces type
- ranges
  - `0..n` = `0 <= i <= n`
    - actually `0.rangeTo(n)`
  - `0 until n` = `0 <= i < n`
  - `n downTo 0` = `n >= i >= 0`
  ~~~
  if (i in 0..n) {
    print(i)
  }
  
  for (i in 0 until n step 2) {
    print i
  }
  ~~~
- class properties
  - default getters and setters (only getters for `val`)
- high level methods for handling collections
  - mapOf(), listOf(), setOf() etc. methods
  - builders for collection-creation
  - Streams-like collection operations
- Sequence
  - same functions as Iterable but different approach
  - lazy execution of processing
- data class
- elvis operator
- companion object
  - declared inside a class
  - a static inner class with a single instance
- extension function

### The little differences
- if is an expression with return value
  - if block of code then the last expression is the value
- `when` instead of `switch`
- classes are final by default
  - `open` modifier make it inheritable
  - similar for functions and properties
- named arguments
  - using the name of an argument, default valued arguments can be skipped
- triple quoted string
  - raw strings, can contain newline and special characters

### Added values
- `val` encourages more immutable code

### Disadvantages
