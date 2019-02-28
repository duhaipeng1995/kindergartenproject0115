<template>
	<div class="payrollsetup">
		<div class="payrollsetupContent">
			<div class="sharingTitle">
				<h3>设置</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>工资表设置</h3>
					<div class="sharingLink">
						<span>计算公式</span>
					</div>
				</div>
				<div class="payrollsetupTable">
					<table class="sharingTable">
						<tr>
							<th>岗位级别</th>
							<th>薪酬级别</th>
							<th>1挡</th>
							<th>2挡</th>
							<th>3挡</th>
							<th>4挡</th>
							<th>5挡</th>
							<th>6挡</th>
							<th>7挡</th>
							<th>8挡</th>
							<th>9挡</th>
							<th>10挡</th>
							<th>11挡</th>
							<th>工资分布</th>
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
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
						</tr>
					</table>
					<table class="sharingTable">
						<tr>
							<th>岗位级别</th>
							<th>薪酬级别</th>
							<th>1挡</th>
							<th>2挡</th>
							<th>3挡</th>
							<th>4挡</th>
							<th>5挡</th>
							<th>6挡</th>
							<th>7挡</th>
							<th>8挡</th>
							<th>9挡</th>
							<th>10挡</th>
							<th>11挡</th>
							<th>工资分布</th>
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
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
							<td>Data</td>
						</tr>
					</table>
				</div>
				<div class="payrollsetupSave">
					<button>保存</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
  	name: 'payrollsetup'
}
</script>

<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.payrollsetup{
  		/*width:1200px;
  		margin: 0 auto;
  		position:relative;*/
  		.payrollsetupContent{
  			/*width:912px;
  			position:absolute;
  			top:0;
  			left:285px;*/
  			.payrollsetupTable{
  				width:100%;
  				overflow-x: scroll;
  				table{
  					width:1200px;
  					margin-top: 15px;
  				}
  			}
  			.payrollsetupSave{
  				width: 912px;
  				text-align: center;
  				button{
  					width: 150px;
  					height: 38px;
  					margin: 30px auto;
  					background: #9BC248;
  					color: #fff;
  					font-size: 18px;
  					border: none; 
  					border-radius: 6px;					
  				}
  			}
  		}
  	}
</style>