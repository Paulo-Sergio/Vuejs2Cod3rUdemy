<template>
  <div class="task" :class="stateClass">
    <p>{{ task.name }}</p>
  </div>
</template>

<script>
export default {
  props: {
    task: { Type: Object, required: true }
  },
  computed: {
    stateClass() {
      return {
        pending: this.task.pending,
        done: !this.task.pending
      };
    }
  }
};
</script>

<style>
.task {
  box-sizing: border-box;
  width: 250px;
  height: 100px;
  padding: 10px;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 300;
  cursor: pointer;
  user-select: none;
  display: flex;
  justify-content: center;
  align-items: center;
}
.pending {
  border-left: 12px solid #B73229;
  background-color: #F44336;
}
.done {
  color: #DDD;
  border-left: 12px solid #0A8F08;
  background-color: #4CAF50;
}
</style>
