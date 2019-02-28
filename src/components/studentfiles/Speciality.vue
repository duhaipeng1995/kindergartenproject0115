<template>
	<div class="speciality">
		<div class="specialityContent">
			<div class="sharingTitle">
				<h3>学生档案</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>特长管理</h3>
				</div>
				<div class="specialityTable">
					<table class="sharingTable">
						<tr>
							<th>名称</th>
							<th>授课人</th>
							<th>课程费用</th>
							<th>结算比例</th>
							<th>月课时</th>
							<th>配课老师</th>
							<th>课时一</th>
							<th>合计</th>
							<th>费用结算</th>
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
  	name: 'speciality'	
}
</script>

<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.speciality{
  		width: 1200px;
  		margin: 0 auto;
  		position:relative;
  		.specialityContent{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.specialityTable{
  				width: 100%;
  				margin-bottom: 15px;
  				overflow-x:scroll;
  				table{
  					width:1247px;
  				}
  			}
  			
  		}
  	}
</style>