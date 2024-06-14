<template>
  <div v-if="show" class="modal">
    <div class="modal-overlay">
      <div class="modal-content">
        <div class="modal-header">
          <h2 class="modal_title">How To Play</h2>
          <button type="button" class="btn-close" @click="close">×</button>
        </div>

        <h3>Guess the Wordle in 6 tries.</h3>
        <ul>
          <li>Each guess must be a valid 5-letter word.</li>
          <li>The color of the tiles will change to show how close your guess was to the word.</li>
        </ul>

        <h3>Examples</h3>

        <ol class="modal_examples">
          <li><strong>W</strong> is in the word and in the correct spot.</li>
          <div class="examples_picture">
            <img
              class="modal_example"
              src="../../src/assets/img/wordle1_right.png"
              alt="right letter in right place"
            />
          </div>

          <li><strong>I</strong> is in the word but in the wrong spot.</li>
          <div class="examples_picture">
            <img
              class="modal_example"
              src="../../src/assets/img/wordle1_not_right.png"
              alt="right letter in wrong place"
            />
          </div>

          <li><strong>U</strong> is not in the word in any spot.</li>
          <div class="examples_picture">
            <img
              class="modal_example"
              src="../../src/assets/img/wordle1_wrong_place.png"
              alt="wrong letter"
            />
          </div>
        </ol>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    show: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    close() {
      this.$emit('close')
    }
  }
}
</script>

<style scoped>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 10;
}

.modal-content {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  gap: 20px;
  background: white;
  padding: 20px;
  border-radius: 2%;
  position: relative;
  max-height: 70%;
  width: 70%;
  max-width: 500px;
  padding: 40px 30px;
}

.btn-close {
  position: absolute;
  top: 15px;
  right: 15px;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
}

.modal_title {
  font-weight: 700;
}

.modal_example {
  height: 50px;
}

.modal_examples {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.examples_picture {
  display: flex;
  padding-left: 20px;
  align-items: center;
}
</style>
