<script setup>
import WelcomeItem from './WelcomeItem.vue'
import CompositionBasic from './composition_api/CompositionBasic.vue'
import ComputedDemo from './composition_api/ComputedDemo.vue'
import WatchDemo from './composition_api/WatchDemo.vue'
import CaseTemplate from './CaseTemplate.vue'
</script>

<template>

  <WelcomeItem>
    <template #heading>组合式 API （Composition API）</template>
    
    <CaseTemplate>
      <template #caseName>CompositionBasic.vue</template>
      <template #caseInfo>
        <a href="https://cn.vuejs.org/guide/essentials/reactivity-fundamentals.html" target="_blank" rel="noopener noreferrer">响应式基础</a>
      </template>
      <template #apiInfo>
          <a href="https://cn.vuejs.org/api/sfc-script-setup.html" target="_blank" rel="noopener noreferrer">script-setup</a>、
          <a href="https://cn.vuejs.org/api/reactivity-core.html#ref" target="_blank" rel="noopener noreferrer">ref()</a>、
          <a href="https://cn.vuejs.org/api/reactivity-core.html#reactive" target="_blank" rel="noopener noreferrer">reactive()</a>、
          <a href="https://cn.vuejs.org/api/general.html#nexttick" target="_blank" rel="noopener noreferrer">nextTick()</a>
      </template>
      <CompositionBasic></CompositionBasic>
    </CaseTemplate>
    
    <CaseTemplate>
      <template #caseName>ComputedDemo.vue</template>
      <template #caseInfo>
        <a href="https://cn.vuejs.org/guide/essentials/computed.html" target="_blank" rel="noopener noreferrer">计算属性</a>
      </template>
      <template #apiInfo>
          <a href="https://cn.vuejs.org/api/sfc-script-setup.html" target="_blank" rel="noopener noreferrer">script-setup</a>、
          <a href="https://cn.vuejs.org/api/reactivity-core.html#ref" target="_blank" rel="noopener noreferrer">ref()</a>、
          <a href="https://cn.vuejs.org/api/reactivity-core.html#reactive" target="_blank" rel="noopener noreferrer">reactive()</a>、
          <a href="https://cn.vuejs.org/api/general.html#nexttick" target="_blank" rel="noopener noreferrer">nextTick()</a>
      </template>
      <ComputedDemo></ComputedDemo>
    </CaseTemplate>

    <CaseTemplate>
      <template #caseName>WatchDemo.vue</template>
      <template #caseInfo>
        <a href="https://cn.vuejs.org/guide/essentials/watchers.html" target="_blank" rel="noopener noreferrer">侦听器</a>
      </template>
      <template #apiInfo>
        <a href="https://cn.vuejs.org/api/reactivity-core.html#watch" target="_blank" rel="noopener noreferrer">watch</a>
      </template>
      <WatchDemo></WatchDemo>
    </CaseTemplate>
    

  </WelcomeItem>

  <WelcomeItem>
    <template #heading>Tooling</template>

    This project is served and bundled with
    <a href="https://vitejs.dev/guide/features.html" target="_blank" rel="noopener">Vite</a>. The
    recommended IDE setup is
    <a href="https://code.visualstudio.com/" target="_blank" rel="noopener">VSCode</a> +
    <a href="https://github.com/johnsoncodehk/volar" target="_blank" rel="noopener">Volar</a>. If
    you need to test your components and web pages, check out
    <a href="https://www.cypress.io/" target="_blank" rel="noopener">Cypress</a> and
    <a href="https://on.cypress.io/component" target="_blank" rel="noopener"
      >Cypress Component Testing</a
    >.

    <br />

    More instructions are available in <code>README.md</code>.
  </WelcomeItem>

  <WelcomeItem>
    <template #heading>Ecosystem</template>

    Get official tools and libraries for your project:
    <a href="https://pinia.vuejs.org/" target="_blank" rel="noopener">Pinia</a>,
    <a href="https://router.vuejs.org/" target="_blank" rel="noopener">Vue Router</a>,
    <a href="https://test-utils.vuejs.org/" target="_blank" rel="noopener">Vue Test Utils</a>, and
    <a href="https://github.com/vuejs/devtools" target="_blank" rel="noopener">Vue Dev Tools</a>. If
    you need more resources, we suggest paying
    <a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">Awesome Vue</a>
    a visit.
  </WelcomeItem>

  <WelcomeItem>
    <template #heading>Community</template>

    Got stuck? Ask your question on
    <a href="https://chat.vuejs.org" target="_blank" rel="noopener">Vue Land</a>, our official
    Discord server, or
    <a href="https://stackoverflow.com/questions/tagged/vue.js" target="_blank" rel="noopener"
      >StackOverflow</a
    >. You should also subscribe to
    <a href="https://news.vuejs.org" target="_blank" rel="noopener">our mailing list</a> and follow
    the official
    <a href="https://twitter.com/vuejs" target="_blank" rel="noopener">@vuejs</a>
    twitter account for latest news in the Vue world.
  </WelcomeItem>

  <WelcomeItem>
    <template #heading>Support Vue</template>

    As an independent project, Vue relies on community backing for its sustainability. You can help
    us by
    <a href="https://vuejs.org/sponsor/" target="_blank" rel="noopener">becoming a sponsor</a>.
  </WelcomeItem>
</template>
