# cy_update_checker

![N|Solid](https://cyberyakku.com/wp-content/uploads/2021/11/unnamed-file.png)

#


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

# Create the json file

- Then create a confirmation [json](https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/update_config.json) file and link to it
- පසුව මෙලෙස [json](https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/update_config.json) පයිල් එකක් සාදා එහි ලින්ක් එක ගන්න.



https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/update_config.json



```sh
{
  "rows": [
    {
      "Version_code"         : 1.2,  // Change Version name of the new update
      "Update_Title"         : " New Update Available ",
      "Update_Message"       : "The latest update to this app has just been released",
      "Update_Button_text"   : "update",
      "Link"                 : "Your App Link",
      "Update_Dialog_Close"  : "true" // Allows you to cancel the update dialog
    }
  ]
}

```

![N|Solid](https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/2.png)



# Command

> The update checks when the app is opened
> App එක OPEN කරන විට Update කිරීම පරීක්ෂා කරයි
```sh

 CyberYakkuUpdateChecker cyberYakkuUpdateChecker = new CyberYakkuUpdateChecker(MainActivity.this,
                "https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/update_config.json"); // enter Your json link
        cyberYakkuUpdateChecker.setVersionName(BuildConfig.VERSION_NAME);

       // The update checks when the app is opened
        cyberYakkuUpdateChecker.check();
	
```
![N|Solid](https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/1.png)


> Checks for updates when the button is pressed
> button එක tuch විට Update සඳහා පරීක්ෂා කරයි

```sh
 @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);



        CyberYakkuUpdateChecker cyberYakkuUpdateChecker = new CyberYakkuUpdateChecker(MainActivity.this,
                "https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/update_config.json"); // enter Your json link
        cyberYakkuUpdateChecker.setVersionName(BuildConfig.VERSION_NAME);



        mUpdate = (Button) findViewById(R.id.Update);


        mUpdate.setOnClickListener(view -> {

            Toast.makeText(this, "Update Checking..", Toast.LENGTH_SHORT).show();
            //Checks for updates when the button is pressed
            cyberYakkuUpdateChecker.check();


        });

```
![N|Solid](https://raw.githubusercontent.com/CyberYakku/cy_update_checker/master/3.png)



## _Powered By [Cyber Yakku](https://cyberyakku.com/)_

