<template>
 <div> 
    <title-stisla title="User" />
    <skeleton>
       <input-text :val="namaLengkap" name="Username" />
      </skeleton>
  </div>
</template>

<script>
import inputText from '../components/form/input-text.vue'
export default {
  components: { inputText },

  data(){
    return{
      nama : ' '
    }
  },

  computed :{
     namaLengkap (){
          const obj = {}
          const split = this.nama.split(' ');
          const firstName = split[0]
          const lastName = split[split.length - 1]

          obj.FullName = "FirstName : "+ firstName + " LastName : " + lastName;

          return firstName
     }
  }
}

</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
