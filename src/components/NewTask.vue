<template>
  <div class="new-task">
      <input v-model='name' @keydown.enter='add' type="text" class="input-element">
      <button @click='add' class="btn">+</button>
  </div>
</template>

<script>
export default {
    data(){
        return {
            name: ''
        }
    },
    methods: {
        add(){
            this.$emit('taskAdded', { name: this.name })
            this.name = ''
        }
    }
}
</script>

<style>
    .new-task {
        width: 100%;
        display: flex;
        justify-content: center;
        margin-bottom: 20px;
    }
    .input-element {
        outline: none;
        width: 70%;
        padding: 5px 10px 8px;
        font-size: 2rem;
        border: 1px solid #fff;
        background: rgba(255, 255, 255, .3);
        border-top-left-radius: 8px;
        border-bottom-left-radius: 8px;
    }

    .btn {
        background: rgba(28, 189, 230, 0.8);
        border: 1px solid #fff;
        border-left: none;
        border-top-right-radius: 8px;
        border-bottom-right-radius: 8px;
      
    }
</style>