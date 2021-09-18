<template>
  <div>
    <v-text-field v-model="val" class="input-type1" @keyup.enter="addTodo">
      <v-icon slot="append" color="red" @click="addTodo"> mdi-plus </v-icon>
    </v-text-field>
  </div>
</template>

<script>
export default {
  data() {
    return {
      val: '',
    }
  },
  methods: {
    addTodo() {
      if (this.val !== '') {
        const obj = { todo: this.val, completed: '' }
        localStorage.setItem(this.val, JSON.stringify(obj))
        this.val = ''
      } else {
        alert('할 일을 입력해주세요.')
      }
    },
  },
}
</script>

<style scope>
.input-type1 {
  width: 20rem;
  margin: 0 auto;
}
</style>
