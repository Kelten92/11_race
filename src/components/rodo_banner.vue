<template>
    <section class="rodo" v-if="!accepted">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quasi consequatur sapiente reiciendis quis commodi veniam fugiat necessitatibus quod quos voluptates.</p>
        <i class="far fa-times-circle" v-on:click="rodo_accept"></i>
    </section>
</template>
<style scoped>
.rodo{
    font-family: Arial, Helvetica, sans-serif;
    background: #aed434;
    padding:15px;
    color:#474b4f;
    position: sticky;
    z-index: 3;
    bottom: 0;
    left: 0;
    width: 100%;
    text-align: center;
}
.rodo p{
    font-size: 14px;
    margin:0 15px;
    display: inline;
}
.rodo i{
    color:red;
    font-size: 24px;
    display: inline;
}
</style>
<script>
export default {
    data () {
        return {
            accepted: false,
        }
    },
    methods: {
        rodo_accept: function() {
            localStorage.setItem("rodo_accepted",1);
            this.accepted = true;
        }
    },
    mounted: function () {
        this.$nextTick(function () {
            if(localStorage.getItem("rodo_accepted") == true)
            {
                this.accepted = true;
            }
        })
    },
}
</script>

