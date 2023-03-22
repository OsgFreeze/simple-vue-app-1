<template>
    <div> 
      <h1> Barcode App</h1>
      <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
      <div> 
        <p> deine gescannte Information: {{ ScannData }}</p>
      </div>

      <div> 
          <img src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T1/images/I/61MypS1KawL._AC_SS450_.jpg" /> 
      </div>
    </div>
</template>

<script>
import { StreamBarcodeReader } from "vue-barcode-reader";
export default {
  data() {
    return {
      ScannData: "text",
      Datenbank: { 
        4059549000152: {
          name: "Atla", Qualität: "für alle Tafeln geeignet"
       }
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
        console.log(this.Datenbank[4059549000152]);
      }  
    }
  }
}
</script>

<style >
</style>
