[![](https://jitpack.io/v/saidmotya/GFX-AdPromote.svg)](https://jitpack.io/#saidmotya/GFX-AdPromote)

# GFX-AdPromote

An Android library for member secretGFX group, This can be used to growing your apps and get more install via a simple banner view & native view and interstitial dialog.

## Installation
*Step 1.* Add the JitPack repository to your project `build.gradle` file
```gradle
allprojects {
    repositories {
        //your repository
        maven { url 'https://jitpack.io' }
    }
}
```
*Step 2.* Add the dependency in the form
```gradle
dependencies {
    implementation 'com.github.saidmotya:GFX-AdPromote:1.0.0'
}
```

## Initialize
In your Java code, you can initialize the library with two way : inside splash with param Activity and check if the lib is connected than start the normal activity Or in MyApplication extend Application with param Context, see the full code source to more understand :
```java
AppPromote.initializePromote(this,"Your link json her");
        AppPromote.setOnPromoteListener(new OnPromoteListener() {
            @Override
            public void onInitializeSuccessful() {
                //AppPromote onInitializeSuccessful
            }

            @Override
            public void onInitializeFailed(String error) {
                //AppPromote onInitializeFailed
            }
        });
```


## How to use BannerPromote :
Place your banner promote in your xml layout like this:
```xml
 <com.gfx.adPromote.BannerPromote
        android:id="@+id/banner_view"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:banner_bodyColor="#FFFFFF"
        app:banner_contentColor="#E41000"
        app:banner_installColor="#FF5722"
        app:banner_installTitle="Install"
        />
```

#### BannerPromote Custom Attributes
| Attribute | Description |
| --- | --- |
| `banner_bodyColor` | Color of the banner body (by default is white) |
| `banner_contentColor` | Color of the banner content : title and description (description by default color : gray) |
| `banner_installColor` | Install button color : default is blue |
| `banner_installTitle` | Title of button : default is "Install" |


## BannerPromote in Javacode :
In your Java code, you can initialize your banner view and get listener, you can make the attributes of banner progrmatically or in xml layout :
```java
 BannerPromote bannerPromote = findViewById(R.id.banner_view);
        //bannerPromote.setInstallTitle("Play"); //Banner title button
        //bannerPromote.setInstallColor("#FFC107"); //Title button color with param String or Resource color
        //bannerPromote.setDescriptionColor(R.color.my_color_description);//Description Text color with param String or Resource color
        bannerPromote.setOnBannerListener(new OnBannerListener() {
            @Override
            public void onBannerAdLoaded() {
                //banner loaded.
            }

            @Override
            public void onBannerAdClicked() {
                //banner clicked.
            }

            @Override
            public void onBannerAdFailedToLoad(String error) {
                //banner failed to load.

            }
        });
```
## BannerPromote Example
![BannerPromote Example](https://raw.githubusercontent.com/saidmotya/GFX-AdPromote/master/ScreenShot/bannerPromo.gif)
