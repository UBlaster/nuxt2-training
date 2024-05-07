<template>
<div>
  <form class="form">
    <div class="form__container">
      <input id="input" class="form__input" placeholder=" "/>
      <label for="input" class="form__label"> {{ placeHolder }} </label>
    </div>

  </form>

</div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue';


interface Test {
  placeHolder: string | null;
}

 export default Vue.extend({
props: {
  placeHolder: {
    type: [String, null] as PropType<Test['placeHolder']>,
    default: null
  }
}

});
</script>

<style scoped lang="scss">
.form {
  color: green;

  &__container {
    position: relative;
  }

  &__input {
    padding: .5rem; 
    border-radius: 8px;
    border: 3px solid black;
    outline: none;
  }

  &__input:focus , &__input:active {
    border: 3px solid green;
  }

  &__label {
    position: absolute;
    left: 0.5rem;
    top: 50%; 
    transform: translateY(-50%);
    transition: top 300ms ease-in,
    left 300ms ease-in;
  }


  &__input:focus ~ &__label, &__input:not(:placeholder-shown).form__input:not(:focus) ~ &__label {
    top: 0;
    left: 1rem;
    background-color: #FFFFFF;
  }
}
</style>