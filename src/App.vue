<template>
    <div> 
      <h1> Barcode App</h1>
      <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
      <p> deine gescannte Information: {{ ScannData }}</p>
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
      if(result == "4059549000152"){
        console.log(this.Kreide);
      }  
    }
  }
}
</script>

<style >
</style>
