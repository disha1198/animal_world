<template>
    <div class="historyContainer">
        <ul>
            <li v-for="(item, index) in history" :key="index">
                <button @click.prevent="playSound(item.sound)">
                    <img :src="require(`../assets/images/${item.img}.png`)">
                    <p>{{item.desc}}</p>
                </button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HistoryBar',
    props: {
        history: {
            type: Array
        }
    },
    methods: {
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
    .historyContainer {
        display: flex;
        justify-content: center;
        width: 85%;
        margin: auto;
        min-height: 7vw;
    }

    button{
        margin: 0 5px 0 5px;
    }

    img {
        width: 5vw;
        height: 6vw;
    }

    ul {
        list-style: none;
    }

    li {
        float: left;
    }
</style>