<template>
  <div>
           <div class="progress">
                  <div class="bar" :style="{
                        width:`${(barInformation.answerdQuestion/barInformation.totalQuestion)*100 }%`
                  }"></div>
                  <div class="status">{{ barInformation.answerdQuestion }} out of {{ barInformation.totalQuestion }} questions answered</div>
            </div>
  </div>
</template>

<script>
export default {
      name:"barComponent",
      props:{
            barInformation:Object
      }
}
</script>

<style>

</style>