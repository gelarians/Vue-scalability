<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <p class="lead">Hallo aus der HomePage.vue :)</p>
        <button 
            class="btn btn-primary"
            @click="openDialog"
        
        >Dialog anzeigen</button>
        <Dialog 
        :timeout=6000
        :type="'danger'"
        @close="closeDialog"
        v-if="showDialog">
            <template v-slot:header>
                <div>
                    <h3>Slot Gefüllt</h3>
                </div>
            </template>
            <template v-slot:body>
                <div>
                    <p>Sie haben sich erfolgreich eingeloggt</p>
                </div>
            </template>
        </Dialog>
      </div>
    </div>
  </div>
</template>

<script>
import Dialog from "../components/Dialog.vue"
export default {
  name: "HomePage",
  data(){
    return {
        showDialog: false
    }
},
  components: {
      Dialog,
    },
    methods: {
        openDialog(){
            this.showDialog = true
        },
        closeDialog(){
            this.showDialog = false
        }
    }
};
</script>

<style>
</style>