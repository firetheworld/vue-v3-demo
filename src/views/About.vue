<template>
  <div class="about">
    <h1>This is an about page</h1>
    <HelloI18n msg='message'/>
    <h1>当前语言是{{locale}}</h1>
    <button @click="changeLang('en')">英文</button>
    <button @click="changeLang('cn')">简体中文</button>
    <button @click="changeLang('zh')">繁體中文</button>
    <button @click="asynLoadingRes()">异步加载资源</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloI18n from '@/components/HelloI18n.vue'
import { useI18n } from 'vue-i18n';

export default {
  name: 'Home',
  setup() {
    const {locale, setLocaleMessage} = useI18n({
      inheritLocale: false,
      useScope: 'global',
    });
    return {locale, setLocaleMessage};
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
    },
    asynLoadingRes() {
      const that = this;
      setTimeout(() => {
        that.setLocaleMessage('zh', {message: '你好啊，繁體字异步'});
      }, 2000)
    }
  }
}
</script>