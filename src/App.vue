<template>
  <header>
      <HelloWorld />
      <StreamBarcodeReader
      @decode="onDecode"
      @loaded="onLoaded"
      ></StreamBarcodeReader>
  </header>
</template>

<script>
import HelloWorld from './components/Scanner.vue'
import { StreamBarcodeReader } from "vue-barcode-reader";

export default{
  data() {
        return {
          data: 0
        }
      },
      methods() {
      },
  }
</script>

<style >
</style>
