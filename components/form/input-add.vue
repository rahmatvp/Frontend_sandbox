<template>
  <div class="input-group">
    <input v-model="inputBook" type="text" placeholder="Judul Buku" class=" form-control rounded-pill m-3" @keyup.enter="add">
    <div class="input-group-append">
      <button class="btn btn-outline-primary rounded-pill m-3" @click="add">
        <i class="fas fa-plus" />
      </button>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      inputBook: ''
    }
  },

  methods: {
    add () {
      this.$emit('valueJudulBuku', this.inputBook)
      this.inputBook = ''
    }
  }
}
</script>
