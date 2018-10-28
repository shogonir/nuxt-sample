<template>
  <section>
    <h1 class="header">Nuxt TypeScript Starter</h1>
    <SnTab
      commonClass="common-class"
      activeClass="active-class"
      inactiveClass="inactive-class"
      :labels="['members', 'teams', 'categories']"
    />
  </section>
</template>



<script lang="ts">

import { Component, Vue } from 'nuxt-property-decorator'
import { State } from 'vuex-class'

import SnTab from '~/components/SnTab.vue'

@Component({
  components: {
    SnTab,
  }
})
export default class extends Vue {
}

</script>



<style scoped>
.header {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana,
    sans-serif;
}

.cards {
  display: flex;
  flex-wrap: wrap;
}
</style>