<template>
  <div> 
    <MyInput :place-holder="placeHolder"></MyInput>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';


interface MyInput {
  placeHolder: string | null;
}

export default Vue.extend({
  layout: 'custom-layout',
  data(): {
    placeHolder: MyInput['placeHolder']
  } {
    return {
      placeHolder: "23"
    }
  }
});
</script>

<style scoped>
  /* Стили, если они нужны, должны быть здесь */
</style>