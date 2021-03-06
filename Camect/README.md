# Camect Connect for Hubitat

This app will allow you to:
1. Sync HSM states to set Camect's Home/Default modes
2. Create virtual Motion devices within Hubitat to represent each camera.
Motion detected on a camera will be synced to Hubitat. You need a Linux system
to run the [Camect Connector](https://github.com/bdwilson/camect-connector). This connects to Camect and forwards events to
Hubitat (still, all communications remains local). 

Instructions
---
* Import [this
driver](https://raw.githubusercontent.com/bdwilson/hubitat/master/Camect/camect_connect-motion-driver.py)
and [this
app](https://raw.githubusercontent.com/bdwilson/hubitat/master/Camect/camect_connect-app.py).
* Install the User App Camect Connect; use the variables you'll need to install the app.
    1. You'll need to then navigate to [https://local.home.camect.com](https://local.home.camect.com) and accept the Terms of Service. You'll end up on your local server and the name will be **xxxxxx**.l.home.camect.com. This beginning part is considered your **Camect Code**. 
    2. You'll then need to determine your username and password - the username in the default case is **admin** and the password is the first part of your email address that you used to register your camect device - for instance, bob@gmail.com would give you the password "bob".
**You need to enable OAUTH for the App during the optional installation.**
* Optionally install
[Camect Connector](https://github.com/bdwilson/camect-connector)
if you wish to sync Camera events to Hubitat. 

# Work In Progress
* Requires middleman to listen to events and forward those to Hubitat. 
* The Camect API is extremely limited, so help me out by voting for these:
    * Would be good if there was an API command to [temporarily suppress notitifications](https://groups.google.com/a/camect.com/forum/?oldui=1#!category-topic/forum/feature-request/1MnFjSAdPUI).  This way, if you are coming/going and not a visitor, you could inform camect suppress notifications (Telegram, Email, etc) based on some Hubitat event. This is somethign I'd really like to see.
    * [Suppressed Events are not exposed via API](https://groups.google.com/a/camect.com/forum/?oldui=1#!category-topic/forum/feature-request/A0K0YgHQizQ) so go vote for this as well if you need this and want to use Hubitat to determine if a notification gets sent.
    * [Animated GIF is not exposed via API](https://groups.google.com/a/camect.com/forum/?oldui=1#!category-topic/forum/feature-request/_PLRDMPR02Q) thus you can't send that URL to a device of your pleasing (Hubitat, or Pushover for instance).  

