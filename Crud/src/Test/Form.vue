<template>
     <div>
          <form>
               <input type="text" v-model="formdata.name" name="name" placeholder="name" />
               <input type="text" placeholder="phone" name="phone" v-model="formdata.phone" />
               <button @click="postdata">Submit</button>
          </form>
          <div>
               <h1>Get all data</h1>
               <div v-for="el in data" :key='el.id'>
                    <p>{{ el.name }}</p>
                         <p>{{ el.phone }}</p>
                         <button @click="deletedata(el.id)">delete</button>
                              <button>edit</button>
               </div>
          </div>
     </div>
</template>

<script>
import axios from "axios";

export default {
     data() {
          return {
               formdata: {
                    name: "",
                    phone: "",
               },
               data: null,
          };
     },

     mounted() {
          this.getall();
     },

     methods: {

          getall() {
               axios.get("http://localhost:3000/user").then((res) => {
                    this.data = res.data;
                    console.log(res.data);
               });
          },

          postdata(e) {
               e.preventDefault();
               axios.post("http://localhost:3000/user", this.formdata).then((res) => {
                    console.log(res.data);
                    this.getall();
               });
          },

         

// delete functionality here

          deletedata(id) {
               axios.delete(`http://localhost:3000/user/${id}`).then((res) => console.log(res));

               this.getall();
          }

// edit functionality here

     },
};
</script>
