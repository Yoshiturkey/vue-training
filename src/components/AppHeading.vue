<template>
  <component :is="HeadComponent">
    <slot></slot>
  </component>
</template>
<script>
/**
 * 着替えるコンポーネントを読み込んでおく
 * componentsのところで requireしてもいいお！
 */
import Heading1 from "./Heading1";
import Heading2 from "./Heading2";
import Heading3 from "./Heading3";
export default {
  props: {
    /**
     * 名前は連想しやすくしたらいいよ！
     * sizeとかでもいいけど、エセ外国かぶれのYoshitakaさんはscaleかなって思いました。:smile:
     */
    scale: {
      type: Number, //今回はh1~h3だけどh1~h6まででも対応できるように数値にした文字列として受け取ってもいいけど computedで加工するのは無駄な工数なので
      default: 1,
      validator(value) {
        return value !== 0 && value < 6; // h1~6 の場合1−6でいいので typeでチェックしてるから今更数値かどうか見る必要はない。
      },
    },
  },
  components: {
    /**
     * 使うコンポーネントを呼び込んでおく！
     */
    head1: Heading1,
    head2: Heading2,
    head3: Heading3,
  },
  computed: {
    HeadComponent() {
      /**
       * propsから渡された値でコンポーネントを選択する
       * validatorで既に1-6のいずれかしか受け付けない事が決まっているのでpropsの値で加工すればよい
       */
      return `head${this.scale}`;
    },
  },
};
</script>
