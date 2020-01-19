<template>
  <q-page class="flex q-pa-md">
    <q-card class="full-width">
        <q-tabs
          v-model="tab"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
        >
          <q-tab name="Login" label="Login" />
          <q-tab name="Register" label="Register" />
        </q-tabs>

        <q-separator />

        <q-tab-panels v-model="tab" animated>
          <q-tab-panel name="Login">
            <Login-Register :tab="tab"/>
          </q-tab-panel>

          <q-tab-panel name="Register">
           <Login-Register :tab="tab"/>
          </q-tab-panel>
        </q-tab-panels>
      </q-card>
  </q-page>
</template>
<script>
export default {
   data () {
    return {
      tab: 'Login'
    }
  },
  components:{
    'Login-Register':require('components/LoginRegister.vue').default
  }

}
</script>