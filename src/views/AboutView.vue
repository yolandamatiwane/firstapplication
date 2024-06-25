<template>
  <div>
    <h1>Counter -><span>{{counter}}</span></h1>
    <button v-on:click="increment()">Increment</button>
    <button @click="decrement()">Decrement</button>
  </div>
  <!-- Attach js value to an attribute tag ... sorthand in ' :'-->
  <img v-bind:src="imgUrl">
  <div>
    <h4 :class='{hello:check}'>Conditional Rendering</h4>
    <h1 v-if="check">The value is True</h1>
    <h1 v-else>The value is False</h1>
    <button @click="checking()">Change state</button>
    <h1 v-show="check">This contains the v-show</h1>
    <ul>
      <!-- <li v-for="sport,index in sports" :key="index">{{sport}}</li> more convinient -->
      <!-- <li v-for="sport in sports" :key="sport">{{sport}}</li> -->
      <!-- <li v-for="({message},index) in objects" :key="index">{{message}}</li> -->
      <li v-for="object in objects" :key="object.id">{{object.message}}</li>
    </ul>
    <!-- one way data binding -->
    <h3>{{oneWayText}}</h3>
    <!-- two way data binding -->
    <h3>{{twoWayText}}</h3>
    <input type="text" v-model="twoWayText">
  </div>
  <!-- <info-comp first-name="hehe" last-name="hehehehe"/>
  <info-comp first-name = "hehe1"/> -->
  <!-- used ':' because we were referring to something in our script tag BELOW -->
  <!-- <info-comp :object-data='singleObject'/> -->
   <info-comp>
    Hehe I am using slots
   </info-comp>
   <slot-comp>
    <!-- correct syntax -> v-slot=slotTitle -->
    <template #slotTitle>
      <!-- Card Slot -->
    </template>
    <template #default>
      <img :src="imgUrl">
    </template>
   </slot-comp>
</template>


<script>
// /*eslint-disable*/
import InfoComp from '../components/InfoComp.vue'
import SlotComp from '../components/SlotComp.vue'
export default {
  data(){
    return{
      counter: 0,
      imgUrl: 'https://store-images.s-microsoft.com/image/apps.44122.14393276044279732.a2dc62ed-f48c-4333-8800-5dd9645ff31a.76e34181-c386-4673-8f9b-15ee3b74f463?q=90&w=480&h=270',
      check: true,
      sports:['soccer','netball','volleyball'],
      objects:[
        {message:'Hello There 1',id:1},
        {message:'Hello There 2',id:2},
        {message:'Hello There 3',id:3}
      ],
      singleObject:{
        name:'Yolanda',
        surname:'Matiwane'
      },
      oneWayText:'hehehehe',
      twoWayText:'hehe2.0'
    }
  },
  components:{
    InfoComp,
    SlotComp
  }
  ,
  methods:{
    increment(){
      this.counter++
    },
    decrement(){
      this.counter--
    },
    checking(){
      this.check = !this.check
    }
  }
}
</script>
<style scoped>
  h1{
    color: blue;
  }
  .hello{
    color: orangered;
  }
  img{
    width: 10rem;
  }
</style>