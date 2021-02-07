<template>
  <div class="clearAllContainer">
      <span class="clearAllBtn" v-on:click="clearTodo">
          Clear All
      </span>
  </div>
</template>

<script>
export default {
    methods: {
        clearTodo(){
            this.$emit('clearTodo');
        }, 
    }
}
</script>

<style scoped>
    .clearAllContainer {display: block; width: 8.5rem; height: 50px; line-height: 50px; background: #fff; border-radius: 5px; margin: 0 auto; cursor: pointer;}
    .clearAllBtn {color: #e20303; display: block;}
</style>