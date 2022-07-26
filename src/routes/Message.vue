<template>
  <div
    v-for="(msg, index) in msgs"
    :key="index"
    class="container">
    <div 
      class="box"
      :class="[ index % 2 === 0 ? 'message-blue' : 'message-orange' ]">
      <p class="message-content">
        {{ msg.context }}
      </p>
      <div class="message-timestamp">
        {{ msg.name }}
      </div>
    </div>
  </div>
  <div
    v-if="isLoading"
    class="spinner-border text-danger"
    role="status">
  </div>
</template>

<script>
import axios from 'axios'
// import msgs from './msg.js'

export default {
  data() {
    return {
      msgs: {},
      isLoading: false
    }
  },
  created() {
    this.getMessage()
  },
  methods: {
    async getMessage(){
      try {
        this.isLoading=true
        const { data } = await axios.get('https://asia-northeast3-kdt-test-97b7e.cloudfunctions.net/api/todo')
        this.msgs = data.map(todo => ({ context: todo.title, name: '익명' }))
      } catch(err) {
        console.log(err)
      } finally {
        this.isLoading=false
      }
    }
  },
}
</script>

<style lang="scss" scoped>
@import url(https://fonts.googleapis.com/css?family=Open+Sans:300,400);

.container {
    width: 70vw;
    padding: 10px;
    padding-bottom: 2px;
    display: relative;
    .box {
      position: relative;
      padding: 1rem;
      width: 300px;
      min-height: 100px;
      font: 400 1.2em 'Open Sans', sans-serif;
      border-radius: 10px;
      text-align: left;
      margin-bottom: 10px;
    }
    .message-blue {
      margin-left: 20px;
      background-color: #A8DDFD;
      border: 1px solid #97C6E3;
      &::after {
        content: '';
        position: absolute;
        width: 0;
        height: 0;
        border-top: 15px solid #A8DDFD;
        border-left: 15px solid transparent;
        border-right: 15px solid transparent;
        top: 0;
        left: -15px;
      }
      &::before {
        content: '';
        position: absolute;
        width: 0;
        height: 0;
        border-top: 17px solid #97C6E3;
        border-left: 16px solid transparent;
        border-right: 16px solid transparent;
        top: -1px;
        left: -17px;
      }
    }
    .message-orange {
      margin-left: calc(100% - 240px);
      background-color: #f8e896;
      border: 1px solid #dfd087;
      &::after {
        border-bottom: 15px solid #f8e896;
        border-left: 15px solid transparent;
        border-right: 15px solid transparent;
        bottom: 0;
        right: -15px;
      }
      &::before {
        border-bottom: 17px solid #dfd087;
        border-left: 16px solid transparent;
        border-right: 16px solid transparent;
        bottom: -1px;
        right: -17px;
     }
     &::after, ::before {
        content: '';
        position: absolute;
        width: 0;
        height: 0;
     }
    }
  .message-content {
      padding: 0;
      margin: 0;
  }
  .message-timestamp {
      position: absolute;
      font-size: 1rem;
      font-weight: 300;
      bottom: 1rem;
      right: 1rem;
  }
}

.spinner-border {
  position: absolute;
  top: 1%;
  left: 50%;
  z-index: 11;
}



</style>
