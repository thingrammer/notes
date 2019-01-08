### Kotlin Notes
#### feature
* global function
* main function parameters avoidable
* return type Unit avoidable
* default-value parameters; named arguments
* string template, with operator ${}
* destructuring declaration
* infix function, like operator overload
* vararg parameters, forward with *
* for (i in 0..10); if (i in 0..10)
* == & === comparision
* data class
* when, pattern match
* sealed class
* singleton object; anonymous object
* flattened lambda expression
* anonymous namespace, ::func
* extension function, Obj.method(); method parameter, A.B()
* default continuation parameter **it**
* directly delegate; only for interfaces

```kotlin
class Rush(py: Py = Py(10)) : Pb by py 

interface Pb {
    fun pick()
    fun take()
}
data class Py(private val x: Int) : Pb {
    override fun pick() = println("pick!")
    override fun take() = println("take!")
}
```

* by lazy {}
```kotlin
    val str: String by lazy {
        println("lazy")
    }
```

#### functions
* repeat
* let, continuation parse operation;
* with, continuation parse method;
* filter, map, any, all, none; 
* find, findLast; return null if absent
* first, last; throw exception if absent
* count
* partition, not stable, splitted to two list of tuple
* associateBy, construct map; groupBy construct multiMap; default value is **it**
* zip; zip to pair list or zip reduce to single list with a continuation
* flatMap; min; max;
* sorted; sortedBy{-it}
* map.withDefault{}; return a new map reference
* getOrElse(index: Int){}

##### wrap
* listOf, mapOf, mutableListOf...

