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

## Android View's Visibility KTX
Useful extension for updating visibility of your views

### :book: Content
* [Set View Visibility to VISIBLE](#show)
* [Set View Visibility to GONE](#gone)
* [Set View Visibility to INVISIBLE](#invisible)
* [Set View Visibility based on boolean condition](#showBool)
* [Set View InVisibility based on boolean condition](#showWeakBool)

---

### <a name="show"/> Set View Visibility to VISIBLE
```kotlin
/**
*  [Author] : Anonymous 
*  [Updated on] : 8/9/2020
**/
fun View.show() {
    this.visibility = View.VISIBLE
}
```
#### Usage
```kotlin
text_view.show()
```
---

### <a name="gone"/> Set View Visibility to GONE
```kotlin
/**
*  [Author] : Anonymous 
*  [Updated on] : 8/9/2020
**/
fun View.gone() {
    this.visibility = View.GONE
}
```
#### Usage
```kotlin
text_view.gone()
```
---
### <a name="invisible"/> Set View Visibility to INVISIBLE

```kotlin
/**
*  [Author] : Anonymous 
*  [Updated on] : 8/9/2020
**/
fun View.invisible() {
    this.visibility = View.INVISIBLE
}
```
#### Usage
```kotlin
text_view.invisible()
```
---

### <a name="showBool"/> Set View Visibility based on boolean condition

```kotlin
/**
*  [Author] : Anonymous 
*  [Updated on] : 8/9/2020
**/
fun View.setVisibility(isVisible:Boolean) {
    if(isVisible){
        this.visibility = View.VISIBLE
    }else{
        this.visibility = View.GONE
    }
}
```
#### Usage
```kotlin
progress.setVisibility(progress < 95)
```

---

### <a name="showWeakBool"/> Set View Invisible based on boolean condition

```kotlin
/**
*  [Author] : Anonymous 
*  [Updated on] : 8/9/2020
**/
fun View.setVisibilityWeak(isVisible:Boolean) {
    if(isVisible){
        this.visibility = View.VISIBLE
    }else{
        this.visibility = View.INVISIBLE
    }
}
```

#### Usage
```kotlin
progress.setVisibilityWeak(progress < 95)
```

---

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


