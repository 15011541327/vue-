<template>
  <div>
    <p>click{{$store.state.count}}times,count is {{evenOrOdd}}</p>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="incrementIfOdd">increment if odd</button>
    <button @click="incrementAsync">increment async</button>
  </div>
</template>

<script>
  import {mapState,mapGetters,mapActions} from 'vuex'
  export default {
    computed : {
      /*evenOrOdd(){
       return this.$store.getters.evenOrOdd;
       }*/
      ...mapState(['count']),//mpaState()返回值：{count(){return this.$store.state.['count']} }
      ...mapGetters(['evenOrOdd'])
    },
    methods : {
      ...mapActions(['increment','decrement','incrementIfOdd','incrementAsync'])
    }
    /*
    *  methods : {
     increment(){
     //通知vuex去增加
     this.$store.dispatch('increment');//触发store中对应的action调用
     },
     decrement(){
     this.$store.dispatch('decrement');
     },
     incrementIfOdd(){
     this.$store.dispatch('incrementIfOdd');
     },
     incrementAsync(){
     this.$store.dispatch('incrementAsync');
     }
     }*/

  }
</script>

<style>

</style>
