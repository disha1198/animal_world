<template>
    <div class="footerContainer">
        <ul class="footerInfo">
            <li>Disha Shah</li>
        </ul>
        <ul class="footerInfo">
            <li><strong>Audio Source:</strong></li>
            <li><a href="https://seaworld.org/animals/sounds/">Seaworld.org</a></li>
        </ul>
        <ul class="footerInfo">
            <li><strong>Image Sources:</strong></li>
            <li><a href="https://pixabay.com/">Pixabay</a></li>
            <li><a href="https://google.com/">Google</a></li>
        </ul>
        <ul class="footerInfo">
            <li><strong>Information Source:</strong></li>
            <li><a href="https://google.com/">Google</a></li>
        </ul>
        <ul class="footerInfo">
            <li><strong>Font Source:</strong></li>
            <li><a href="https://www.fontspace.com/mistis-fonts/whale-i-tried">Whale I Tried</a></li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style scoped>
    .footerContainer {
        display: flex;
        color: #fff;
        justify-content: center;
        font-family: Helvetica, Arial, sans-serif;
        width: 100%;
        height: 20%;
        margin: auto;
        margin-top: 40px;
        font-size: 0.5em;
        background-color: #00ae42;
        -webkit-text-stroke: 0px darkgreen;

    }

    .footerInfo {
        text-align: left;
        list-style: none;
        padding-left: 6vw;
        padding-right: 3vw;
    }
    strong{
        color: #003a15;
        line-height: 30px;
    }
    a{
        color: aliceblue;
        text-decoration: none;
    }
</style>