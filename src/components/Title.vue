<template>
  <div class="header_title">
    <div>Welcome to Wordle!</div>
    <div class="header_rules">
      For reading the rules, click <a href="#" @click.prevent="openModal">here</a>
    </div>
  </div>
  <ModalWithRules v-if="isModalOpen" @close="closeModal" />
</template>

<script>
import ModalWithRules from './ModalWithRules.vue'
export default {
  components: {
    ModalWithRules
  },
  data() {
    return {
      isModalOpen: false
    }
  },
  methods: {
    openModal() {
      this.isModalOpen = true
    },
    closeModal() {
      this.isModalOpen = false
    }
  }
}
</script>

<style scoped>
.header_title {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-size: 24px;
  font-style: italic;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-weight: 900;
}

.header_rules {
  font-size: 14px;
}
</style>
