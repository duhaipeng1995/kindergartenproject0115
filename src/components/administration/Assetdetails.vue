<template>	
	<div class="assetdetails">
		<div class="assetdetailsContent">
			<div class="sharingTitle">
				<h3>园所经营</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>资产明细统计</h3>
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
				</div>
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
				</div>
				<div class="assetdetailsTable">
					<table class="sharingTable">
						<tr>
							<th><input type="radio" /></th>
							<th>部门</th>
							<th>责任人</th>
							<th>购置时间</th>
							<th>资产</th>
							<th>数量</th>
							<th>单价</th>
							<th>核销数量</th>
						</tr>
						<tr class="sharingTablecolor_one">
							<td><input type="radio" /></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<input type="text" class="assetdetailsInput"/>
							</td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td><input type="radio" /></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<input type="text" class="assetdetailsInput"/>
							</td>
						</tr>
						<tr class="sharingTablecolor_one">
							<td><input type="radio" /></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<input type="text" class="assetdetailsInput"/>
							</td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td><input type="radio" /></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<input type="text" class="assetdetailsInput"/>
							</td>
						</tr>
					</table>
				</div>
			</div>
			<div class="assetdetailsSubmission">
				<button>提交审核</button>
			</div>
		</div>	
	</div>
</template>

<script>
	export default{
		name:"assetdetails",
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
  	.assetdetails{
  		width: 1200px;
  		margin: 0 auto;
  		position: relative;
  		.assetdetailsContent{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.assetdetailsTable{
  				width: 100%;
  				table{
  					width:880px;
  					margin: 15px auto;
  					.assetdetailsInput{
  						width:80px;
  						height:25px;
  						border:1px solid #dcdcdc;
  						border-radius:5px;
  					}
  				}
  			}
  			.assetdetailsSubmission{
  				width: 100%;
  				text-align: center;
  				button{
  					width:120px;
  					height:38px;
  					margin-top: 40px;
  					border: none;
  					background: #4395FF;
  					color: #fff;
  					font-size: 16px;
  					border-radius: 5px;
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