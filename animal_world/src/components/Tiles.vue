<template>
    <!-- <div> -->
        <div class="tileContainer1">
            <ul>
                <li v-for="(item, index) in images" :key="index">
                    <button id="myButton" @click="checkHistoryCount(index)" @click.prevent="playSound(item.sound)">
                        <img :src="require(`../assets/images/${item.img}.png`)">
                        <p>{{item.desc}}</p>
                    </button>
                </li>
            </ul>
        </div>

</template>

<script>
export default {
    name: 'Tiles',
    props: {
        images: {
            type: Array
        },
        history: {
            type: Array
        }
    }
    ,
    methods: {
        addToHistory(ind) {
            this.history.push({img:this.images[ind].img, desc:this.images[ind].desc, sound:this.images[ind].sound});
        },
        deleteEntry(key){
            this.history.splice(key,1);
        },
        checkHistoryCount(ind) {
            if(this.history.length < 10){
                this.addToHistory(ind);
            }
            else{
                this.deleteEntry(this.key);
                this.addToHistory(ind);
            }
        },
        playSound (sound) {
            if(sound) {
                var audio = new Audio(sound);
                audio.play();
            }
        }
    }
}

</script>

<style scoped>

    @font-face {
    font-family: "kids";
    src: url("../assets/fonts/Whale I Tried - TTF.ttf");
    }

    p{
        font-family: 'kids', Helvetica, Arial, sans-serif; 
        font-size: 2em;
        color: #00ae42;
        -webkit-text-stroke: 0px black;
    }

    ul {
        list-style: none;
        padding-left: 5vw;
        justify-content: center;
    }

    li {
    float: left;
    }

    img {
        width: 9vw;
        height: 9vw;
        padding: 3vw 2vw;;
    }

    .tileContainer1 {
        display: flex;
        justify-content: center;
        width: 90%;
        margin: 0 auto;
    }

    button {
        margin-left: 0.5vw;
        margin-right: 0.5vw;
        margin-bottom: 1vw;
    }
    
</style>