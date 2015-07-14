# Sound.js
a Wrapper of  Audio &amp; WebAudio for playing a normal audio file

==============

Use HTML5 Audio:
```
    var sound = new Sound({
        id: "bgm",
        src: "res/bgm.mp3",
        loop: false,
        volume: 1,
        channel: 4,
        useWebAudio: false,
    });
    sound.load();
    sound.onLoad=function(){
       this.play();
    }
 ```
 
 Use WebAudio :
 
 ```
     var sound = new Sound({
        id: "bgm",
        src: "res/bgm.mp3",
        loop: false,
        volume: 1,
        channel: 2,
        useWebAudio: true,
    });
    sound.load();
    sound.onLoad = function(){
       this.play();
    }
 ```
 
 useWebAudio: default is true. It will try to use WebAudio first.
 
 channel: for Multi Channel .
 
 ```
 sound.play();
 
 setTimeout(function(){
     // if channel <=1 , 
     //      the prev playing will be stopped.
     //  else , another there will be a new playing

     sound.play();
 },1000);
 
 
 ```