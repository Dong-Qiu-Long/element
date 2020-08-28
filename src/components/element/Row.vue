<template>
	<div
		:class="[
			'el-row',
			{'el-row-flex' : this.type === 'flex'},
			this.justify !== 'start' && `is-justify-${justify}`,
			this.align !== 'top' && `is-align-${align}`
			]" :style="style">
		<slot></slot>
	</div>
</template>
<script>
export default {
  name: 'ElRow',
  props: {
    gutter: {
      type: Number,
      default: 0,
    },
    type: String,
    justify: {
      type: String,
      default: 'start',
      validator: (val) => ['start', 'end', 'center', 'space-between', 'space-around'].includes(val),
    },
    align: {
      type: String,
      default: 'top',
      validator: (val) => ['top', 'middle', 'bottom'].includes(val),

    },
  },
  computed: {
    style() {
      const style = {};
      style.marginLeft = `${-this.gutter}px`;
      style.marginRight = style.marginLeft;
      return style;
    },
  },
};
</script>
<style lang="scss" scoped>
	.el-row{
		&::after{
			display: block;
			content: '';
			visibility: hidden;
			clear: both;
			height: 0;
		}
		&-flex{
			display: flex;
			&::after,
			&::before{
				display: none;
			}
			&.is-justify-end{
				justify-content: flex-end;
			}
			&.is-justify-ecenter{
				justify-content: center;
			}
			&.is-justify-space-between{
				justify-content: space-between;
			}
			&.is-justify-space-around{
				justify-content: space-around;
			}
			&.is-align-middle{
				align-items: center;
			}
			&.is-align-bottom{
				align-items: flex-end;
			}
		}
		box-sizing: border-box;
	}
</style>
