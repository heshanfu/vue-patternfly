<template functional>
  <div
    v-bind="data.attrs"
    v-on="listeners"
    :class="[data.class, data.staticClass]"
    class="empty-chart-content"
    :style="[data.style, data.staticStyle, {
      'height': `${props.height}px`,
      'padding-top': `${Math.min(Math.round((props.height - 40) / 2), 20)}px`,
    }]"
  >
    <pf-icon name="pficon-info"/>
    <slot>
      <span>No data available</span>
    </slot>
  </div>
</template>

<script>
export default {
  name: 'pf-empty-chart',

  props: {
    height: {
      type: Number,
      default: 40,
    },
  },
};
</script>

<style>
.empty-chart-content {
  text-align: center;
}
.empty-chart-content .pficon {
  font-size: 24px;
}
.empty-chart-content span {
  vertical-align: middle;
  width: 100%;
}
</style>
