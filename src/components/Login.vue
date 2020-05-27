<template>
<div>
  <section class="form-simple">
    <mdb-row>
      <mdb-col md="5">
        <mdb-card>
          <div class="header pt-3 grey lighten-2">
            <mdb-row class="d-flex justify-content-start">
              <h3 class="deep-grey-text mt-3 mb-4 pb-1 mx-5">Log in</h3>
            </mdb-row>
          </div>
          <form>
          <mdb-card-body class="mx-4 mt-4">
            <mdb-input label="Your email" type="text" required/>
            <mdb-input label="Your password" type="password" containerClass="mb-0"  required/>
            <div class="text-center mb-4 mt-5">
             <a href="https://saravanakumark.000webhostapp.com/" ><mdb-btn color="danger" type="button" class="btn-block z-depth-2">Log in</mdb-btn></a>
            </div>
           
           
          </mdb-card-body>
           </form>
        </mdb-card>
      </mdb-col>
    </mdb-row>
  </section>
   <ul>
        <li v-for="todo of todos"  :key="todo.id"> 
            {{ 'Narmatha'==(todo.name)
                
             }}</li>
            
    </ul>
    </div>
</template>
<script>
import axios from 'axios';
  import { mdbRow, mdbCol, mdbCard, mdbCardBody, mdbInput, mdbBtn } from 'mdbvue';
  export default {
    name: 'FormsPage',
    components: {
      mdbRow,
      mdbCol,
      mdbCard,
      mdbCardBody,
      mdbInput,
      mdbBtn,
      
    },
    data(){
        return{
            todos:[],
            
        } 
    },
     async created()
    {
     
      const res =await axios.get('http://localhost:3000/todos');
    this.todos=res.data;
    
    },
  }
</script>
<style>
  .form-simple .font-small {
    font-size: 0.8rem; }

  .form-simple .header {
    border-top-left-radius: .3rem;
    border-top-right-radius: .3rem; }

  .form-simple input[type=text]:focus:not([readonly]) {
    border-bottom: 1px solid #ff3547;
    -webkit-box-shadow: 0 1px 0 0 #ff3547;
    box-shadow: 0 1px 0 0 #ff3547; }

  .form-simple input[type=text]:focus:not([readonly]) + label {
    color: #4f4f4f; }

  .form-simple input[type=password]:focus:not([readonly]) {
    border-bottom: 1px solid #ff3547;
    -webkit-box-shadow: 0 1px 0 0 #ff3547;
    box-shadow: 0 1px 0 0 #ff3547; }

  .form-simple input[type=password]:focus:not([readonly]) + label {
    color: #4f4f4f; }
    .form-simple{
      margin-left: 13cm;
     
    }
</style>
