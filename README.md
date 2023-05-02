# aframe
 
# Änderungen Stand 02.05.23:

Funktionalität im Script-Element:

      AFRAME.registerComponent('play', {
        init: function () {
          var myEl = document.querySelector('#boxsound1')
          this.el.addEventListener('click', function() {
            myEl.components.sound.playSound();
          });
        }
      })

      AFRAME.registerComponent('stop', {
        init: function () {
          var myEl = document.querySelector('#boxsound1')
          this.el.addEventListener('click', function() {
            myEl.components.sound.stopSound();
          });
        }
      })

      AFRAME.registerComponent('pause', {
        init: function () {
          var myEl = document.querySelector('#boxsound1')
          this.el.addEventListener('click', function() {
            myEl.components.sound.pauseSound();
          });
        }
      })
      
__________________________________________________________________

Die A-Frame Elemente:

 <assets>
        <audio
          id="prio"
          src="assets/audio/First_Things.mp3"
          preload="auto"
        ></audio>
     
        <audio
        id="prio02"
        src="assets/audio/First_Things.mp3"
        preload="auto"
      ></audio>
    </assets>

      <a-entity id="boxsoundAuto" 
            geometry="primitive: box" 
            position="35 5.23936 5" 
            color="#002999"
            scale="5 5 5"
            sound="src: #prio02; autoplay: false; loop: true" 
      ></a-entity> 



      <a-box
      id="boxsound1"
      position="40 5.23936 5"
      scale="5 5 5"
      sound="src: #prio;"
      event-set__click="_event: on: click"

      play
    ></a-box>

      <a-box
        id="boxstart"
        position="36 3 18"
        scale="3 3 3"
        color="#177245"
        soundcontrollers
        event-set__click="material.color: #0DFB85"
        event-set__mouseenter="_event: material.color: #0DFB85"
        event-set__leave="_event: moulseleave; material.color: #177245"
        event-set__down="_event: mousedown; scale: 2.5 2.5 2.5"
        event-set__up="_event: mouseup; scale: 3 3 3"
        event-set__leave="_event: mouseleave; scale: 3 3 3"

        play
      ></a-box>

      <a-box
        id="boxpause"
        position="40 3 18"
        scale="3 3 3"
        color="#EF9B0F"
        soundcontroller
        event-set__click="material.color: #FFDB1C;"
        event-set__down="_event: mousedown; scale: 2.5 2.5 2.5"
        event-set__up="_event: mouseup; scale: 3 3 3"
        event-set__leave="_event: mouseleave; scale: 3 3 3"

        pause
      ></a-box>

      <a-box
        id="boxstop"
        position="44 3s 18"
        scale="3 3 3"
        color="#C51E3A"
        event-set__click="material.color: #FF1A40"
        event-set__down="_event: mousedown; scale: 2.5 2.5 2.5"
        event-set__up="_event: mouseup; scale: 3 3 3"
        event-set__leave="_event: mouseleave; scale: 3 3 3"
        soundcontroller
        stop
      ></a-box>
