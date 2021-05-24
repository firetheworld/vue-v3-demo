<template>
  <p>{{ t(msg) }}</p>
</template>

<script>
import { defineComponent } from 'vue'
import { useI18n } from 'vue-i18n'

export default defineComponent({
  name: 'HelloI18n',
  props: ['msg'],
  setup() {
    const { t } = useI18n({
      inheritLocale: false,
      useScope: 'global',
    })
    return { t }
  }
})
</script>
