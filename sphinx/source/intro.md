# Camera Module


## 1. Setup Raspberry pi
```{Failure}
:title: Raspivid no more available _(use libcamera instead)_
:collapsible: close
___Go to 2.A.a to see the camera commands___
```

Raspivid is no longer available on raspberry pi (raspbian os)
### A. Edit config file
Edit with your favorite editor the /boot/config.txt file
Remove "camera_auto_detect=1" and add "start_x=1"
It should be like that
```txt
# camera_auto_detect=1
start_x=1
```


## 2. Use command line tool
### A. Use of the cammera
```{attention}
:title: __Attention setup done the 23-11-05__
:collapsible: open

Good luck! Here is the [link](https://www.youtube.com/watch?v=ZDCuPhlKQqk) 
```


#### a. Camera Commands
1. test camera
    ```bash
    libcamera-hello -t 0
    ```
    
    ````{attention}
    :title: Errors, No camera available
    :collapsible: close    
    This command line permit a test of the camera,
    
    However it will send an error, 
    ```bash
    ***no cameras available***
    ```
    __GO TO THE PART 1, TO FIX THIS__
    
    ````
1. Get an image
    ```bash
    libcamera-jpeg -o test.jpg -t 1 --width 640 --height 480
    libcamera-raw -o test.raw -t 1 --width 640 --height 480
    ```
1. Get video
    ```bash
    libcamera-vid -t 10000 -o test.h264
    ```
