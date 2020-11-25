<template>
  <div>
    <h3>
      Identicon Creator
    </h3>

    <div>
      Input: 
      <input class="border"
        v-on:input="onInput"  
      />
    </div>

    <div>
      Output:
      <div v-html="identicon">

      </div>
    </div>

  </div>
</template>

<script>
import * as jdenticon from 'jdenticon';

export default {
  name: 'App',
  data: () => {
    return {
      textInput:''
      }
  },
  computed: {
    identicon: function(){
      return jdenticon.toSvg(this.textInput, 200)
    }
  },
  methods: {
    onInput: function(event) {
      this.textInput = event.target.value;
      console.log(this.textInput)
    }
  }
}
</script>

<style>
@import "css/tailwind.css";

</style>
