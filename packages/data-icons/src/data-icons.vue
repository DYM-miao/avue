<template>
  <div class="data-icons">
    <el-row :span="24">
      <template v-for="item in data">
        <el-col :span="span">
          <div class="item"
               :class="[{'item--easy':discount}]">
            <div class="item-icon"
                 :style="{color:color}">
              <i :class="item.icon"></i>
            </div>
            <div class="item-info">
              <span>{{item.title}}</span>
              <h3 :style="{color:color}">{{item.count}}</h3>
            </div>
          </div>
        </el-col>
      </template>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'AvueDataIcons',
  data () {
    return {

    }
  },
  computed: {
    span () { return this.option.span || 4 },
    data () { return this.option.data },
    color () { return this.option.color || 'rgb(63, 161, 255)' },
    discount () { this.option.discount || false }
  },
  props: {
    option: {
      type: Object,
      default: () => { }
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
