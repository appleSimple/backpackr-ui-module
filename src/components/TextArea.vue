<template>
  <div class="text-area-wrapper">
    <div class="field-wrapper">
      <legend>default,<br />입력중</legend>
      <DefaultTextArea
        id="defaultTextArea"
        placeholder="내용이 있을수도 있습니다"
        v-model="defaultTextArea"
        @controlInputEvent="
          [(defaultTextArea = $event.target.value), controlButton($event)]
        "
      />
      <button v-if="isButton" type="button">Save</button>
    </div>
    <div class="field-wrapper">
      <legend>disabled</legend>
      <DefaultTextArea
        id="disabledTextArea"
        v-model="disabledTextArea"
        @controlInputEvent="disabledTextArea = $event.target.value"
        disabled
      />
    </div>
    <div class="field-wrapper">
      <legend>readonly</legend>
      <DefaultTextArea
        id="readonlyTextArea"
        v-model="readonlyTextArea"
        @controlInputEvent="readonlyTextArea = $event.target.value"
        readonly
      />
    </div>
  </div>
</template>

<script>
import DefaultTextArea from './DefaultTextArea.vue';

const DEFAULT_CONTENTS = '초기값이 있을수 있습니다';
const DISABLED_CONTENTS = '주문 요청사항을 입력해주세요';
const READONLY_CONTENTS = '읽기 전용 상태입니다';

export default {
  name: 'TextArea',
  components: { DefaultTextArea },
  data() {
    return {
      defaultTextArea: DEFAULT_CONTENTS,
      disabledTextArea: DISABLED_CONTENTS,
      readonlyTextArea: READONLY_CONTENTS,
      isButton: false,
    };
  },
  methods: {
    controlButton(event) {
      const value = event.target.value;

      if (value === DEFAULT_CONTENTS || value === '') {
        this.isButton = false;
        return;
      }
      this.isButton = true;
    },
  },
};
</script>

<style scoped lang="scss">
.text-area-wrapper {
  .field-wrapper {
    width: 600px;
    height: 100px;
    display: flex;
    
    legend {
      font-weight: 600;
      margin-right: 10px;
    }

    button {
      width: 90px;
      height: 100%;
      margin-left: 4px;
    }
  }
}
</style>
