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

## Glide Image Loading KTX
Useful extension for image loading using Glide

### :book: Content
* [Load Image using Glide](#ImageLoadingGlide)
* [Load Image using Glide with placeholder](#ImageLoadingGlidePlaceholder)
* [Load Circular Image using Glide ](#CircularImageLoadingGlide)
* [Load Circular Image using Glide with Placeholder ](#CircularImageLoadingGlidePlaceholder)

---

### <a name="ImageLoadingGlide"/> Load Image using Glide
```kotlin
/**
*  [Submitted by] : Inderpreet Singh 
*  [Updated on] : 14/10/2020
*  Load image using Glide 
**/
fun ImageView.loadImage(context: Context, url: String) {
    GlideApp.with(context).load(url).into(this)
}
```
#### Usage
```kotlin
//sample usage
imageView.loadImage(this@MyActivity,imageUrl)
```
---

### <a name="ImageLoadingGlidePlaceholder"/> Load Image using Glide with placeholder
```kotlin
/**
*  [Submitted by] : Inderpreet Singh 
*  [Updated on] : 14/10/2020
**/
fun ImageView.loadImageWithPlaceholder(context: Context, url: String, placeHolderId: Int) {
    GlideApp.with(context).load(url).placeholder(placeHolderId).into(this)
}
```
#### Usage
```kotlin
//sample usage
imageView.loadImageWithPlaceholder(this@MyActivity,imageUrl,R.drawable.ic_placeholder)
```
---

### <a name="CircularImageLoadingGlide"/> Load Circular Image using Glide
```kotlin
/**
*  [Submitted by] : Inderpreet Singh 
*  [Updated on] : 14/10/2020
**/
fun ImageView.loadCircularImage(context: Context, url: String) {
    GlideApp.with(context)
			.load(url)
			.circleCrop()
            .into(this)
}

```
#### Usage
```kotlin
//sample usage
imageView.loadCircularImage(this@MyActivity,imageUrl)
```
---


### <a name="CircularImageLoadingGlidePlaceholder"/> Load Circular Image using Glide with Placeholder
```kotlin
/**
*  [Submitted by] : Inderpreet Singh 
*  [Updated on] : 14/10/2020
**/
fun ImageView.loadCircularImageWithPlaceholder(context: Context, url: String, placeHolderId: Int) {
    GlideApp.with(context).load(url).circleCrop()
            .placeholder(placeHolderId)
            .into(this)
}

```
#### Usage
```kotlin
//sample usage
imageView.loadCircularImageWithPlaceholder(this@MyActivity,imageUrl,R.drawable.ic_placeholder)
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


