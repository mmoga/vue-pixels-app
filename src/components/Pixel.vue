<template>
  <div @click="handleClick" :class="['pixel', color, current ? 'current' : '']"></div>
</template>

<script>
export default {
  name: "Pixel",
  props: {
    color: String,
    current: Boolean,
    isInColorPicker: Boolean,
    isInCanvas: Boolean,
    index: Number
  },
  methods: {
    handleClick: function() {
      if (this.isInColorPicker) {
        this.$root.$emit("updatecolor", this.color);
      }
      if (this.isInCanvas) {
        this.$root.$emit("clickedpixel", this.index);
      }
    }
  }
};
</script>


<style lang="stylus" scoped>
.pixel {
  border: 1px solid lightgrey;
  width: 30px;
  height: 30px;
  box-sizing: border-box;

  &.current {
    border: 4px solid yellow;
  }
}

.white {
  background-color: white;
}

.lightblue {
  background-color: rgb(0, 188, 212);
}

.blue {
  background-color: rgb(3, 169, 244);
}

.darkblue {
  background-color: rgb(33, 150, 243);
}
</style>
