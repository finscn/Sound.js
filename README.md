# Sound.js
a Wrapper of  Audio &amp; WebAudio for playing a normal audio file

==============

Use HTML5 Audio:
```
    var sound = new Sound({
        id: "bgm-1",
        src: "res/bgm-1.mp3",
        loop: false,
        volume: 1,
        tag: "bg",
        channel: 4,
        useWebAudio: false,
    });
    sound.load();
    sound.onLoad = function(){
       this.play();
    }
 ```
 
 Use WebAudio :
 
 ```
     var sound = new Sound({
        id: "sfx-1",
        src: "res/sfx-1.mp3",
        loop: false,
        volume: 1,
        tag: "sfx",
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
 
 tag: you can do something to many sounds by tag.
 example:
 
 Sound.setMuteByTag("bg", true)
 
 all sounds that tag=="bg" will be muted.
 