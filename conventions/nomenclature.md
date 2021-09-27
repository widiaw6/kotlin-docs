# Nomenclature

## General Principles

Names should reveal the intention/purpose of the entity. So, choose good and meaningful names.

* Descriptive
* Avoid abbreviations
  ```
  genYmdHms() -> generateTimestamp()
  ```
* Avoid generic words, e.g: `Manager`, `Processor`, `Data`, `Info`.
* Pronounceable.
  ```
  DataRcrd123 -> Customer
  ```
* When using an acronym, if it consists of two letters, capitalize it. If more, treat it as a word.
  ```
  IOStream, HttpInputStream, XmlFormatter, sendOtp()
  ```
* Add prefix `has` or `is` to variable/method with Boolean type/return
  ```
  val isPosted : Boolean = false
  fun hasAttachedDocuments() : Boolean { .. }
  ```
* Avoid encoding, hungarian notation, and member prefixes
* Explain yourself in code
  ```
  invoice != null && invoice.status == Status.REJECTED -> isInvoiceRejected
  ```
* Searchable


## Classes & Objects

* A descriptive class names are usually a noun or a noun phrase saying what the class _is_: `DeliveryOrder`, `UserPreference`.
* Avoid meaningless name
  ```
  class DeliveryOrderData -> class DeliveryOrder
  ```
* Write in **PascalCase**


## Functions / Methods

* A descriptive method names are usually a verb or a verb phrase saying what the method _does_: `createInvoice()`, `save()`
* Self explanation
  ```
  uploadPhoto -> uploadPhotoKtp
  ```
* Pick one word per concept, e.g: `fetch`/`retrieve`/`get`
* Write in **camelCase**

## Variables / Properties

* Having variable type as part of name
```kotlin
val employeeAccount: Account
val btnSave: Button
```
* Use plural names for arrays / collections
* Write in **camelCase**, for variables that hold objects with behaviour or mutable data
* Write in **SCREAMING_SNAKE_CASE**, for `const` or `val` properties with no custom `get` function
```kotlin
const val MAX_COUNT = 8
val USER_NAME_FIELD = "UserName"
```