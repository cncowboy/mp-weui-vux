<template>
  <a
    :class="['weui-cell', {'weui-cell_access': !!link}]"
    :hover-class="!!link ? 'weui-cell_active' : 'none'"
    @click="$emit('click', $event)"
    :href="link"
  >
    <div class="weui-cell_hd">
      <!-- <slot name="icon"> -->
        <img
          class="weui-cell__icon"
          :src="icon"
          v-if="icon"
        />
      <!-- </slot> -->
    </div>
    <div class="weui-cell__bd">
      <!-- <slot> -->
        <span v-text="title" />
      <!-- </slot> -->
    </div>
    <div :class="['weui-cell__ft', {'weui-cell__ft_in-access': !!link}]">
      <!-- <slot name="label"> -->
        <span v-text="value"/>
      <!-- </slot> -->
    </div>
  </a>
</template>

<script>
export default {
  name: 'MpCell',
  props: {
    title: String,
    icon: String,
    value: String,
    link: String,
    'is-link': Boolean,
  },
};
</script>

<style lang="less">
.weui-cell__icon {
  width: 20px;
  height: 20px;
  margin-right: 5px;
  vertical-align: middle;
}
</style>

