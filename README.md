# fathym.io_Sparkfun_Photon_WeatherShield

Download the [fathym.io.photon-0.0.1-weathershield library folder](https://github.com/fathym/fathym.io_ParticleDev/blob/master/fathym.io.photon-0.0.1.zip) to get your Sparkfun Photon Weather Shield up and running in Fathym.
## About 
[![Fathym logo](http://community.fathym.com/Files/Storage/ef3e1f7f-3303-4296-9660-044c33e60cbd "Fathym Logo")](http://fathym.com) [![Particle logo](http://blog.particle.io/images/particle-horizontal-dark.png "Particle logo")](http://particle.io)
[![Sparkfun logo](https://www.sparkfun.com/marcomm/SF-Logo-2C-PC-%C2%AE.jpg "Sparkfun logo")](https://www.sparkfun.com/)


[Fathym](http://fathym.com) is a platform that gives you collaborative, front-end apps, dashboards and notifications for your Particle Photon. Get up and running in the cloud, and even control your photon from your very own Fathym app in minutes. 

# Tutorial

## Getting up and running

1. **Wire up your hardware**
  - Adding the [Sparkfun Photon Weather Shield](https://www.sparkfun.com/products/13630) is as simple as aligning the pins and securing your Photon to the Weather Shield ![Sparkfun Photon Weather Shield](http://community.fathym.com/Files/Storage/11f58daf-0073-4fe9-af9a-62ec43adf2ae "Sparkfun Photon Weather Shield")
  - If you want, add a [Soil Moisture Sensor](https://www.sparkfun.com/products/13322) to the area on the Weather Shield marked "Soil Moisture" ![Soil Moisture Sensor](http://community.fathym.com/Files/Storage/571b7548-e980-45c1-8586-9332a8ca5d7a "Sparkfun Photon Weather Shield")
2. **Download the [fathym.io.photon-0.0.1-weathershield](https://github.com/fathym/fathym.io_Sparkfun_Photon_WeatherShield/blob/master/fathym.io.photon-0.0.1-weathershield.zip) zip folder from this repo and unzip**
2. **Open the Particle Dev Desktop app and add the fathym.io.photon-0.0.1-weathershield folder**
![Particle Dev](https://40.media.tumblr.com/85a6b84ac6a20005769c38cf79ea9c55/tumblr_o58dv5IR7S1qcz8h1o1_1280.jpg "Particle Dev")
  - Download the [Particle Dev Environment](https://www.particle.io/dev) if you haven't already
  - Inside Particle Dev: File -> Add Project Folder -> Find the fathym.io folder
  - For more about working with your Photon, start with the tutorials in the [Particle Guide](https://docs.particle.io/guide/getting-started/intro/photon/)
5. **Select your device, save, compile, flash**                                       
    ![Particle Icons](http://community.fathym.com/Files/Storage/18dc2dab-fd6e-4754-89ba-28e6611c1dae "Particle Icons")
  - The .ino should get random test data flowing to Fathym exactly as is, so we'll test everything before messing with the code
6. **Create a new Photon Part in your Fathym Home Space**
  ![Fathym Home](https://41.media.tumblr.com/101c284e6b4c640957cbaa86e444fe32/tumblr_o58dv5IR7S1qcz8h1o2_1280.jpg "Fathym Home")
  - Create an  account at [community.fathym.com](http.//community.fathym.com) if you haven't already
  - From your Home Space, click the plus "+" button to get to the catalog of addable parts
  - Choose the Particle Photon part
  - Add your Photon deviceID, which you can find on your [Particle Dashboard](https://dashboard.particle.io/user/devices)
8. **Enter your Photon Part on Fathym and add visualizations**
![Inspector](https://36.media.tumblr.com/e783e4d513003a6dc328c38347a4fa51/tumblr_o58dv5IR7S1qcz8h1o3_1280.jpg "Inspector")
  - From inside your Particle Photon Part, click the plus "+" button to get to the catalog of addable parts
  - Start by adding the inspector display
  - Save and watch your data flow through!

## Customizing

1. **Inside Particle Dev, open the fathym.io-photon.ino file**
![ino](https://40.media.tumblr.com/31879b26805e0ddac21e0a97e9fbe36e/tumblr_o58dv5IR7S1qcz8h1o4_1280.jpg "ino")
  - You'll see commented instructions about how and where to add code for your sensors
  - If you've added a [Soil Moisture Sensor](https://www.sparkfun.com/products/13322) to your weather station, be sure to uncomment the associated code
  - Note that fathym.set("attribute name", value, "units of measurement") formats the JSON to send to Fathym
2. **Open the Fathym.Build.h file**         
![build.h](https://40.media.tumblr.com/7ec2caa15654a3f089cb182301aefcbd/tumblr_o58dv5IR7S1qcz8h1o5_1280.jpg "build.h")
  - Edit the attributes that are automatically sent along with your payload by setting each item to true or false 
  - Note that the Fathym.io library includes support Photon battery power - enable battery support by uncommenting the code at the bottom of the FathymBuild.h file
  - If you've added a [Battery](https://www.sparkfun.com/products/8483) and [Battery Shield](https://www.sparkfun.com/products/13626), be sure to uncomment the associated code in the FathymBuild.h file
3. **Add additional dashboard visualizations for your device in Fathym**
![Fathym Dashboard](https://36.media.tumblr.com/447b4d8abf0869768b89b0411e377eae/tumblr_o2crfxZXFf1qcz8h1o2_1280.jpg "Fathym Dashboard")
  - From inside your Particle Photon part, click the plus "+" button to get to the catalog of addable parts
  - Try an Historic Value part
    - Fill out the "Property Name" field with one of the attributes you're sending from your Photon (the attribute name must be an exact, case-sensitive match). Leave this field blank to create a generic graph with dropdown menu of the attributes you're sending so you can switch the attribute on the fly.   
4. **Create a Fathym Notification**         
![Notification Rule](http://community.fathym.com/Files/Storage/4ed0acc5-6b33-47e5-a8ae-a4bc5484b12a "Notification Rule")
  - From inside your Particle Photon part, click the config "cog wheel" button
  - Enter the "Add Ons" part
  - Enter the "Publish Subscription" part
  - Again, click the config "cog wheel" button
  - Enter the "Responses" part
  - Click the plus "+" button to get to the catalog of addable parts
  - Select the "Check" part
  - Name the Check Part and add a "Message Evaluation" 
    - Ensure that the property name you use is an exact match to one you're sending from your Photon
  - Save the Check part and then Enter into the Check part you just created
  - Click the plus "+" button to get to the catalog of addable parts
  - Add an "Email Response" and configure with your message and desired send frequency

## Collaborating and Setting Permissions
![Permissions](http://community.fathym.com/Files/Storage/06927353-54ad-4ecc-b29a-99cbc1f837da "Permissions")
1. From inside your Particle Photon part, click the edit button (pencil icon)
2. Open the "Permissions" tab
3. Here you can select which users have read, write, delete, contributor, moderator, or full control access
  - Full control allows the user to enter the parts configure settings in addition to everything else
  - You can only give permission to existing Fathym users
  - Type "Everyone" to give the entire Fathym userbase a certain permission
4. Once you've given a user permission to work with your part, you'll need to share the part's url with them directly or place your part in a space that they already have access to, like the Community Space for example.

## Share your project with the Fathym community                 

1. From inside your Fathym Home Space, find and enter the "Community Space" (tree icon) 
2. Inside the Community Space,  click the plus "+" button to get to the catalog of addable parts
3. Change the selected tab in the upper right from "Create New" to "Add Existing
4. Search the "Existing Catalog" for your Particle Photon Device and Add!


  
