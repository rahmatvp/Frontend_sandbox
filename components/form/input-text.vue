<template>
  <div>
    <div :class="addClass">
      <label for="inputEmail"> input :   {{ name }}</label>
      <input
        id="inputEmail"
        v-model="val"
        :type="type"
        class="form-control"
        :placeholder="'input '+ name"
      >
      <p>{{ val }}</p>
    </div>
  </div>
</template>
<script>
export default {
 props: {
    addClass: {
      type: String,
      deafult: 'col-12'
    },
    name: {
      type: String,
      deafult: 'Text'
    },
    val: {
      type: String,
      default: 'input Text'
    },

    type: {
      type: String,
      default: 'text'
    }
  }
}
</script>