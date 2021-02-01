<template>
  <v-dialog
    v-model="showDialog"
    max-width="290"
  >
    <v-card>
      <v-card-title class="headline">
        Modal
      </v-card-title>
      <v-card-text>{{text}}</v-card-text>
    </v-card>
  </v-dialog>
</template>
<script>
import showModal from '@/mixins/showModal.js'
export default {
  name: 'Modal',
  props: {
    text: {
      type: String,
      default: ''
    },
    show: {
      type: Boolean,
      default: false
    }
  },
  mixins: [showModal],
  data() {
    return {
      showDialog: false
    }
  },
  watch: {
    show: function (val) {
      this.showDialog = val
    },
    showDialog: function (val) {
      if (!val) {
        this.$emit('hide', false)
      }
    }
  }
}
</script>