# Functions in Kotlin


## Characteristic

Some of the function characteristic in Kotlin are:

* Returning as value
* Can be passed as an arguments
* Can be assigned to a variable
* Can be stored in data structure
* Can be declared in top of file (not necessarily a member of a class)
* Can have default arguments & named arguments


## Declaration
Declared using `fun` keyword, followed by function name, followed by list of parameters inside parentheses `(paramName: paramType)`, optionally followed by `: returnType` (by default returns `Unit`), then the function body inside `{ .. }`

```kotlin
// Without return type
fun save() { }
// is implicitly equals to
fun save(): Unit { }

// With return type
fun add(x: Int, y: Int): Int {
    return x + y
}
```

## Default arguments
Function parameters can have default values, so when you call the function, by default you don't have to specify a value for those parameters.

Tips: It is recommended that the parameters with default values are the last ones in the list of parameters, otherwise the default values can be used only when calling the function with named arguments.

```kotlin
fun formatDateTo(
    date: Date, 
    format: String = "dd MM yyyy"
): String { }

val displayedDate: String = formatDateTo(Date())
```

## Named arguments
When named arguments are used, the position order of their declaration can be changed.

```kotlin
fun formatDateTo(
    date: Date,
    format: String = "dd MM yyyy"
): String { }

val displayedDate: String = formatDateTo(format = "yyyy-MM-dd", date = Date())
```

## Types of functions

### Generic functions
Functions can have generic parameters, which are specified using angle brackets `<>` before the function name.

```kotlin
fun <T> getListItem(list: List<T>, index: Int): T { }

val deliveryOrders: List<DeliveryOrder> = listOf()
val drivers: List<Driver> = listOf()
val firstDeliveryOrder: DeliveryOrder = getListItem(deliveryOrders, 0)
val firstDriver: Driver = getListItem(drivers, 0)
```

### Higher Order Function
* Is a function that takes function as an parameters, or returns a function

```kotlin
class Button: View() {
    fun setOnClickListener(
        onClick: (View) -> Unit
    ) {
        onClick.invoke(this)
    }
}
fun main() {
    val button = Button()

    // without lambda, use named arguments
    button.setOnClickListener(onClick = {
        println("button clicked")
    })
    
    // with lambda
    button.setOnClickListener { view ->
        println("button clicked")
    }
}
```

### Extension functions

```kotlin
fun Date.formatTo(format: String): String { }

// call the function
val today = Date()
println(today.formatTo("dd-MM-yyyy"))
```

### Infix functions

* Must be declared as class member / extension function
* Must have single parameter
* No default argument
* The paramaters must not varargs

```kotlin
class Person(val name: String) {
    infix fun eat(food: String) {
        println("$name eat $food")
    }
}
fun main() {
    val toy = Person("Toy")
    toy eat "KFC" // print: Toy eat KFC
}
```