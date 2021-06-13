<template>
  <ul>
    <li v-for="(food, index) in foods" 
    :key="`${food}-${index}`">
      {{ food }}
    </li>
  </ul>
</template>
<script>

const MAX_FOOD  = 5;

export default ({
    props: {
        foods: { type: Array, default: () => [] }
    },
    watch:{
      foods (){
        if(this.foods.length >= MAX_FOOD){
          this.$emit('stop', 'Marcos Falou que ta cheio');""
        }
        console.log('chenged', this.foods.length)
      }
    }
})
</script>
