<template>
    <section class="single-recipe">
        <h1> {{ recipe.title }} </h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
        </div>
        <p>{{recipe.descriptionText}}</p>
    </section>
</template>

<script>
export default {
     asyncData(context){
      return new Promise((resolve,reject)=>{
        setTimeout(() => {
          resolve({
            recipe:[
              {
                id:"1",
                title:"Title1",
                previewText:"Some nice preview text",
                descriptionText:" Some nice description text description textdescription text ",
                thumbnail:"https://theculinaryaddict.com/wp-content/uploads/2019/10/vegetables-italian-pizza-restaurant.jpg"
              },
                {
                id:"2",
                title:"Title2",
                previewText:"Some nice preview text 2",
                descriptionText:"Some nice description text description textdescription text ",
                thumbnail:"https://www.baconismagic.ca/wp-content/uploads/2019/01/lisbon-food-arroz-con-marisco-768x1152.jpg"
              }
            ].find(e=>e.id===context.params.id)
          })
        }, 1500)
      })
}
}
</script>
<style scoped>
.single-recipe{
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}
.recipe-image{
    width: 100%;
    height: 300px;
}
</style>