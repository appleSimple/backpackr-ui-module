<template>
  <div class="textarea-wrapper">
    <textarea
      :value="value"
      @input="controlInputEvent($event)"
      :name="id"
      :id="id"
      :placeholder="placeholder"
      :readonly="readonly"
      :disabled="disabled"
    ></textarea>
    <span class="text-conter">{{ textCounter }}</span>
  </div>
</template>

<script>
export default {
  name: 'DefaultTextArea',
  model: {
    prop: 'value',
    event: 'changeValue',
  },
  props: {
    value: {
      type: String,
      default: '',
    },
    id: {
      type: String,
      default: '',
      required: true,
    },
    placeholder: {
      type: String,
      default: '',
      required: false,
    },
    readonly: {
      type: Boolean,
      default: false,
    },
    disabled: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      defaultLength: 500,
    };
  },
  computed: {
    textCounter: function () {
      return this.defaultLength - this.value.length;
    },
  },
  methods: {
    controlInputEvent(event) {
      this.$emit('controlInputEvent', event);
    },
  },
};
</script>

<style scoped lang="scss">
.textarea-wrapper {
  width: 100%;
  height: 100%;
  position: relative;

  textarea {
    width: 100%;
    height: 100%;
    padding: 0;
    box-sizing: border-box;
    resize: none;

    // 아래 순서 변경 금지 (style 오버라이드)
    &:read-only {
      color: grey;
    }
    &:disabled {
      color: red;
    }
  }
  .text-conter {
    position: absolute;
    right: 22px;
    bottom: 4px;

    font-size: 10px;
    color: grey;
  }
}
</style>
