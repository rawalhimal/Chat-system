<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          @click="leftDrawerOpen = !leftDrawerOpen"
          icon=""
          aria-label="Menu"
        />
    <q-btn
    v-go-back.single
     icon="arrow_back" 
     label="back" 
     flat
     dense
     />
        <q-toolbar-title class="absolute-center">
         {{title}}
        </q-toolbar-title>
      </q-toolbar>
        <q-btn
     to="/auth"
     icon="account_circle" 
     class="absolute-right q-mr-sm "
     no-caps
     label="LogIn" 
     flat
     dense
     />
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  data () {
    return {
   
    }
  },
  computed:{
         title(){
    let currentPath=this.$route.fullPath
    if(currentPath=='/') return 'Himal Chat'
    else if(currentPath=='/chat') return 'Chat'
    else if(currentPath=='/auth') return 'Auth'
  }
  }
  
}
</script>
