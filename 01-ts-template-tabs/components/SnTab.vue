<template>
  <div>
    <div class="tab-headers-area">
      <div
        v-for="(label, index) in labels"
        :key="label"
        :class="tabHeaderClass(index)"
        @click="onClickTabHeader(index)"
      >
        {{ label }}
      </div>
    </div>
    <div class="tab-contents-area">
    </div>
  </div>
</template>



<script lang="ts">

import { Component, Prop, Vue } from 'nuxt-property-decorator'

@Component({})
export default class SnTab extends Vue {
  
  @Prop()
  private commonClass: string

  @Prop()
  private activeClass: string

  @Prop()
  private inactiveClass: string

  @Prop()
  private labels: string[]

  private activeTabIndex: number = 0

  mounted() {
    console.log(this.activeClass)
  }

  tabHeaderClass(index: number): string {
    return index === this.activeTabIndex
      ? `${this.commonClass} ${this.activeClass}`
      : `${this.commonClass} ${this.inactiveClass}`
  }

  onClickTabHeader(index: number) {
    this.activeTabIndex = index
  }
}

</script>



<style scoped>

.tab-headers-area {
  width: 100%;
  height: 70px;
  background-color: red;
}

.tab-contents-area {
  width: 100%;
  height: 100%;
  background-color: blue;
}

.common-class {
  width: 200px;
  float: left;
}

.active-class {
  background-color: green;
}

</style>
