<template>
    <div>
        <div class="row">
            <div class="col-9">
                <select id="inputSelect" v-model="dataBook" class="form-control mt-3 mr-3 rounded-pill">
                    <option value ="">{{namebook}} </option>
                    <option v-for="(book,index) in valbook" :key="index" :value="book">
                        {{ book }} 
                    </option> 
                </select>

                 <select id="inputSelect" v-model="dataName" class="form-control mt-3 mr-3 rounded-pill">
                    <option value =""> {{namePembaca}}  </option>
                    <option v-for="(name,index) in valname" :key="index" :value="name">
                        {{ name }} 
                    </option> 
                </select>
            </div>
            <div class="col-3 mt-2">
               <button class="btn btn-outline-primary rounded-pill px-3 py-5" @click="showModal(dataName,dataBook)">
                    <i class="fas fa-plus" />
                </button>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    props :{
        valbook :{
            type : Array,
            default : () => []
        },
          valname:{
            type : Array,
            default : () => []
        },
        namebook:{
            type : String,
            default : "Nama Buku"
        },
        namePembaca:{
            type : String,
            default : "Nama Pembaca"
        }

    },
    data() {
        return{
            dataBook : '',
            dataName : '',
            myModal : false
            }
    },

   methods: {
    add () {
      if(this.dataName && this.dataBook)
      this.$emit('valueData',this.dataName + ' - ' + this.dataBook)
        
     },

     showModal(name, book){
          swal({
                title: "Apa Kamu Yakin?",
                text: name + " Membaca buku "+book,
                icon: "warning",
                buttons: true,
                dangerMode: true,
            })
            .then((willAdd) => {
                if (willAdd) {
                this.add()
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