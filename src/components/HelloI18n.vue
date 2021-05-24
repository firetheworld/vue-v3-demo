<template>
  <p>{{ t('message') }}</p>
</template>

<script>
import { defineComponent } from 'vue'
import { useI18n } from 'vue-i18n'

export default defineComponent({
  name: 'HelloI18n',
  setup() {
    const { t } = useI18n({
      inheritLocale: false,
      useScope: 'global',
    })
    return { t }
  }
})
</script>
