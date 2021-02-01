<template>
  <div>
    <p class="title">Component {{index}}</p>
    <v-row>
      <v-btn @click="showModal">Button 1</v-btn>
      <v-btn @click="showModal">Button 2</v-btn>
      <v-btn @click="showModal">Button 3</v-btn>
      <Modal :text="dataComp" :show="dialog" @hide="hideDialog"/>
    </v-row>
  </div>
</template>

<script>
import Modal from '@/components/Modal.vue'
import showModal from '@/mixins/showModal.js'
export default {
  name: 'ParentComp',
  components: {
    Modal
  },
  props: {
    text: {
      type: String,
      default: ''
    },
    index: {
      type: Number,
      default: 1
    }
  },
  mixins: [showModal],
  data() {
    return {
      dataComp: this.text
    }
  },
  methods: {
    hideDialog() {
      this.dialog = false
    }
  }
}
</script>