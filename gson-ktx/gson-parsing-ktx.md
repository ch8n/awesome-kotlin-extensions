<h1 align="center">Awesome Android Extensions - <a href="https://chetangupta.net" target="_blank">AndroidBites</a>
</h1>

![awesome-android-extension-androidbites](./../androidbites_awesome_extension_banner.jpg)

<p align="center">
    A curated list of Awesome Kotlin Extensions. :octocat:
</p>

<p align="center">
  <a href="#"><img alt="Android Language Badge" src="https://badgen.net/badge/OS/Android?icon=https://raw.githubusercontent.com/androiddevnotes/awesome-android-kotlin-apps/master/assets/android.svg&color=3ddc84"/></a>
  <a href="#"><img alt="Kotlin Language Badge" src="https://badgen.net/badge/language/Kotlin?icon=https://raw.githubusercontent.com/androiddevnotes/awesome-android-kotlin-apps/master/assets/kotlin.svg&color=f18e33"/></a>
</p>

## :eyes: Social
[LinkedIn](https://bit.ly/ch8n-linkdIn) | 
[Medium](https://bit.ly/ch8n-medium) | 
[Twitter](https://bit.ly/ch8n-twitter) | 
[StackOverflow](https://bit.ly/ch8n-stackOflow) | 
[CodeWars](https://bit.ly/ch8n-codewar) |
[Portfolio](https://bit.ly/ch8n-home) |
[Github](https://bit.ly/ch8n-git) |
[Instagram](https://bit.ly/ch8n-insta) |
[Youtube](https://bit.ly/ch8n-youtube) 


## :memo: Contribution
See [contributing.md](contribution.md)

## Gson Parsing KTX
Useful extension for parsing GSONString to Object and vice-versa

### :book: Content
* [Convert Object class to JSONString](#ObjectToJSONStringConversion)
* [Convert JSONString to respective Object Class](#JSONStringToObjectConversion)
---

### <a name="ObjectToJSONStringConversion"/> Convert Given Object class to JSON String
```kotlin
/**
*  [Author] : Ashok 
*  [Updated on] : 12/10/2020
**/
fun Any.toJson(): String? {
    try {
        return gson.toJson(this)
    } catch (exception: Exception) {
    }
    return null
}
```
#### Usage
```kotlin
//test class used for demonstration
data class TestObject(val name: String?,val rollNo: Int?)

val testObject = TestObject("Ashok", 922)
val json = testObject.toJson()
```
---

### <a name="JSONStringToObjectConversion"/> Convert JSON String to respective Object class
```kotlin
/**
*  [Author] : Ashok 
*  [Updated on] : 12/10/2020
* Below method uses generics and can convert JSONString
* to Any type of object depending on the type provided]
**/
fun <T> String.fromJson(type: Type): T? {
    if (this.isEmpty()) {
        return null
    }
    try {
        return gson.fromJson<T>(this, type)
    } catch (exception: Exception) {
    }

    return null
}
```
#### Usage
```kotlin
//test class used for demonstration
data class TestObject(val name: String?,val rollNo: Int?)

val json= "{\"name\":\"Ashok\",\"rollNo\":922}"
val testObject: TestObject? = json.fromJson<TestObject>(TestObject::class.java)
```

## :cop: License
```
   Copyright [2020] [Chetan gupta] [chetangupta.net]
   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

 ```


