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
* [Load Image using Glide with options](#ImageLoadingGlideWithOptions)

---

### <a name="ImageLoadingGlide"/> Load Image using Glide
```kotlin
/**
*  [Submitted by] : Inderpreet Singh 
*  [Updated on] : 21/10/2020
* Load Image using glide.
*
* If a placeholder resource is applied it will be shown else nothing is displayed for
* placeholder
**/

fun ImageView.loadImage(url: String, @DrawableRes placeHolder: Int = -1) {
    Glide.with(context)
        .load(url)
        .apply { if (placeHolder != -1) this.placeholder(placeHolder) }
        .into(this)
}
```
#### Usage
```kotlin
//sample usage
imageView.loadImage(imageUrl,R.id.placeHolder)
```
---

### <a name="ImageLoadingGlideWithOptions"/> Load Image using Glide with different options
```kotlin
/**
*  [Submitted by] : Inderpreet Singh 
*  [Updated on] : 21/10/2020
**/

//Data class for different glide options
data class GlideImageOptions(
    @DrawableRes val errorHolder: Int,
    @DrawableRes val placeholder: Int? = null,
    val scaleType: GlideScaleType = GlideScaleType.Default,
    val isCircular: Boolean = false,
    val cache: GlideCache = GlideCache.Default
)

sealed class GlideScaleType {
    object Default : GlideScaleType()
    object CenterCrop : GlideScaleType()
    object FitCenter : GlideScaleType()
    object CenterInside : GlideScaleType()
    data class Custom(val height: Int, val width: Int) : GlideScaleType()
    data class CustomDimen(@DimenRes val height: Int, @DimenRes val width: Int) : GlideScaleType()
}

enum class GlideCache {
    Default,
    All,
    Data,
    None,
    Resource,
    Automatic
}

fun ImageView.loadImageWithOptions(url: String?, options: GlideImageOptions) {
    Glide.with(context)
        .load(url)
        .apply {
            when (options.scaleType) {
                is GlideScaleType.Default -> {
                    //do nothing
                }
                is GlideScaleType.CenterCrop -> this.centerCrop()
                is GlideScaleType.FitCenter -> this.fitCenter()
                is GlideScaleType.CenterInside -> this.centerInside()
                is GlideScaleType.Custom -> with(options.scaleType) {
                    val (height, width) = this@with
                    this@apply.override(height, width)
                }
                is GlideScaleType.CustomDimen -> with(options.scaleType) {
                    val (height, width) = this
                    this@apply.override(height, width)
                }
            }

            when (options.cache) {
                GlideCache.Default -> {
                    //do nothing
                }
                GlideCache.All -> {
                    this.diskCacheStrategy(DiskCacheStrategy.ALL)
                }
                GlideCache.Automatic -> {
                    this.diskCacheStrategy(DiskCacheStrategy.AUTOMATIC)
                }
                GlideCache.None -> {
                    this.diskCacheStrategy(DiskCacheStrategy.NONE)
                }
                GlideCache.Data -> {
                    this.diskCacheStrategy(DiskCacheStrategy.DATA)
                }

                GlideCache.Resource -> {
                    this.diskCacheStrategy(DiskCacheStrategy.RESOURCE)
                }
            }
            this.error(options.errorHolder)
            if (options.placeholder != null) {
                this.placeholder(options.placeholder)
            }

            if (options.isCircular) {
                this.circleCrop()
            }
        }.into(this)

}
```
#### Usage
```kotlin
//sample usage
imageView.loadImageWithOptions(imageUrl, GlideImageOptions(errorHolder = R.mipmap.ic_launcher,isCircular = true,scaleType = GlideScaleType.FitCenter))

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


