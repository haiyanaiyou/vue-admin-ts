<template>
 <div class="header-search">
   <svg-icon class="search-icon" name="search"/>
   <el-select v-model="search">
     <el-option
      v-for="option in options"
      :key="option.path"
      :label="option.meta.title.join('>')"></el-option>
   </el-select>
 </div>
</template>

<script lang="ts">
import { Component, Vue, Watch } from 'vue-property-decorator'
import { RouteConfig } from 'vue-router'

@Component({
  name: 'HeaderSearch'
})
export default class extends Vue {
  private search = ''
  private options: RouteConfig[] = []
}
</script>

<style lang="scss" scoped>

</style>
