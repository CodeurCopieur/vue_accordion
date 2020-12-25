<template>
  <div :class="open ? 'faq open': 'faq'" @click="$emit('toggleOpen', index)">
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
   props: ['faq', 'index', 'open'],
   data: () => {
     return {}
   }
  }
</script>

<style lang="scss">
  
  .faq {
    display: block;
    cursor: pointer;
    width: 60%;
    margin: 30px auto;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, .2);
    background-color: #fff;
    transition: all .4s linear;

    &.open > .question {
      margin-bottom: 15px;
    }

    &.open > .question::after {
      transform: translateY(-50%) rotate(90deg);
    }

    &.open > .answer {
      opacity: 1;
      max-height: max-content;
    }

    .question {
      position: relative;
      color: #35495E;
      font-size: 20px;
      transition: all .4s linear;

      &::after {
        content: "";
        position: absolute;

        top: 50%;
        right: 0;
        transform: translateY(-50%) rotate(0deg);

        width: 30px;
        height: 30px;

        background-image: url('../assets/img/arrow-down-mint.svg');
        background-position: center;
        background-size: contain;
        background-repeat: no-repeat;
        cursor: pointer;

        transition: all .4s linear;
      }
    }

    .answer {
      color: #41B883;
      font-size: 18px;
      opacity: 0;
      max-height: 0;
      overflow: hidden;
      transition: all .4s ease-in;
    }
  }
</style>