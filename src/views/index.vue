<template>
  <div class="container">
		<el-container>
			<el-header>
				<h1 class="title">小说世界生成器</h1>
			</el-header>
			<el-container>
				<el-aside width="201px">
					<el-col :span="12">
						<el-menu
							default-active="1"
							class="el-menu-vertical-demo"
							@select='select'
							background-color="#545c64"
							text-color="#fff"
							active-text-color="#ffd04b" style="width:200px;">
							<el-menu-item index="1">
								<span slot="title">卡池</span>
							</el-menu-item>
							<el-menu-item index="2">
								<span slot="title">导航二</span>
							</el-menu-item>
							<el-menu-item index="3">
								<span slot="title">导航三</span>
							</el-menu-item>
							<el-menu-item index="4">
								<span slot="title">导航四</span>
							</el-menu-item>
						</el-menu>
					</el-col>
				</el-aside>
				<el-main>
					<card-pool v-if="currentMainPage==1"></card-pool>
				</el-main>
			</el-container>
	</el-container>
	</div>
</template>

<script>
import cardPool from '@/components/mainBox/cardPool.vue'
export default {
	name: 'index',
  data() {
		return {
			currentMainPage: 1,
		}
	},
	components: {
		cardPool
	},
	beforeCreate() {
	},
	methods: {
		select(index) {
			this.currentMainPage = index
		},
	},
}
</script>

<style lang='scss'>
	.container {
		height: 100%;
		.el-container {
			height: 100%;
		}
		.el-header {
			background-color: #B3C0D1;
			color: #333;
			text-align: center;
			height: 90px !important;
			text-align: center;
			line-height: 90px;
			.title {
				font-size: 40px;
				font-family: hanzi01;
				letter-spacing: 2px;
				text-shadow: 0px 0px 1px rgba(51,51,51,0.3);
			}
		}
		
		.el-aside {
			background-color: #545c64;
			color: #333;
			text-align: center;
			border-right: 1px solid #3f4246;
			overflow-x:hidden;
		}
		
		.el-main {
			background-color: #E9EEF3;
			color: #333;
			text-align: center;
			padding: 0;
		}
	}
</style>
