<template>
<time class="countdown">
    <div class="block">
        <p class="digit">{{ days | two_digits }}</p>
        <p class="text">Days</p>
    </div>
    <div class="block">
        <p class="digit">{{ hours | two_digits }}</p>
        <p class="text">Hours</p>
    </div>
    <div class="block">
        <p class="digit">{{ minutes | two_digits }}</p>
        <p class="text">Minutes</p>
    </div>
    <div class="block">
        <p class="digit">{{ seconds | two_digits }}</p>
        <p class="text">Seconds</p>
    </div>
</time>
</template>
<style scoped>
.countdown{
    width: 50%;
    margin-left: auto;
    margin-right: auto;
    display: block;
}
.block {
    display: block;
    float: left;
    width: 25%;
}
.text {
    color: #aed434;
    font-size: 16px;
    text-align: center;
}

.digit {
    font-size: 18px;
    color: #6b6e70;
    text-align: center;
}

@media (min-width: 600px){
    .countdown{
        width: 30%;
    }
}
</style>
<script>
export default {

    /* ready function will be here */

    props : {
        date : {
            type: Number,
        }
    },

    data() {
        return {
            now: Math.trunc((new Date()).getTime() / 1000)
        }
    },

    /* Computed properties will be here */
    mounted() {
        window.setInterval(() => {
            this.now = Math.trunc((new Date()).getTime() / 1000);
        },1000);
    },

    computed: {
        modifiedDate(){
            return Math.trunc(Date.parse(this.date) / 1000);
        },
        seconds() {
            return (this.modifiedDate - this.now) % 60;
        },

        minutes() {
            return Math.trunc((this.modifiedDate - this.now) / 60) % 60;
        },

        hours() {
            return Math.trunc((this.modifiedDate - this.now) / 60 / 60) % 24;
        },

        days() {
            return Math.trunc((this.modifiedDate - this.now) / 60 / 60 / 24);
        }
    }
}
</script>

