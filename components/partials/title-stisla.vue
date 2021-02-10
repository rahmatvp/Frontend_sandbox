<template>
  <div>
    <div class="section-header">
      <h1>{{ title }}</h1>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: { // mengambil nilai title agar dynamis
      type: String,
      default: 'Ini Judul halaman'
    }
  }
}
</script>
