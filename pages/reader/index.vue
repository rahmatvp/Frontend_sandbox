<template>
    <div>
        <title-stisla title="Reader" />
        <skeleton>
          <div class="row">
            <div class="col-4">
              <input-add-reader @ValueInput="(val) => this.books.push(val)"  name="Judul Buku" :val="inputBook"/>
              <ul class="list-group m-3">
              <li v-for="(book,i) in books" :key="i" class="list-group-item d-flex justify-content-between align-items-center rounded-pill mt-2">
                {{ book }}
                <button type="buton" class="btn btn-outline-danger rounded-pill" @click="showModal('book',book,i)"> 
                  <i class="fas fa-minus" />
                </button>
              </li>
            </ul>
            </div>
          <div class="col-4">
              <input-add-reader @ValueInput="(val) => this.Names.push(val)" name="Nama Pembaca" :val="inputNama"/>
              <ul class="list-group m-3">
              <li v-for="(nama,i) in Names" :key="i" class="list-group-item d-flex justify-content-between align-items-center rounded-pill mt-2">
                {{ nama }}
                <button type="buton" class="btn btn-outline-danger rounded-pill" @click="showModal('name',nama,i)">
                  <i class="fas fa-minus" />
                </button>
              </li>
            </ul>
            </div>

           <div class="col-4">
               <selection :valbook="books" 
                          :valname="Names" 
                           namebook="Nama buku"
                           namePembaca="Nama Pembaca"
                          @valueData="(valbook,valname) => this.dataPembaca.push([valbook,valname])"
                          />
               
               <ul class="list-group m-3">
               <li v-for="(secbook,i) in dataPembaca" :key="i" class="list-group-item d-flex justify-content-between align-items-center rounded-pill mt-2">
                {{ secbook[0] }}
                <button type="buton" class="btn btn-outline-danger rounded-pill" @click="showModal('pembaca',secbook[0],i)">
                  <i class="fas fa-minus" />
                </button>
              </li>
            </ul>
          </div>

          </div>
        </skeleton>
    </div>
</template>

<script>
import InputAddReader from '../../components/form/input-addReader.vue'
import skeleton from '../../components/partials/skeleton.vue'
import swal from 'sweetalert'
export default {

  components: { skeleton, InputAddReader },

  data () {
    return {
      books: [],
      Names : [],
      inputNama : '',
      inputBook :'',
      dataPembaca : []
    }
  },
   methods: {
    setValue (val) {
      this.books.push(val)
    },
    removeBooks (index) {
      this.books = this.books.filter((book, i) => i !== index)
    },
     removeNames (index) {
      this.Names = this.Names.filter((nama, i) => i !== index)
    },
   removeData (index) {
      this.dataPembaca = this.dataPembaca.filter((secbook, i) => i !== index)
    },
  
   showModal(hapus,data,i){

        swal({
        title: "Apakah Kamu Yakin",
        text: "Hapus "+ data,
        icon: "warning",
        buttons: true,
        dangerMode: true,
      })
      .then((willDelete) => {
        if (hapus == "book") {
          this.removeBooks(i)
        }else if(hapus == "name") {
          this.removeNames(i)
        }else{
          this.removeData(i)
        }
        //   swal("Poof! Your imaginary file has been deleted!", {
        //     icon: "success",
        //   });
        // } else {
        //   swal("Your imaginary file is safe!");
        // }
      });

    }

  }
    
}
</script>