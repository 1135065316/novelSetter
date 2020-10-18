<template>
	<div>
		<el-menu
			default-active="1"
			class="el-menu-demo"
			mode="horizontal"
			@select="handleSelect"
			background-color="#545c64"
			text-color="#fff"
			active-text-color="#ffd04b"
			style="height:56px;">
			<el-menu-item index="1" class="topTab">生成卡片</el-menu-item>
			<el-menu-item index="2" class="topTab">2</el-menu-item>
			<el-menu-item index="3" class="topTab">3</el-menu-item>
			<el-menu-item index="4" class="topTab">4</el-menu-item>
			
		</el-menu>
		
		<div class="cardBox" v-if="activeTab == 1">
			<el-form ref="form" :model="form" label-width="80px">
				<el-form-item label="卡片名称">
					<el-input v-model="form.name"></el-input>
				</el-form-item>
				<el-form-item label="卡片类型">
					<el-input v-model="form.type"></el-input>
					<el-radio-group v-model="form.type">
						<el-radio :label="item" v-for="(item,index) in cardType" :key='index'></el-radio>
					</el-radio-group>
				</el-form-item>
				<el-form-item label="卡片描述">
					<el-input type="textarea" v-model="form.desc"></el-input>
				</el-form-item>
				<el-form-item>
					<el-button type="primary" @click="onSubmit">立即生成</el-button>
					<el-button>取消</el-button>
				</el-form-item>
			</el-form>
		</div>

	</div>
</template>

<script>
	export default {
		data() {
			return {
				form: {
          name: '',
          type: '',
          desc: ''
				},
				cardType: ['人物','物品','场景'],
				activeTab: 1,
			}
		},
		methods: {
			handleSelect(index) {
				this.activeTab = index
			},
			// 提交卡片
			onSubmit(data) {
				// 输入校验
				if(!this.inputCheck()) {
					return
				}
				console.log(this.form)
			},
			// 输入校验
			inputCheck() {
				// 名称不能为空
				if(this.form.name == '') {
					this.$message({
						message: '名称不能为空',
						type: 'warning'
					});
					return false
				}
				// 类型不能为空
				if(this.form.type == '') {
					this.$message({
						message: '类型不能为空',
						type: 'warning'
					});
					return false
				}

				return true
			}
		},
	}
</script>

<style lang="scss">
	.topTab {
		height: 56px !important;
	}
	.cardBox {
		border: 1px solid #c0bebe;
		border-radius: 3px;
		padding: 24px;
		width: 460px;
		margin: 50px;
		box-shadow: 2px 2px 5px #c0bebe;
	}
</style>