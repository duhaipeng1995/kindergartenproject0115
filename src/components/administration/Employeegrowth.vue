<template>
	<div class="employeegrowth">
		<div class="employeegrowthContent">
			<div class="sharingTitle">
				<h3>管理</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>员工成长率</h3>
					<div class="sharingLink">
						<a href="">导出</a>
					</div>
				</div>
				<div class="distribution">
					<ul class="park">
						<h3>所属园区:</h3>
						<li class="style">全部</li>
						<li>星光幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
					</ul>
					<ul class="park">
						<h3>所属职位:</h3>
						<li class="style">全部</li>
						<li>主班</li>
						<li>分园长</li>
						<li>见习园长</li>
						<li>园长助理</li>
						<li>厨师长</li>
					</ul>				
					<div class="sharingTime">
						<div class="sharingDate">
							<span class="demonstration">时间</span>
						    <el-date-picker
						      v-model="value6"
						      type="daterange"
						      range-separator="~"
						      start-placeholder="开始日期"
						      end-placeholder="结束日期">
						    </el-date-picker>
						</div>
						<div class="sharingInput">
							<el-row>
								<el-input
								    placeholder="请输入内容"
								    prefix-icon="el-icon-search"
								    v-model="input21">
								</el-input>
								<el-button class="departureStyle">搜索</el-button>
								<el-button>成长排名</el-button>
								<el-button>所选</el-button>
							</el-row>
						</div>
					</div>			
				</div>
				<div class="employeegrowthTable">
					<table class="sharingTable">
						<tr>
							<th for="quan"><input id="quan" type="checkbox" @click="checkAll($event)">全选</th>
							<th>编号</th>
							<th>员工姓名</th>
							<th>职务</th>
							<th>所在班级/部门</th>
							<th>所在园区</th>
							<th>状态</th>
							<th>入职时间</th>
							<th>学习提升</th>
							<th>工作亮点</th>
							<th>排名</th>
						</tr>
						<tr class="sharingTablecolor_one" v-for="item in ajaxData">
							<td><input class="checkItem" type="checkbox" :value="item.value" v-model="checkData"> {{item.name}}</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>
								<img src="../../../static/img/top.png" alt="" />
								Data
							</td>
						</tr>
						<tr class="sharingTablecolor_two" v-for="item in ajaxData">
							<td><input class="checkItem" type="checkbox" :value="item.value" v-model="checkData"> {{item.name}}</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>
								<img src="../../../static/img/bottom.png" alt="" />
								Data
							</td>
						</tr>
						<tr class="sharingTablecolor_one" v-for="item in ajaxData">
							<td><input class="checkItem" type="checkbox" :value="item.value" v-model="checkData"> {{item.name}}</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>
								<img src="../../../static/img/top.png" alt="" />
								Data
							</td>
						</tr>
						<tr class="sharingTablecolor_two" v-for="item in ajaxData">
							<td><input class="checkItem" type="checkbox" :value="item.value" v-model="checkData"> {{item.name}}</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>
								<img src="../../../static/img/bottom.png" alt="" />
								Data
							</td>
						</tr>
						<tr class="sharingTablecolor_one" v-for="item in ajaxData">
							<td><input class="checkItem" type="checkbox" :value="item.value" v-model="checkData"> {{item.name}}</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>
								<img src="../../../static/img/top.png" alt="" />
								Data
							</td>
						</tr>
						<tr class="sharingTablecolor_two" v-for="item in ajaxData">
							<td><input class="checkItem" type="checkbox" :value="item.value" v-model="checkData"> {{item.name}}</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>
								<img src="../../../static/img/bottom.png" alt="" />
								Data
							</td>
						</tr>
					</table>
				</div>
			</div>				
		</div>
	</div>	
</template>

<script>
export default {
  	name: 'employeegrowth',
  	data () {
    	return {
    		input21: '',
    		ajaxData: [{ // 后台请求过来的数据
					name: '选项1',
					value: 'apple'
				}],
			checkData: [], // 双向数据绑定的数组
    		pickerOptions2: {
	          		shortcuts: [{
	//          		text: '最近一周',
	    				onClick(picker) {
				      		const end = new Date();
				     		const start = new Date();
				     		start.setTime(start.getTime() - 3600 * 1000 * 24 * 7);
				     		picker.$emit('pick', [start, end]);
			    		}
			  		}, {
	//          		text: '最近一个月',
					    onClick(picker) {
					      	const end = new Date();
					      	const start = new Date();
					      	start.setTime(start.getTime() - 3600 * 1000 * 24 * 30);
					      	picker.$emit('pick', [start, end]);
					    }
					}, {
	//          		text: '最近三个月',
	    				onClick(picker) {
	      					const end = new Date();
	      					const start = new Date();
	     		 			start.setTime(start.getTime() - 3600 * 1000 * 24 * 90);
	      					picker.$emit('pick', [start, end]);
	    				}
	  				}]
				},
				value6: ''
    	}
  	}, 	
  	
  	
  	watch: {
			checkData: { // 监视双向绑定的数组变化
				handler() {
					if(this.checkData.length == this.ajaxData.length) {
						document.querySelector('#quan').checked = true;
					} else {
						document.querySelector('#quan').checked = false;
					}
				},
				deep: true
			}
		},
	methods: {
		checkAll(e) { // 点击全选事件
				if(e.target.checked) {
					this.ajaxData.forEach((el, i) => {
						// 数组里没有这一个value才push，防止重复push
						if(this.checkData.indexOf(el.value) == '-1') {
							this.checkData.push(el.value);
						}
					});
				} else { // 全不选选则清空绑定的数组
					this.checkData = [];
				}
			}
  	
  	
	}
}
</script>

<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.employeegrowth{
  		width: 1200px;
		margin: 0 auto;
		position: relative;
		.employeegrowthContent{
			width: 912px;
			position: absolute;
			top: 0;
			left: 285px;
			.employeegrowthTable{
				width: 100%;
				overflow-x:scroll;
				table{
					width: 1062px;
					margin-left: 15px;
					margin-top: 15px;
				}
			}
		}
  	}
</style>
<style>
	.employeegrowth .el-date-editor--daterange{
		height: 32px;
		margin-top: 10px;
	}
	.employeegrowth .el-input{
		width: 180px;
		height: 32px;
	}
	.employeegrowth .el-input__inner{
		height: 32px;
	}
	.employeegrowth .el-button{
		padding: 5px 10px;
		height: 32px;
	}
	.employeegrowth .departureStyle{
		margin-left: 45px;
	}
</style>