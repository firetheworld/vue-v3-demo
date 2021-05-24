<template>
  <div class="about">
    <h1>This is an about page</h1>
    <HelloI18n />
    <h1>当前语言是{{locale}}</h1>
    <button @click="changeLang('en')">英文</button>
    <button @click="changeLang('cn')">简体中文</button>
    <button @click="changeLang('zh')">繁體中文</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloI18n from '@/components/HelloI18n.vue'
import { useI18n } from 'vue-i18n';

export default {
  name: 'Home',
  setup() {
    const {locale} = useI18n();
    return {locale};
  },
  components: {
    HelloI18n
  },
  data: function () {
    return {
      test: 'test'
    }
  },
  methods: {
    changeLang: function(lang) {
      this.locale = lang;
    }
  }
}
</script>