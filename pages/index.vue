<template>
  <qrcode-stream @decode="onDecode" />
</template>

<script>
import { QrcodeStream } from 'vue-qrcode-reader'
export default {
  components: {
    QrcodeStream
  },
  methods: {
    onDecode () {
      this.$router.replace('./form')
    }
  }
}
</script>
