<template>
  <div class="container_faq">
    <div class="question">
      {{ faq.question}}
    </div>
    <div class="answer">
      {{ faq.answer}}
    </div>
  </div>
</template>

<script>
 export default {
   name: 'Faq',
   props: ['faq', 'index'],
   data: () => {
     return {}
   }
  }
</script>

<style lang="scss" scoped>
  
</style>