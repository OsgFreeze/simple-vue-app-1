<template>
    <div> 
      <h1> Barcode App</h1>
      <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded" id="readerID"></StreamBarcodeReader>
    </div>

    <div id="div2ID">
      <button id="ButtonID"> Recognized </button>
      <p id="ScannDataID" style="padding-left: 30px"> Information: {{ ScannData }}</p>
    </div>

    <div id="ProduktFensterID" v-if="visible==true"> 
      <div > 
        <img id="ProductPictureID" src='https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T1/images/I/61MypS1KawL._AC_SS450_.jpg' /> 
      </div>
      <div id="Info"> 
       Produktname: {{ Datenbank[4059549000152].name }}
       Preis: {{ Datenbank[4059549000152].preis }}
      </div>
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
          name: "Atla", preis: "1,99€", bildURL: "https://m.media-amazon.com/images/W/IMAGERENDERING_521856-T1/images/I/61MypS1KawL._AC_SS450_.jpg"
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
        document.getElementById("ButtonID").style.background='#008000';
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
#ButtonID{
  background-color:rgb(128, 0, 0);
  text-align: left;
}
#ProduktFensterID {
  display: flex;
  flex-direction: row;
  padding-top: 20px;
}

#Info{
  text-align: center;
}

#div2ID {
  display: flex;
  flex-direction: row;
  padding-top: 20px;
}

</style>
