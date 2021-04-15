/* eslint-disable vue/no-mutating-props */
<template>
<div>
  <q-item
    clickable
    v-bind="itemProps"
    v-if="scope.children"
    @click="cascaderone(scope)"
  >
   <!-- <q-item-section><q-radio v-model="selectmodel" :val="keyvalue(scope)" :label="firstName(scope)" /></q-item-section> -->
    <q-item-section>{{ firstName(scope) }}</q-item-section>
    <q-item-section side v-if="scope.children">
      <q-icon name="keyboard_arrow_right" />
    </q-item-section>

    <q-menu anchor="top end" self="top start">
      <q-list v-if="scope.children">
        <CascaderItem
          v-for="n in scope.children"
          :key="keyvalue(n)"
          :scope="n" :optlabel="optlabel" :optvalue="optvalue"
        >
        </CascaderItem>
      </q-list>
    </q-menu>
  </q-item>
  <q-item
    clickable
    v-bind="itemProps"
    v-else
    @click="cascaderone(scope)"
  >
   <!-- <q-item-section><q-radio v-model="selectmodel" :val="keyvalue(scope)" :label="firstName(scope)" /></q-item-section> -->
    <q-item-section>{{ firstName(scope) }}</q-item-section>
  </q-item>
  <q-separator></q-separator>
</div>
</template>

<script>
import { EventBus } from './eventbus'
export default {
  name: 'CascaderItem',
  components: {},
  data () {
    return {
      displayvalue: null,
      selectmodel: null
    }
  },
  computed: {},
  props: {
    scope: {
      type: Object,
      default: () => null
    },
    itemEvents: {
      type: Object,
      default: () => null
    },
    itemProps: {
      type: Object,
      default: () => null
    },
    optvalue: {
      type: String,
      default: () => ''
    },
    optlabel: {
      type: String,
      default: () => ''
    }
  },
  watch: {
  },
  mounted () {
  },
  beforeDestroy () {},
  methods: {
    firstName (v) {
      return v[this.optlabel]
    },
    keyvalue (k) {
      return k[this.optvalue]
    },
    cascaderone (f) {
      this.displayvalue = f[this.optlabel]
      this.selectmodel = f[this.optvalue]
      EventBus.$emit('change', [this.displayvalue, this.selectmodel])
    //   console.log('CascaderPanel click', f)
    }
  }
}
</script>
<style lang="scss" scoped></style>
