<template>
  <div class="home">
    <h1>包裹入库</h1>
    <div>
      <span>运单号：</span>
      <input v-model="orderNumber" type="text" />
    </div>
    <h1></h1>
    <div>
      <span>收件人：</span>
      <input v-model="reciverName" type="text" />
    </div>
    <h1></h1>
    <div>
      <span>电话：</span>
      <input v-model="reciverTel" type="text" />
    </div>
    <h1></h1>
    <div>
      <span>重量：</span>
      <input v-model="weight" type="text" />
    </div>
    <h1></h1>
    <div>
      <button @click="msg1Call">提交</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
export default {
  name: 'home',
  components: {},
  data: function () {
    return {
      orderNumber: '',
      reciverName: '',
      reciverTel: '',
      weight: ''
    }
  },
  // data: {
  //   orderNumber: '',
  //   reciverName: '',
  //   reciverTel: '',
  //   weight: ''
  // },
  methods: {
    msg1Call: function() {
      let self = this;
      axios
        .post("http://localhost:8080/", {
          orderNumber: this.orderNumber,
          reciverName: this.reciverName,
          reciverTel: this.reciverTel,
          weight: this.weight
        })
        .then(function(e) {});
    }
  }
};
</script>
