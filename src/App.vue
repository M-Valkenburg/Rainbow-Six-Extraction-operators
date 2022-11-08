<script lang="js">
import operators from './data/operators.js';
import HeaderBanner from './components/Header.vue';
import OpSelect from './components/OpSelect.vue';
import OpDisplay from './components/OpDisplay.vue';

export default {
  name: 'App',
  components: {
    HeaderBanner,
    OpSelect,
    OpDisplay
  },
  data() {
    return {
      opInfo: operators,
      displayedOp: 0
    }
  },
  methods: {
    setDisplayedOp(index) {
      return this.displayedOp = index
    }
  }
}
</script>

<style lang="scss">
@import './app.scss';
</style>

<template>
  <HeaderBanner/>
  <section>
    <OpSelect :ops="opInfo" @update-op="setDisplayedOp" />
    <OpDisplay :op="opInfo[displayedOp]" />
  </section>
</template>
