<template>
    <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
    <div> 
      <p> {{ ScannData }}</p>
    </div>
</template>

<script>
import { StreamBarcodeReader } from "vue-barcode-reader";

export default {
  data() {
    return {
      ScannData: "text",
     Kreide: {
      name: "Atla", Qualität: "für alle Tafeln geeignet"
      }
    }
  },
  components: {
    StreamBarcodeReader
  },
   methods: {
     onDecode (result) { 
      this.ScannData = result;
      console.log(result) 
      if(result == "4059549000152"){
        console.log("funktioniert");
      }  
    }
  }
}
</script>

<style >
</style>
