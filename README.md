[![](https://jitpack.io/v/ankit1057/SuperPinView.svg)](https://jitpack.io/#ankit1057/SuperPinView)
# SuperiorPinView For Android

SuperiorPinView For Android is a library for getting PIN as input or OTP In a much easier and Beautiful Way.

## Installation


Add it in your root build.gradle at the end of repositories:
```gradle

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```

#### Fetch Using Gradle :

```gradle

dependencies {
	        implementation 'com.github.ankit1057:SuperPinView:v1.57'
	}
```

## Usage

```XML
 <io.ankit.superiorpinview.SuperiorPinView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:pinWidth="40dp"
        app:textColor="#000"
        app:pinHeight="40dp"
        app:textSize="12sp"
        app:pinLength="5"
        app:cursorVisible="false"
        app:hint=""
        app:inputType="number"
        app:forceKeyboard="false"
        app:password="false"
        >
    </io.ankit.superiorpinview.SuperiorPinView>

```
##### Available xml attributes and explanations : 

```app:pinBackground``` : Sets the pin box's background, accepts a drawable or a selector drawable. When a ```selector``` is used, the focused pin box is highlighted. <br />
```app:pinWidth``` and ```app:pinHeight``` : Sets the width and height of the pinbox. <br />
```app:pinLength``` : number of pin boxes to be displayed.<br />
```app:forceKeyboard``` : forces the keyboard when the pinview is activity/fragment is opened.
```app:cursorVisibility``` : Toggles cursor visibility.<br />
```app:hint``` : Pin box hint. <br />
```app:inputType``` : Accepts ```number``` or ```text``` as values. <br />
```app:password``` : Masks the pin value with ```*``` when true. <br />
```app:splitWidth``` : Determines the width between two pin boxes.
### Java : 

To create the view programmatically : 
```java
SuperiorPinView pin = new SuperiorPinView(this);
```
Or reference it from findViewById
```java
pin = (SuperiorPinView) findViewById(R.id.pinview);
pin.setPinBackgroundRes(R.drawable.sample_background);
pin.setPinHeight(40);
pin.setPinWidth(40);
pin.setInputType(Pinview.InputType.NUMBER);
pin.setValue("1234");
myLayout.addView(pin);    
```
##### To get and set the pin values use the ```pin.getValue()``` and ```pin.setValue()``` methods respectively.

There is an event listener which is triggered when the user is done entering the otp which can be used as follows : 
```java
pinview.setPinViewEventListener(new SuperiorPinView.PinViewEventListener() {
            @Override
            public void onPinEntered(SuperiorPinView pinview, boolean userInput) {
	    	//Make api calls here or what not
                Toast.makeText(MainActivity.this, pinview.getValue(), Toast.LENGTH_SHORT).show();
            }
        });
```
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

