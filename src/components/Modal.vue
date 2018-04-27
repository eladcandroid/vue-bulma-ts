<template>
  <div class="modal is-active">
    <div class="modal-background"></div>
    <div class="modal-content box">
      <slot></slot>
      check
    </div>
    <button @click="closeModal()" class="modal-close is-large" aria-label="close"></button>
  </div>
</template>

<script lang="ts">
  import { Component, Prop, Vue } from 'vue-property-decorator';

  @Component
  export default class HelloWorld extends Vue {
    @Prop() private msg!: string;
    public closeModal() {
      this.$emit('close', 'check');
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '~bulma/sass/utilities/initial-variables';
  
  $modal-background-background-color: $blue;
  
  @import '~bulma/bulma';
</style>
