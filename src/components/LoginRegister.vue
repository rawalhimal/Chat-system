<template>
 <q-form @submit="submitForm">
     <q-input 
     v-if="tab=='Register'"
     outlined 
     class="q-pa-md"
     v-model="formData.name" 
     label="Name" />
       <q-input 
     outlined 
     class="q-pa-md"
     v-model="formData.email" 
     label="Email" />
       <q-input 
     outlined 
     class="q-pa-md"
     v-model="formData.password" 
     label="Password" />
     <div class="row">
     <q-space/>
     <q-btn
      color="primary" 
      :label="tab" 
      type="submit"/>
     </div>
       
 </q-form>
</template>
<script>
export default {
    props:['tab'],
    data(){
        return{
            formData:{
                name:'',
                email:'',
                password:''
            }
        }
    },
    methods:{
        submitForm(){
            if(this.tab=='Login')
            console.log('login sucess')
            else
            console.log('register success')
        }
    }
}
</script>