<template>
  <div class="hello">
      <div class="reply">
       选出其中一项：
        <div class="radio-box" v-for="(item, index) in radios" :key="index">
          <span class="radio" :class="{'on': item.isChecked}"></span>
          <input type="checkbox" :value="item.value" class="input-radio" :checked="item.isChecked" @click="check(index)">{{item.label}}
        </div>
      </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      radios: [
        {
          label: 'a',
          value:'1',
          isChecked: true,
        },
        {
          label: 'b',
          value:'2',
          isChecked: false,
        },
        {
          label: 'c',
          value:'3',
          isChecked: false,
        }
      ]
    }
  },
  methods: {
    check(index){
      this.radios.forEach((item) => {
        item.isChecked = false;
      })
      // this.radio = this.radios[index].value
      this.radios[index].isChecked = true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
