<template>
  <div class="task-progress">
      <span class="progress-value">{{ progress }}%</span>
      <div class="progress-bar" :style="{width: progress + '%'}"></div>
  </div>
</template>

<script>
export default {
    props: {
        progress: { type: Number, default: 0 }
    }
}
</script>

<style>
    .task-progress {
        position: relative;
        background: rgba(144, 144, 209, 0.6);
        width: 70%;
        margin: 20px 0;
        text-align: center;
        height: 25px;
        border: 1px solid rgba(255,255,255,.4);
        border-radius: 12px;
    }

    .progress-value {
        position: relative;
        z-index: 1;
    }

    .progress-bar {
        position: absolute;
        top:0;
        bottom: 0;
        background: green;
        border-radius: 12px;
        
    }
</style>