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
    }
  },
  components: {
    StreamBarcodeReader
  },
   methods: {
     onDecode (result) { 
      this.ScannData = result;

      console.log(result) } 
    }
}
</script>

<style >
</style>
