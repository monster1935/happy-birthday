<template>
  <div id="app">
     <div class="velas">
        <div class="fuego"></div>
        <div class="fuego"></div>
        <div class="fuego"></div>
        <div class="fuego"></div>
        <div class="fuego"></div>
    </div>
    <Candle></Candle>
    <Cake></Cake>

    <div class="name">Dear YuanYuan</div>
    <div class="happy">
        <img src="static/img/HappyBirthday.png">
    </div>
    <bg-pic></bg-pic>
    <audio src="static/music/happy.mp3" autoplay="autoplay" loop="loop"></audio>
  </div>
</template>

<script>
import $ from 'jquery';
import Cake from './components/Cake';
import BgPic from './components/BgPic';
import Candle from './components/Candle';

export default {
  name: 'App',
  data () {
    return {
    };
  },
  components: {
      Cake,
      BgPic,
      Candle
  },
  mounted () {

    setTimeout(function () {
        $('.name').animate({
            opacity:"1",
            top:"15%"
        },2000);
    },6000);

    setTimeout(function () {
        $('.happy').animate({
            opacity:"1",
            top:"15%"
        },2000);
    },6000);
    
    // ios auto play hack
    const $bgAudio = $('audio')[0];
    $bgAudio.play();
   
    
    document.addEventListener('click', function () {
        $bgAudio.play()
    }); 
    document.addEventListener('touchstart', function () {
        $bgAudio.play()
    });
  },
}
</script>

<style>
html, body {
  height: 100%;
  padding: 0;
  margin: 0;
  overflow: hidden;
}
#app {
  text-align: center;
  position: relative;
  background: #ee9ca7;
  background: -webkit-linear-gradient(top left, #ee9ca7 0%, #ee9ca7 100%);
  background: linear-gradient(to bottom right, #ee9ca7 0%, #ee9ca7 100%);
  background-color:rgba(255,255,255,0.9);
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  overflow: hidden;
}
.name{
    font-weight: bold;
    position: absolute;
    text-align: center;
    overflow: hidden;
    width: 100%;
    top: -100px;
    opacity: 0;
    font-size: 32px;
    color: #fff;
    z-index: 10;
}
.happy {
    position: absolute;
    opacity:0;
    width: 230px;
    height: 137px;
    overflow: hidden;
    left: 50%;
    margin-left: -115px;
    top: 30%;
    animation-delay: 0s;
    z-index: 10;
}

@-webkit-keyframes in {
    to {
        -webkit-transform: translateY(0);
        transform: translateY(0);
    }
}

@keyframes in {
    to {
        -webkit-transform: translateY(0);
        transform: translateY(0);
    }
}

.come {
    animation-delay: 0.4s;
    animation: coming 2s;
    opacity: 1;
}

@keyframes coming {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

@-webkit-keyframes coming {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}


</style>
