<template>
	<div class="expenditure">
		<div class="expenditureContent">
			<div class="sharingTitle">
				<h3>园所经营</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>支出数据</h3>
					<div class="sharingLink">
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
						<li>支付宝</li>
						<li>微信</li>
						<li>银行卡</li>
					</ul>	
					<ul class="park">
						<h3>均摊维度:</h3>
						<li>平均</li>
						<li>学生人数</li>
						<li>不需要均摊</li>
						<li>自定义</li>
						<li>定义金额</li>
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
				<div class="expenditureText">
					<h3>支出明细表</h3>
				</div>		
				<div class="expenditureTable">
					<table class="sharingTable">
						<tr>
							<th colspan="3">办公费</th>
							<th colspan="3">日用品维修</th>						
							<th colspan="3">厨房买菜</th>						
							<th colspan="3">返托费</th>						
							<th colspan="3">返监控</th>						
							<th colspan="3">返特长</th>						
							<th colspan="3">快乐会议</th>						
							<th colspan="3">工资支出</th>						
							<th colspan="3">校车支出</th>						
							<th colspan="3">水费</th>						
							<th colspan="3">入账总部</th>						
							<th colspan="3">合计</th>						
						</tr>
						<tr>
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
							<td rowspan="2">Data</td>
							<td colspan="2">Data</td>						
						</tr>
						<tr>						
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>						
							<td>Data</td>
							<td>Data</td>
						</tr>
						<tr>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
						</tr>
					</table>
				</div>
				
			</div>
		</div>
	</div>	
</template>

<script>
import axios from 'axios'; 
export default {
  	name: 'expenditure',
  	data () {
    	return {
    		checkList: ['复选框 A'],
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
  	methods:{
  		fn(){
  			axios.post("api/index.php/api/money/ShouRu",{
  				admin_id:admin_id
  			}).then(({data})=>{
  				console.log(data);
  			})
  		}
  	}
}
</script>

<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.expenditure{
  		width:1200px;
  		margin: 0 auto;
  		position:relative;
  		.expenditureContent{
  			width: 912px;
			position: absolute;
			top: 0;
			left: 285px;
			.sharingLink{
				a{
					color:#9bc248;
				}
			}
			.expenditureText{
				width: 100%;
				text-align: left;
				line-height: 98px;
				text-indent: 15px;
				font-size: 26px;
				color: #333;
				h3{
					width: 200px;
					font-weight: normal;
				}
			}
			.expenditureTable{
				width: 100%;
				overflow-x:scroll;
				table{
					width:3138px;
				}
			}
  		}
  	}
</style>
<style>
	.expenditure .el-button--text{
		color: #9BC248;
		font-size: 18px;
	}
	.expenditure .el-date-editor--daterange{
		height: 32px;
		margin-top: 10px;
	}
	.expenditure .el-input{
		width: 180px;
		height: 32px;
	}
	.expenditure .el-input__inner{
		height: 32px;
	}
	.expenditure .el-button{
		padding: 5px 10px;
		height: 32px;
	}
	.expenditure .departureStyle{
		margin-left: 45px;
	}
	.expenditure .el-checkbox-group{
		margin-left: 15px !important;
}
</style>