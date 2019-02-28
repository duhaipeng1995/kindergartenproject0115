<template>
	<div class="budget">
		<div class="budgetContent">		
			<div class="sharingTitle">
				<h3>园所经营</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>明细账</h3>
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
						<h3>所属班级:</h3>
						<li class="style">全部</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
					</ul>
					<ul class="park">
						<h3>资金渠道:</h3>
						<li class="style">全部</li>
						<li>微信</li>
						<li>支付宝</li>
						<li>现金</li>
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
							</el-row>
						</div>
					</div>
				</div>
				<div class="budgetTable">
					<table class="sharingTable">
						<tr>
							<th>时间</th>
							<th>园所</th>
							<th>操作人</th>
							<th>班级</th>
							<th>姓名</th>
							<th>收入</th>
							<th>支出</th>
							<th>摘要</th>
							<th>现金渠道</th>
							<th>结余</th>
						</tr>
						<tr class="sharingTablecolor_one">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
						<tr class="sharingTablecolor_one">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
						<tr class="sharingTablecolor_one">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
						<tr class="sharingTablecolor_one">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
							<td>111</td>
						</tr>
					</table>
				</div>
			</div>
		
		</div>
	</div>
	
</template>

<script>
export default {
  	name: 'budget',
  	data () {
  	
    	return {
    		input21: '',
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
}
</script>

<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.budget{
  		width: 1200px;
  		margin: 0 auto;
  		position: relative;
  		.budgetContent{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.budgetTable{
  				width: 100%;
  				margin-top: 15px;
  				margin-bottom: 15px;
  				overflow-x: scroll;
  				table{
  					width:986px;
  				}
  			}
  		}
  	}
	
</style>
<style>
	.budget .el-button--text{
		color: #9BC248;
		font-size: 18px;
	}
	.budget .el-date-editor--daterange{
		height: 32px;
		margin-top: 10px;
	}
	.budget .el-input{
		width: 180px;
		height: 32px;
	}
	.budget .el-input__inner{
		height: 32px;
	}
	.budget .el-button{
		padding: 5px 10px;
		height: 32px;
	}
	.budget .departureStyle{
		margin-left: 45px;
	}
</style>