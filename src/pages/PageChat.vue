<template>
  <q-page class="flex column">
     <q-banner inline-actions class=" bg-grey-4 text-center">
          user is offline
    </q-banner>
    <div class="q-pa-md column col justify-end">
       <q-chat-message
       v-for="message in messages"
       :key="message.text"
       :name="message.from"
       :text="[message.text]"
       :sent="message.from=='me'?true :false"
      />
    </div>
   <q-footer elevated >
        <q-toolbar>
          <q-form 
            
          class="full-width" >
             <q-input
           v-model="newMessage" 
            label="message" 
             dense 
             bg-color="white" 
             rounded
             outlined
            >
          <template v-slot:after>
          <q-btn 
          type="submit"
          dense 
          flat 
          color="white"
          @click="sendMessage"
          icon="send" />
          </template>
          </q-input>
        </q-form>
        </q-toolbar>
      </q-footer>
  </q-page>
</template>
<script>
export default {
  data(){
    return{
      newMessage:'',
      messages:[
                  {
                    text:'hey himal how are you',
                    from:'me'
                  },
                  {
                    text:'I am fine and you',
                    from:'them'
                  },
                  {
                    text:'also fine',
                    from:'me'
                  },
              ]
          }
         },
  methods:{
    sendMessage(){
     this.messages.push({
                        text: this.newMessage,
                        from: 'me'
                       })
                       this.newMessage=''
                  }
  }

               }
</script>