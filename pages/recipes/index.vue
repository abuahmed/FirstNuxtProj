<template>
  <section id="recipes">
    <Recipe
      v-for="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText" />

    
  </section>
</template>

<script>
import Recipe from "@/components/Recipe"
export default {
    components: {
        Recipe
    },
    asyncData(){
      return new Promise((resolve,reject)=>{
        setTimeout(() => {
          resolve({
            recipes:[
              {
                id:"1",
                title:"Title1",
                previewText:"Some nice preview text",
                thumbnail:"https://theculinaryaddict.com/wp-content/uploads/2019/10/vegetables-italian-pizza-restaurant.jpg"
              },
                {
                id:"2",
                title:"Title2",
                previewText:"Some nice preview text2",
                thumbnail:"https://www.baconismagic.ca/wp-content/uploads/2019/01/lisbon-food-arroz-con-marisco-768x1152.jpg"
              },
            ]
          })
        }, 0);
      })

    }
}   
</script>

<style scoped>
/* .container
{
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
} */
#recipes{
  padding-top: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
@media (min-width: 35rem) {
    #recipes{
        flex-direction: row;
    }
}
</style>