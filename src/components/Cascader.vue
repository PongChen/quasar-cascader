/* eslint-disable no-void */
<template>
  <q-select
    outlined
    :dense="dense"
    :readonly="readonly"
    v-model="model"
    input-debounce="0"
    :label="label"
    clearable
    @clear="clearcascader"
    :options="options"
    :rules="important ? [val => val != null || '请输入' + label] : []"
  >
    <template v-slot:label v-if="important">
      {{ label }}
      <strong class="text-deep-orange">*</strong>
    </template>
    <template v-slot:option="scope">
      <Item
        :itemProps="scope.itemProps"
        :itemEvents="scope.itemEvents"
        :scope="scope.opt"
        :optlabel="optlabel"
        :optvalue="optvalue"
      ></Item>
    </template>
    <!-- <template v-slot:selected-item>
      {{ displayvalue }}
    </template> -->
  </q-select>
</template>

<script>
import Item from "./Item";

import { EventBus } from "./eventbus";

export default {
  name: "Cascader",
  components: {
    Item
  },
  data() {
    return {
      displayvalue: null,
      model: null,
      result: []
    };
  },
  computed: {},
  props: {
    options: {
      type: Array,
      default: () => []
    },
    selected: {
      type: Number,
      default: () => null
    },
    label: {
      type: String,
      default: () => ""
    },
    optvalue: {
      type: String,
      default: () => ""
    },
    optlabel: {
      type: String,
      default: () => ""
    },
    dense: {
      type: Boolean,
      default: false
    },
    important: {
      type: Boolean,
      default: false
    },
    readonly: {
      type: Boolean,
      default: false
    }
  },
  watch: {
    options: {
      handler: function(newVal, oldVal) {
        if (newVal.length > 0 && this.selected) {
          this.find(this.options);
          if (this.result.length > 0) {
            this.model = this.result[0][this.optlabel];
          }
        }
      }
    },
    selected: {
      handler: function(newVal, oldVal) {
        if (newVal && this.options.length > 0) {
          this.find(this.options);
          if (this.result.length > 0) {
            this.model = this.result[0][this.optlabel];
          }
        }
      }
    }
  },
  created() {
  },
  mounted() {
    EventBus.$on("change", msg => {
      this.model = msg[0];
      this.$emit("change", msg[1]);
    });
    if (this.selected && this.options.length > 0) {
      this.find(this.options);
      if (this.result.length > 0) {
        this.model = this.result[0][this.optlabel];
      }
    }
  },
  beforeDestroy() {
    // eventbus 陷阱
    // TODO 如果一个页面有多个本组件，其中一个销毁若关闭监听，会导致其他组件事件监听失效
    EventBus.$off();
    // EventBus.$off('change')
  },
  methods: {
    find(arr) {
      arr.forEach(item => {
        if (item.children) {
          this.find(item.children);
        }
        console.log(item.name);
        if (this.judge(item)) {
          this.result.push(item);
        }
      });
    },
    judge(item) {
      return item[this.optvalue] === this.selected;
    },
    setcascader(s) {
      this.model = s;
    },
    clearcascader() {
      this.model = null;
      this.$emit("change", this.model);
      //   this.dataForm.type = null
    }
  }
};
</script>
<style lang="scss" scoped></style>
