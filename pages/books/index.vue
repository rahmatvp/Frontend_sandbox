<template>
  <div>
    <title-stisla title="Daftar Buku" />
    <skeleton>
      <input-add @valueJudulBuku="(val) => this.books.push(val)" />
      <!-- <p>{{ books }}</p> -->
      <ul class="list-group m-3">
        <li v-for="(book,i) in books" :key="i" class="list-group-item d-flex justify-content-between align-items-center rounded-pill mt-2">
          {{ book }}
          <button type="buton" class="btn btn-outline-danger rounded-pill" @click="remove(i)">
            <i class="fas fa-minus" />
          </button>
        </li>
      </ul>
    </skeleton>
  </div>
</template>
<script>
export default {
  data () {
    return {
      books: []
    }
  },
  methods: {
    setValue (val) {
      this.books.push(val)
    },
    remove (index) {
      this.books = this.books.filter((book, i) => i !== index)
    }
  }
}
</script>
