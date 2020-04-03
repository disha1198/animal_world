<template>
  <div id="app" class="container">
    <img id="mainLogo" alt="Animal Street logo" src="./assets/animals.png">
    <h1>{{showHeading}}</h1>
    <div class="slider">
	<!-- <div class="caption">
		Activity <img alt="Unicorn" src="./assets/unicorn.svg">
		<div class="text-box">
			<div>See</div>
			<div>and</div>
			<div>Say</div>
		</div>
	</div> -->
</div>
    <Tiles :images="tileList" :history="historyList"/>
    <HistoryBar :history="historyList"/>
    <Footer/>
  </div>
</template>

<script>
import Tiles from './components/Tiles.vue'
import HistoryBar from './components/HistoryBar.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  components: {
    Tiles,
    HistoryBar,
    Footer
  },
  data() {
    return {
      showHeading: "Click on an animal to hear voice",
      tileList:[
        {img: "bear", desc: "Bear", sound: "https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/bear.ashx?version=1_201811134817&la=en&hash=EF7EC380B6FB032DDEE3CEA31A01F27939E6DE63"},
        // {img: "https://pixabay.com/vectors/panda-bear-teddy-bear-animal-cute-1304584/", desc:"Bear"},
        // {img: "bear", desc: "Bear", sound: "bear.mp3"},
        {img: "camel", desc:"Camel", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/camel.ashx?version=1_201811134822&la=en&hash=6AEEC05C59F71ED708D2C6ED467AF0723E3D13B8"},
        {img: "cat", desc:"Cat", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/domestic_cat.ashx?version=1_201811134819&la=en&hash=E2E1A076205AC91E552CA84AFA46BEB6B32E5C50"},
        {img: "dog", desc:"Dog", sound: "https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/dogbark.ashx?version=1_201811134824&la=en&hash=5010B196BEBA48E3C9CD3CA4EA26D49863A4E092"},
        {img: "dolphin", desc:"Dolphin", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/dolphin_clicks.ashx?version=1_201811134825&la=en&hash=19CFFBE9F0F4F9DCA2847188795E9826729AF2B2"},
        {img: "elephant", desc:"Elephant", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/elephant.ashx?version=1_201811134825&la=en&hash=0557BBB893EA6D3FE7D62B6C3CE0427CE7142218"},
        {img: "horse", desc:"Horse", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/clydesdale.ashx?version=1_201811130506&la=en&hash=D277EAA7C0D1D48F224A69C120C47D86414CA142"},
        {img: "lion", desc:"Lion", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/lion_1.ashx?version=1_201811134826&la=en&hash=7232CC103347978D2ED052B973F0EE79E28CAABA"},
        {img: "tiger", desc:"Tiger", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/bengal_tiger.ashx?version=1_201811134825&la=en&hash=E14722662857807E1A2997FB06D2A853777E7F93"},
        {img: "whale", desc:"Whale", sound:"https://seaworld.scdn3.secure.raxcdn.com/-/media/seaworld-dotorg/audio-files/sound-library/beluga-whale-001.ashx?version=1_201811135223&la=en&hash=11BBC76EFE4ECC351687A52825F0262D64E6B1D3"},
      ],
      historyList:[
      ]
    }
  }

}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

@font-face {
  font-family: "kids";
  src: url("./assets/fonts/Whale I Tried - TTF.ttf");
}
#app {
  font-family: 'kids', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  letter-spacing: 1.5px;
  background-color: #28684D;
  /* background-image: url(./assets/images/bg01.jpg); */
  background-repeat: no-repeat;
  background-size: cover;
  font-size: 2em;
  color: #d6ddd9;
  -webkit-text-stroke: 1px darkgreen;
}

div > img {
  width: 25%;
  height: auto;
}

#mainLogo{
	width: 250px;
}

h1{
	font-size:2em;
}
.slider{
	text-align: center;
	position: relative;
	margin-top: 50px;
}

.caption{
  text-align: center;
  padding-top: 50px;
  padding-left: 10vw;
	line-height: 100px;
	font-size: 60px;
	color: #fff;
	position: relative;
	top: 50%;
	transform: translateY(-50%);
	text-shadow: 0px 5px 5px rgba(0,0,0,.25);
	margin-left: -300px;
}

.caption img {
  width: 50px;
}

.text-box{
	display: inline-block;
	position: relative;
  padding-left: 2vw;
}

.text-box div{
	display: inline-block;
	position: absolute;
	top: -200px;
	transform: rotateX(-90deg);
	opacity: 0;
	text-shadow: 0px 5px 5px rgba(0,0,0,.25);
	animation-timing-function: ease;
}

.text-box div:nth-child(1){
	animation: rollDown 7s forwards infinite;
}

.text-box div:nth-child(2){
	animation: rollDown2 7s forwards infinite;
}

.text-box div:nth-child(3){
	animation: rollDown3 7s forwards infinite;
}


@keyframes rollDown {
	0%{
		top: -200px;
		transform: rotateX(-90deg);
	}
	11%{
		top: -74px;
		transform: rotateX(0deg);
		opacity: 1;
	}
	22%{
		top: -74px;
		transform: rotateX(0deg);
		opacity: 1;
	}
	33%{
		top: 50px;
		transform: rotateX(30deg);
		opacity: 0;
	}
}

@keyframes rollDown2 {
	33%{
		top: -200px;
		transform: rotateX(-90deg);
	}
	44%{
		top: -74px;
		transform: rotateX(0deg);
		opacity: 1;
	}
	55%{
		top: -74px;
		transform: rotateX(0deg);
		opacity: 1;
	}
	66%{
		top: 50px;
		transform: rotateX(30deg);
		opacity: 0;
	}
}

@keyframes rollDown3 {
	66%{
		top: -200px;
		transform: rotateX(-90deg);
	}
	77%{
		top: -74px;
		transform: rotateX(0deg);
		opacity: 1;
	}
	88%{
		top: -74px;
		transform: rotateX(0deg);
		opacity: 1;
	}
	99%{
		top: 50px;
		transform: rotateX(30deg);
		opacity: 0;
	}
}

@keyframes slideColor{
	0%{
		background-color: #387780;
	}
	33%{
		background-color: #3f88c5;
	}
	66%{
		background-color: #588b8b;
	}
	100%{
		background-color: #387780;
	}
}

</style>
