<template>

<div class="container">
<br><br>
   <input type="text" v-model="message">
t {{message}}
code : {{code}}
    <vue-qrcode :value="code" /><br> <br>

    <!--<input type="button"  class="btn btn-primary" @click="enregistrer" value="enregistrer"> -->

  </div>

</template>

<script>
import VueQrcode from 'vue-qrcode';


export default{
    
    components: {VueQrcode},

    data() {
    return {
        message: ''
    }
    },
    props: {
        code: String,
        description: String
    },
    
    }
    
   


 
</script>