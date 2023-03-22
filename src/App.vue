<template>
    <div> 
      <h1> Barcode App</h1>
      <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded" id="readerID"></StreamBarcodeReader>
    </div>

    <div id="div2ID">
      <button id="ButtonID"> Recognized </button>
      <p id="ScannDataID"> Information: {{ ScannData }}</p>
    </div>

    <div id="ProduktFensterID" v-if="visible==true"> 
      <img id="ProductPictureID" src="https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T1/images/I/61MypS1KawL._AC_SS450_.jpg" /> 
      {{ Datenbank[4059549000152] }}
    </div>
    
</template>

<script>
import { StreamBarcodeReader } from "vue-barcode-reader";
export default {
  data() {
    return {
      ScannData: "text",
      visible: false,
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
        this.visible=true;
      }  
    }
  }
}
</script>

<style >
#readerID {
  background-color: brown;
}
#ProductPictureID {
  width: 150px;
  height: 150px;
}
#ButtonId{
  color:green;
  text-align: left;
}
#ProduktFensterID {
  background-color: blue;
}
#div2ID {
  display: flexbox;
  flex-direction: row
}

</style>
