<template>
  <div class="note-card">
    <p>{{ title }}</p>
    <p>日期：{{ date }}</p>
  </div>
</template>

<script>
export default {
  name: 'NoteCard',
  props: {
    title: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.note-card {
  background-color: #F9F4E9;
  border-radius: 10px;
  padding: 15px;
  flex: 1;
  transition: all 0.3s ease;
}

.note-card:hover {
  border: 1px solid #E1BE97;
}

.note-card p:first-child {
  font-size: 1.5vh;
  color: black;
  margin-bottom: 10px;
}

.note-card p:last-child {
  font-size: 1vh;
  color: gray;
}
</style>
