# Jellyfin client is now available on all LG webOSes
As of May 17, 2024, LG has approved the Jellyfin client for all webOSes ([link](https://github.com/jellyfin/jellyfin-webos/issues/169#issuecomment-2002719660)). As a result, the app is no longer available in the Web OS Dev Manager Apps but should now be availalbe in all webOS app stores. The below steps are no longer necessary, but have been left for reference.

# *Legacy steps:*

## Install Jellyfin on LG webOS Permanently
Yes you read the title right, It is possible to install Jellyfin permanently on a LG webOS smart TV and that too without rooting your TV.

Although I did make a guide nearly a year back, some new things have come to my attention that no longer require you to install a bulky IDE or have to extend developer mode every 50 hours.

### Requirements

- Access to a computer (Linux, Windows, Mac whatever)

- A LG Developer account. (If you dont have one sign up [here](https://webostv.developer.lge.com/develop/app-test/preparing-account/)) 

### Setting Up the TV

On your WebOS TV go to the LG content store and download the Developer mode app. Open it up and Sign in.

Then 1) Enable Developer mode and restart your TV.

Upon restart open up developer mode and enable the Key Server. Make note of the TV's ip address and Paraphrase you will need this later.

### Configuring it from your PC

Get the latest version of WebOS dev manager from webOS brew from [here](https://github.com/webosbrew/dev-manager-desktop) for your operating system and run it.

1. From the hand bar click on then add a device option.

2. When Prompted enter the IP address and paraphrase of TV and click add.

3. Once the connection has been made, select Available from the top bar and find Jelly fin and click on the install button.

There you go, Jelly fin is now installed.

### Making the Install Permanent

The way developer mode works is that it checks LG's servers to see if the time has run out or not. You can extend this by making a call to API. 

NOTE: The TV dos not need to be on for this to work.

Thankfull the webOS dev manager fetches the API key for us and all we have to do is call on it once before the 50 hours end. There are many ways to do this, bash scripts, home assistant and IF TTT.

I am going to be using a IF TTT applet. Click on this [link](https://ifttt.com/create) and create a account. Then create a new applet setting. Make it daily and select any random time. For the "do" stuff select web hooks.

In WebOS dev manager open the info tab and click on renew automatically from there copy the url and paste it in IF TTT's web hook.

There you go. Now Developer mode will be extended indefinitely and Hopefully should work without a hitch.

