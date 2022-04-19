# cy_update_checker


> 1.Add a gradle allprojects
```sh
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}


```
> 1.Add a gradle dependency.

	dependencies {

		implementation 'com.github.CyberYakku:cy_update_checker:CyberYakku'
    		implementation "com.airbnb.android:lottie:5.0.1"
   		implementation 'com.intuit.sdp:sdp-android:1.0.6'

	}




# Command




https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/update_config.json


{
  "rows": [
    {
      "Version_code": 1.2,  // 
      "Update_Title": " New Update Available ",
      "Update_Message": "The latest update to this app has just been released",
      "Update_Button_text": "update",
      "Link": "Your App Link",
      "Update_Dialog_Close": "true"
    }
  ]
}



