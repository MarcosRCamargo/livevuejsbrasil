<template>
<div>
  <h1>Minha Lista</h1>
  <input 
    id="addfoodselement"
    @keyup.enter="addFood"
    type="text" v-model="currentFood">
  <button @click="addFood">Add</button>
  <food-list
  @My-event="handleClick" 
  :foods="foods"
  />
</div>

</template>

<script>
// import FoodList from './components/FoodList'
import FoodList from './components/FoodList.vue';
export default {
  components: {FoodList},
  data: () => ({
  name: "Marcos Camargo",
  color: "tomato",
  foods: ['Maça', 'Pera'],
  }),
  methods:{
    handleClick(){
      window.alert('Clicado!')
    },
    addFood(){
      window.alert(this.currentFood)
      if(this.currentFood === undefined && this.currentFood === null && this.currentFood === ''){
        window.alert('É informe uma comida')
        this.$refs.addfoodselement.focus()
      }
      this.foods.push(this.currentFood)
      this.currentFood = ''
    }
  }
};
</script>
