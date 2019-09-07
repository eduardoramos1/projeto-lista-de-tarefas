<template>
  <div class="task" :class="stateClass" @click="$emit('taskStateChange', task)">
      <span @click.stop="$emit('taskDeleted', task)" class="close">x</span>
      <p>{{ task.name }}</p>
  </div>
</template>

<script>
export default {
    props: {
        task: {
            type: Object,
            required: true
        }
    },
    computed: {
        stateClass(){
            return {
                pending: this.task.pending,
                done: !this.task.pending
            }
        }
    }
}
</script>

<style>
    .task {
        box-sizing: border-box;
        width: 300px;
        height: 150px;
        padding: 10px;
        margin: 5px;
        border-radius: 10px;
        font-size: 1.8rem;
        border: 1px solid black;
        font-weight: 350;
        cursor: pointer;
        user-select: none;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .done {
        color: rgb(194, 192, 192);
        text-decoration: line-through;
        border-left: 12px solid #087408;
        background: #099109;
        position: relative;
        
    }
    
    .pending {
        border-left: 12px solid #750e06;
        background: rgb(219, 17, 17);
        position: relative;
    }

    .pending .close{
        background: rgb(161, 11, 11);

    }

    .done .close {
        background: #087008;
    }

    .close {
        position: absolute;
        right: 10px;
        top: 10px;
        font-size: .9rem;
        font-weight: 650;
        height: 20px;
        width: 20px;
        border-radius: 10px;
        display: flex;
        justify-content: center;
    }
</style>