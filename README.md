# JioSaavn Song Downloader Chrome Extension

![Song Quality Selector](https://i.ibb.co/0Xgm001/Screenshot-1.png)
![Downloads](https://i.ibb.co/KswRTGr/Screenshot-2.png)
![Downloads](https://i.ibb.co/Fsf0Dz6/Screenshot-3.png)
![Single Song Download](https://i.ibb.co/tHfNZtT/Screenshot-9.png)
![Bulk Song Download](https://i.ibb.co/MM4Y9F2/Screenshot-11.png)

This Extension will allow you to download any song, album or playlist in JioSaavn (previously Saavn) seamlessly and easily.

## Features

- Select Any Quality Downloads (Supports HQ 320kbps)
- Download a Single Song
- Download an Album
- Download a Playlist

## How to use it

- You will have a Download Selector on Top Menu. where you can select your download Quality
- To Download a Single Song. You will see a "Download" button near the song title
- To Download an Album You will see a "Download" button near the album title
- To Download an Playlist You will see a "Download" button near the playlist name

## How to Install it

this extension is currently not hosted in chrome webstore, so you will have to install it manually on chrome. below are the steps

- download the extension here : [download](https://github.com/justiriser/JioSaavn-Downloader-Chrome-Extension/archive/master.zip)
- extract the zip file
- go to chrome extensions page [chrome://extensions/](chrome://extensions/)
- you will see a button called "Load Unpacked Extension.." click that
- select the extracted folder and press "ok"

Note : the extension will be enabled on development mode. you will have a popup when opening the chrome. press cancel on that popup. you can always enable it again on the chrome extension page.

## Issues

if you have any issues regarding this extension you may submit a issue in here [issue link](https://github.com/naqushab/saavn-downloader-extension/issues/new) 

## Behind the Scenes

### overview

Sorry to write this. but the saavn has a very poor security it is just exposed to everyone.. they haven't even mingled there code where in point a hacker or someone cannot read the code. the code they have minified is readable and easily exploitable because of it.

if you have javascript knowledge you can easily understand whats going behind. on the web application they will generate a single response url for a song playback which will be played via the player on the web. the song url will expire in approx 10s which means you cannot download it most of the time as the url expires. it will give an Forbidden error most of the time when you try to download.

### Flaws

the web is typically exploitable we all know that. atleast this would have been much harder for someone to crack if it has been improved

-The Didn't Mingle the code. anyone can read the code and understand it.

-The Api of the application is exposed to the global anyone can access it from the chrome developer tools. for instance the 'Player' object :D you can play songs Programmatically. are you kidding ?

-Each song object details directly printed on the dom '.song-json' :D any hacker can easily deserialize  the json object and use the data.

if they fix those the extension will be stopped from working :D sorry guys

### How it works

Song
- When you press a download button on song. it will send a request and generate a download URL from server.
- Then it will download the song asynchronously in background. as the download song will have a gibberish name and no song details.
- Then we will download the album art asynchronously.
- Then we will add ID3 tags (Title, Singer, Cover, Composer and stuff) to the downloaded song.

Album, Playlist
- Will download all Songs asynchronously as mentioned above.
- We will make a virtual zip on memory and create a folder and add the songs there.
- Download the Zip

### What's New
- Support for JioSaavn.com (previously Saavn.com)
- Minor Modifications
