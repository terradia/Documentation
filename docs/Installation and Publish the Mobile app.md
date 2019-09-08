![Logo terradia](https://lh3.googleusercontent.com/-lNyFr6uZKvH9DKEpZSowznpXG-Oa83EJ14Pq77OyfG2VK8lqm6np8NF_Yj1F6_UDxCYxsf20ddU "Terradia")

### Installation  
  
First, just run :
  
    npm install
    
to install all the dependencies.  
  
It is needed to install `expo-cli` to publish the app on the Stores or update "Over the Air" the app.  

    npm install -g expo-cli
       
[HERE ADD PARAGRAPH ABOUT THE ENV]  
  
### Run the app  
  
[HERE DESCRIBE HOW TO RUN THE MOBILE APP AND THE SERVER]  
  
### Publish the app  
  
Publish the app means send the last version to the servers of `expo` see [this link](https://docs.expo.io/versions/latest/workflow/publishing/) for more information about what publishing does.  
  
What is important to know is that if you publish the app with the "release-channel" `prod`, it will update the app on all the mobiles connected to internet when they will run the app. Note that the changes will be available on the devices only after the second run of the app  
  
This is called update of the app `Over the Air` or `OTA`, [more info here](https://docs.expo.io/versions/latest/guides/configuring-ota-updates/).  
  
To publish the app and update over the air simply run :  
  
	 # ~/terradia-mobile/ > expo publish --release-channel=prod

to publish in release-channel "prod" that corresponds to the production.  
  
### Update the App on Mobile Stores  
  
#### App Store  
  
First, you need to change the version number in the `app.json` file at the root of the mobile app  
  
  
	 "expo": {
		 ...
		 "version": [new version tag],
		 ...
	 }

Then, you need to publish the app on `prod` like seen in last part.  
  
	 # ~/terradia-mobile/ > expo publish --release-channel=prod

Now, we will be able to build the app in the newest version.  
      
- Run the command to build the app :  
  
    ```bash  
    #start the build on expo servers  
    expo build:ios --release-channel=[your release-channel]  
    ```  
      
Now we need to upload the app just built to the [AppStore Connect](https://appstoreconnect.apple.com/)  .  
  
To do that just run :   
  
	 expo upload:ios 

It will download the app from the servers of expo.  
Once you started the script to upload, expo will ask some data :  
- First your AppleID & Password  
  
- A two factor auth will be send to your Apple devices if it is the first time you upload the app, just put the code in your terminal as demanded.  
  
- The most tricky part could be the moment expo demand the application password. Just follow the instructions expo tell you.  
      
- After some time (this is really long, sometimes more than 10-15 minutes), your app is uploaded to the App Store Connect.  
  
- Now go to the [AppStore Connect](https://appstoreconnect.apple.com/)  
  
- My apps. Select `Terradia`  
  
Once the build is sent to the App Store Connect, we will prepare the new version.  
To create the new version on the App Store, it is really simple, follow these instructions :  
- Click on the `(+) Version or platform` and select `iOS`  
  
- On the page, you will need to precise what is new in the version, precise the number of the version etc... just fill the data correctly and precisely.  
  
- Select the build corresponding to the version you just sent to the store a few minutes ago. (Note that the build might not be available directly. There is a delay of a few minutes / hours before you can test the build with TestFlight. At the moment the build is available with TestFlight, it is available in the page of the version to be pushed.)  
  
- Finish to complete all the fields and proceed to the submission of the app.  
  
Now you need to wait 24 to 48 hours for the App Store to start the process of checking the app conformity. Once all the test passed, the app is updated on the store during the 24 hours to come.   
  
#### Play Store  
  
For the Play Store, it is similar than the App Store, thanks to expo.  
  
First, you need to change the version number in the `app.json` file at the root of the mobile app. You also need to update the versionCode like this :  
  
	 "expo": {
		 ...
		 "version": [new version tag],
		 ...
		 android: {
			 "versionCode": [new versionCode] (last value + 1 is recommanded),
			 ...
		 }
	 } 

Since the versionCode is a number, you cannot choose : "1.0.1" or anything like that, you can only do 2, or 3 etc..  
  
Then, you need to publish the app on `prod` like seen in last part.  
  
	 # ~/terradia-mobile/ > expo publish --release-channel=prod 
 
Now, we will be able to build the app in the newest version.  
   
- Run the command to build the app :  
  
    ```bash  
     #start the build on expo servers  
     expo build:android --release-channel=[your release-channel]  
    ```  
    
Now, we need to upload the apk freshly built to the Google Play Console.  
  
To do that just run :   
  
	 expo upload:android  
 
It will download the app from the servers of expo.  
Once you started the script to upload, expo will ask you the path to the json file to connect to the Play Console.
  
[HERE PRECISE WHERE YOU CAN FIND THE FILE]
  
When you gave the path to the file, just wait a few moment and then the apk will be uploaded to the play console.  
  
- Go to the [Play Console](https://play.google.com/apps/publish/)  
  
- Click on `Terradia`  
  
- Then `Publication Management` and finally `Application Versions`.  
  
- In the Card "Production" click on `Manage`  
  
Here you will be able to handle the versions of the app in Production. 
  
- Click on `Create a version`. On the page, choose the build that you just pushed under "choose a build on the library"  
  
- Fill the update description in any languages needed.
  
- Save & Verify the app.  

Google will test the app under the 24 - 72 hours, and then an update will be send to the devices that downloaded the app.
