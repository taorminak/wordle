<template>
  <div class="keyboard">
    <div v-for="(row, index) in rows" :key="index" class="row">
      <div v-if="index === 2" class="special-keys">
        <div class="key service-buttons" @click="handleSpecialKeyClick('enter')">Enter</div>
      </div>
      <div v-for="key in row" :key="key" class="key" @click="handleKeyClick(key)">
        {{ key }}
      </div>

      <div v-if="index === rows.length - 1" class="special-keys">
        <div class="key service-buttons delete" @click="handleSpecialKeyClick('delete')">
          <img class="delete_key" src="../../src/assets/img/delete-key.png" alt="delete" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const ROWS = ['qwertyuiop', 'asdfghjkl', 'zxcvbnm']

export default {
  name: 'Keyboard',
  data() {
    return {
      rows: ROWS
    }
  },
  methods: {
    handleKeyClick(key) {
      console.log('Regular key clicked:', key)
    },
    handleSpecialKeyClick(type) {
      console.log('Special key clicked:', type)
      if (type === 'delete') {
        this.deleteChar()
      } else if (type === 'enter') {
        this.enterAction()
      }
    },
    deleteChar() {
      console.log('Deleting character...')
    },
    enterAction() {
      console.log('Enter action...')
    }
  }
}
</script>

<style scoped>
.keyboard {
  display: flex;
  padding: 10px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: white;
}

.row {
  display: flex;
  justify-content: center;
  margin: 10px 0;
}

.key {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50px;
  height: 50px;
  background-color: white;
  color: black;
  font-family: system-ui, sans-serif;
  font-size: 16px;
  margin: 0 5px;
  cursor: pointer;
  border-radius: 10%;
  transition: all 0.2s ease-in-out;
}

.key:hover {
  background-color: #f7c9c9;
  color: white;
}

.key:active {
  border-radius: 50%;
  background-color: #f09394;
  color: white;
}

.service-buttons {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50px;
  height: 50px;
  background-color: white;
  color: black;
  font-family: system-ui, sans-serif;
  font-size: 16px;
  margin: 0 5px;
  cursor: pointer;
  border-radius: 10%;
  transition: all 0.2s ease-in-out;
}

.service-buttons:hover {
  background-color: #f7c9c9;
  color: white;
}

.service-buttons:active {
  border-radius: 50%;
  background-color: #f09394;
  color: white;
}

.delete {
  border-radius: 5px;
  font-size: 12px;
  width: 70px;
}

.enter {
  border-radius: 5px;
  font-size: 12px;
  width: 70px;
}

img.delete_key {
  height: 40px;
}
</style>
