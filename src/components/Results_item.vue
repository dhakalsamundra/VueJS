<template>
  <div class="result">
    <p>Reaction time: {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>

  </div>
</template>

<script>
export default {
props: ["score"],
data(){
    return{
        rank: null
    }
},
mounted(){
    if(this.score < 250){
        this.rank = "SupreMan"
    } else if(this.score < 400) {
        this.rank = "Rapid Reflex..."
    } else {
        this.rank = "Tortoise"
    }
}
}
</script>

<style>
.rank{
    font-size: 1.4em;
    color: green;
    font-weight: bold;
}
</style>