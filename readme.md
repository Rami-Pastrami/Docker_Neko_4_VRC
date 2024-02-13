# NEKO 4 VRC

![image](https://github.com/Rami-Pastrami/Docker_Neko_4_VRC/assets/25966197/168b61ef-fe2a-423f-a5e0-42938db5f95f)

This is just a premade docker-compose file to allow the use of viewing the session within [N.eko](https://github.com/m1k1o/neko) inside VRChat over RTSP, by utilizing [MediaMTX](https://github.com/bluenviron/mediamtx) to convert the RTMP stream output from N.eko into an RTSP stream that VRChat can play on AVPro enabled players.

This is NOT a way to interact with browsers from VRChat directly. Work can be done to enable such functionality, but that was not my goal with making this. I simply wanted a convenient way to share media from a browser with all of my friends, and to self-host that solution.

## Instructions

- Clone the entire repository
- Edit the .env file to your requirements
	- Make sure you set your user and admin passwords each to something unique. They themselves are not revealed to users who are merely watching the RSTP stream, they are only relevant to those who connect to your Neko instance
	- Set the local machine IP key to the IP of the machine you are running this docker compose stack from
	- The other settings can be left as they are, but can be changed as per your liking
- Start the compose stack
- Enter N.eko from your local machine by going to (server_IP):8080 and confirm you can login and control the browser yourself
- *Optional* Use VLC to confirm the RTSP stream is working locally by opening network stream "rtsp://internal_server_IP:(rtsp_port)/(stream_key)"
- Port Forward your RTSP port from your router
- *Optional* User VLC to confirm the RTSP stream is working remotely by opening network stream "rtsp://your_external_IP:(rtsp_port)/(stream_key)"
- Use the link in vrchat worlds "rtsp://your_external_IP:(rtsp_port)/(stream_key)" to share with other people 
- *Optional* Instead of using your external IP in the address, set up a DDNS service to make your URL a bit prettier. Keep in mind its trivial to retrieve your IP from this, however.

## Standard Disclaimers
Take standard precautions that come when exposing ports to the public internet, even if its just the RTSP stream. Keep in mind all URLs put in VRC are saved to easily accessible logs, and users could check on your RTSP stream at later times if the endpoint never changes.

You can also expose N.eko to the internet to allow your friends to also control the browser from their end. There are various configurations for doing this, and you can read for what works best for you [here](https://neko.m1k1o.net/#/getting-started/configuration). Please keep in mind the people you give access to this browser, as any content they pull up from Neko would be logged as coming from your IP address.
