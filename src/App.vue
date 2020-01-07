<template>
  <div id="app">
    <div>333</div>
    <HelloWorld msg="ljy"/>
    {{a}}
    //<div v-bind:class="color">gege</div>
    <p>{{1==2 ? 'yes' : 'no'}}</p>
    <p>{{message.split('').reverse().join('')}}</p>
    <div
        v-bind:class= "[isActive ? 'active' : '', isGreen ? 'green' : '']"
        style="width:200px; height:200px; text-align:center; line-height:200px;">
        wi
    </div>
    <ul>
      <li v-for="(item,index) in items" :key="index">
        {{index}}{{item.message}}
      </li>
      <li v-for="(value, key) in object" :key="key">
        {{key}}:{{value}}
      </li>
    </ul>
     <div>
     <button v-on:click="counter += 1">数值 : {{counter}} </button><br/>

     
     </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.demo.vue'

const vm =  {
  name: 'app',
  // data: {
  //  a: 1
  // },
  data: function () {
    return {
      counter: 0 ,
      a: 123,
      color:'red',
      ok:1,
      message:"vue",
      isActive:true,
      isGreen:true,
      items:[
        { message: 'foo', index: 1 },
        { message: 'Bar', index: 2}
      ],
      object: {
        title: '1245',
        author: '634',
        publishedAt: '2020-11-02'
      }
    }
  },

  // created :function(){
  // this.$data.a = 'wrgw';
  // },
  //mounted: function(){
  //  this.$data.a = 'xxx';
  //},
  //watch: {
  //  a: function(newVal, oldVal) {
  //    console.log(newVal, oldVal);
  //  }
  //},
  components: {
    HelloWorld
  }
}

export default vm;
</script>

<style>
.red {
  color:red;
}
.blue {
  color:red;
}
.active{
  background:#FF0000;
  }
.green{
  color:#00FF00;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
