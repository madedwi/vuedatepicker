<style>
.demo > * {
  margin-right: 10px;
}
</style>

<template>
  <div class="demo">
    <datepicker :readonly="true" format="YYYY-MM-DD" name="date1"></datepicker>
    <datepicker value="2018-9-5" format="YYYY-M-D" name="date2" :input-attr="{ 'data-test': 'value' }"></datepicker>
    <datepicker :readonly="true" format="MMM/D/YYYY" name="date3" :disabled-date="disabledDate"></datepicker>
    <datepicker :readonly="true" format="YYYY-MM-DD" name="date1" v-model="date1"></datepicker>
    <br>
    Model Value : {{date1}}
  </div>
</template>

<script>
import datepicker from '../src/vue-date-picker.vue'

export default {
  components: {
    datepicker
  },
  data(){
    return {
      date1 : '2019-11-18'
    }
  },
  methods: {
    disabledDate (date) {
      return date.getTime() < Date.now()
    }
  },
  watch : {
    date1(n, o){
      console.log(n);
      
    }
  }
}
</script>
