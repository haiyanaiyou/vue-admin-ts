<template>
  <div class="app-container">
    <el-button type="primary" @click.native.stop="handleGuide">引导</el-button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import Driver from 'driver.js'
import 'driver.js/dist/driver.min.css'
import steps from './steps'

@Component({
  name: 'Guide'
})
export default class extends Vue {
  private driver: Driver | null = null;
  mounted() {
    this.driver = new Driver({
      padding: 5
    })
  }

  private handleGuide() {
    if (this.driver) {
      this.driver.defineSteps(steps)
      this.driver.start()
    }
  }
}
</script>

<style lang="scss" scoped></style>
