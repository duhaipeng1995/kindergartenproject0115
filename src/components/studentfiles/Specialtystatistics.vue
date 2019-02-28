<template>
	<div class="specialtystatistics">
		<div class="specialtystatisticsContent">
			<div class="sharingTitle">
				<h3>学生档案</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>特长统计</h3>
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
						<h3>所属园区:</h3>
						<li class="style">全部</li>
						<li>星光幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
					</ul>
					<ul class="park">
						<h3>所属类别:</h3>
						<li class="style">全部</li>
						<li>0001书法</li>
						<li>0002英语</li>
						<li>0003数学</li>
						<li>0004轮滑</li>
						<li>0005吉他</li>
					</ul>
					<div class="specialtystatisticsTotal">
						<span>合计人数：<i>121</i></span>
						<span>合计金额：<i>131313</i></span>
						<span>合计收入：<i>131313</i></span>
						<span>合计支出：<i>131313</i></span>
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
				<div class="specialtystatisticsTable">
					<table class="sharingTable">
						<tr>
							<th>特长名称</th>
							<th>金额</th>
							<th>收入比例</th>
							<th>支出比例</th>
							<th>班级</th>
							<th>学习人数</th>
							<th>金额</th>
							<th>收入</th>
							<th>支出</th>
						</tr>
						<tr class="sharingTablecolor_one">
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
						<tr class="sharingTablecolor_two">
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
						<tr class="sharingTablecolor_one">
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
						<tr class="sharingTablecolor_two">
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
export default {
  	name: 'specialtystatistics',
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
  	.specialtystatistics{
  		width: 1200px;
  		margin: 0 auto;
  		position:relative;
  		.specialtystatisticsContent{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.specialtystatisticsTable{
  				width: 100%;
  				margin-bottom: 15px;
  				overflow-x:scroll;
  				table{
  					width:1030px;
  				}
  			}
  			.specialtystatisticsTotal{
  				width: 100%;
  				text-align: right;
  				line-height: 24px;
  				span{
  					margin-right: 35px;
  				}
  			}
  		}
  	}
</style>
<style>
	.specialtystatistics .el-button--text{
		color: #9BC248;
		font-size: 18px;
	}
	.specialtystatistics .el-date-editor--daterange{
		height: 32px;
		margin-top: 10px;
	}
	.specialtystatistics .el-input{
		width: 180px;
		height: 32px;
	}
	.specialtystatistics .el-input__inner{
		height: 32px;
	}
	.specialtystatistics .el-button{
		padding: 5px 10px;
		height: 32px;
	}
	.specialtystatistics .departureStyle{
		margin-left: 45px;
	}
</style>