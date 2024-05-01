# mesibo_sample_app

## Problem
the sending of message is not working. you can verify that by following steps
1. login from 1st device as user 1
2. login from 2nd device as user 2
3. send messsage form user 1 to user 2
4. you wont receive the message and also the listener `Mesibo_onMessageStatus` is not called which further verifies that message is not sent

## more info
1. platform and api version that we encountered this issue on : we tested using `mesibo_flutter_sdk v2.2.17` on android api level 34, 33 , 29 , we tested on real device as well as emulator
2. mesibo app id: `366532`
3. mesibo app token:  `tvjt0pdj4xd67rgknpc9mi0z1nifrom667iubjobeeajkq8ofaz58cnyt8khkogy`
4. Mesibo connection status: as you can see from the logs, it is `Mesibo.MESIBO_STATUS_ONLINE`
5. logs:
   user 1 logs:
```
D/EGL_emulation( 6201): app_time_stats: avg=3223.43ms min=3.58ms max=90088.07ms count=28
I/MesiboCore ( 6201): E0105-165022-960(6201)(stop): stop called by API, s: 70
I/MesiboCore ( 6201): E0105-165022-961(6201)(stop): stop called by API, s: 70
I/MesiboCore ( 6201): E0105-165022-962(6201)(set_credentials): waiting for stop() to complete
I/MesiboCore ( 6201): E0105-165022-961(6264)(main_thread): mesibo api stopped: reason 1 0 (3)
I/MesiboCore ( 6201): E0105-165023-013(6201)(set_credentials): stopped
D/EGL_emulation( 6201): app_time_stats: avg=108223.55ms min=108223.55ms max=108223.55ms count=1
I/MesiboCore ( 6201): E0105-165023-630(6201)(start): mesibo android api: 2.4.5 protocol: 2.4.2 os: 33 app: com.yoliday.experience
I/MesiboCore ( 6201): E0105-165023-631(6201)(start): starting mesibo
I/flutter ( 6201): Mesibo_onConnectionStatus: 2
I/flutter ( 6201): Mesibo_onConnectionStatus: 5
I/flutter ( 6201): Mesibo_onConnectionStatus: 6
I/flutter ( 6201): Mesibo_onConnectionStatus: 1
D/EGL_emulation( 6201): app_time_stats: avg=32.55ms min=3.85ms max=415.80ms count=21
D/EGL_emulation( 6201): app_time_stats: avg=198.16ms min=13.24ms max=916.15ms count=5
I/flutter ( 6201): Mesibo_onMessage: from: (Mohamed) group: () Message: Hello from Flutter
```
   user 2 logs:
```
I/MesiboCore (  961): E0105-175022-954(2103)(main_loop): mesibo - user signed-in from another device...exiting   
I/MesiboCore (  961): E0105-175022-955(2103)(main_thread): mesibo api stopped: reason 4 0 (3)
I/flutter (  961): Mesibo_onConnectionStatus: 5
I/MesiboCore (  961): E0105-175121-944(961)(start): mesibo android api: 2.4.5 protocol: 2.4.2 os: 29 app: com.yoliday.experience
I/MesiboCore (  961): E0105-175121-944(961)(start): starting mesibo
I/flutter (  961): Mesibo_onConnectionStatus: 6
I/flutter (  961): Mesibo_onConnectionStatus: 1
```