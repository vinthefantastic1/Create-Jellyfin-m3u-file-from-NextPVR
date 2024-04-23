# Create Jellyfin m3u file from NextPVR

### In NextPVR under Settings/Access/Unauthenticated Access (at the bottom)

		make sure "Allow unauthenticated access for streaming Live TV / Recordings" is checked
  
### Use this command to create your m3u file (of course replace the url with your url)
		curl http://192.168.4.188:8866/service?method=channel.m3u -o channels.m3u

### You should get something like this:

    #EXTM3U url-tvg="http://192.168.4.188:8866/service?method=channel.xmltv.x"

    #EXTINF:0 tvg-id="nextpvr-7181" tvg-chno="4.1", SomeChannel-HD
    http://192.168.4.188:8866/live?channel=4.1
    
    #EXTINF:0 tvg-id="nextpvr-7149" tvg-chno="4.2", SomeChannel SD
    http://192.168.4.188:8866/live?channel=4.2
    
    #EXTINF:0 tvg-id="nextpvr-7150" tvg-chno="4.3", SomeChannel Other
    http://192.168.4.188:8866/live?channel=4.3
    
    #EXTINF:0 tvg-id="nextpvr-7151" tvg-chno="4.4", SomeChannel 4.4
    http://192.168.4.188:8866/live?channel=4.4

### Save this file somewhere you can access it for Jellyfin (in the next step)

## In Jellyfin

#### Go to Administration/Dashboard/Live TV (toward the middle left)

  1. Add Live Tuner
  1. Select M3U Tuner
  1. On the File or URL, enter the location of the file you saved above like this:
             
          /media2/channels.m3u
  1. Press Save
  2. Press the HOME Button
  3. Go to Live TV
  4. Then Channels at the top
  5. Click on one of the channels to see the live tv
  6. Adding the Program Guide is something for another day
     




