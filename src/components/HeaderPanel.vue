<template>
  <div class="content">
    <button class="button" @click="$emit('show')" title="Upload your image!">
      <img class="button__img" src="@/assets/download-photo-svgrepo-com.svg" alt="">
    </button>
    <button class="button" :disabled="!startImage" :class="{ active: isPippet}" @click="$emit('pippet')" title="Color picker. To select the second color, click with Alt pressed.">
      <img class="button__img" src="@/assets/pipette.svg" alt="">
    </button>
    <button class="button" :disabled="!startImage" :class="{ active: isGrab}" @click="$emit('grab')" title="Grab your image">
      <img class="button__img" src="@/assets/hand-grab.svg" alt="">
    </button>
    <button class="button" :disabled="!startImage" @click="$emit('scale')" title="Resize your image">
      <img class="button__img" src="@/assets/scale-up.svg" alt="">
    </button>
    <button class="button" :disabled="!startImage" :class="{ active: isCurves}" @click="$emit('curve')" title="Curves">
      <img class="button__img" src="@/assets/curve.svg" alt="">
    </button>
    <button class="button" :disabled="!startImage" :class="{ active: isFiltering}" @click="$emit('filtering')" title="Filtering">
      <img class="button__img" src="@/assets/filtering.svg" alt="">
    </button>
    <button class="button" :disabled="!startImage" @click="$emit('save')" title="Save your image">
      <img class="button__img" src="@/assets/save.svg" alt="">
    </button>
    <button class="button" :disabled="!startImage" @click="$emit('clear')" title="Clear">
      <img class="button__img" src="@/assets/delete-2-svgrepo-com.svg" alt="">
    </button>
  </div>
</template>
  
  <script>
export default {
  name: "HeaderPanel",
  props: {
    state: String,
    startImage: Object,
  },
  data() {
    return {
      new: null,
    };
  },

  methods: {
  },
  computed:{
    isPippet(){
      if (this.state == 'pippet'){
        return true
      } else {
        return false
      }
    },
    isGrab(){
      if (this.state == 'grab'){
        return true
      } else {
        return false
      }
    },
    isCurves(){
      if (this.state == 'curves'){
        return true
      } else {
        return false
      }
    },
    isFiltering(){
      if (this.state == 'filter'){
        return true
      } else {
        return false
      }
    }
  }
};
</script>
  
  <style lang="scss" scoped>
.content {
  height: 80px;
  background-color: #1b263b;
  display: flex;
  flex-direction: row;
  align-items: center;
  column-gap: 50px;
  padding: 10px;
}
.button{
  background-color: #778da9;
  border: 1px solid #0d1b2a;
  border-radius: 10px;
  padding: 7px;
  height: fit-content;
  margin-left: 20px;

  &__img{
    height: 35px;
  }

  &:last-child{
    margin-left: auto;
    margin-right: 20px;
  }

  &:disabled{
    background-color: #212a39;
  }

  &.active{
    background-color: #1b263b;
  }
}
</style>
  