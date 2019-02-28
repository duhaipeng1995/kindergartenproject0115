<template>
		<el-dialog
	  :visible.sync="EmployeepromotionMarkDialogVisible"
	  center
	   width="340px"
	   height="250px">
	    <div class="marks">
	    	<h3>晋升职位</h3>
			<div class="attendance_bottom">
				<div class="attendance_top">
						<span>主班</span>
						<span>分园长</span>
						<span>主班</span>
						<span>主班</span>
				</div>
				<div class="attendance_top">
						<span>主班</span>
						<span>分园长</span>
						<span>主班</span>
						<span>主班</span>
				</div>
			</div>
			<span slot="footer" class="dialog-footer">
		    <el-button @click="$emit('update:EmployeepromotionMarkDialogVisible',false)">取 消</el-button>
		    <el-button type="primary" @click="$emit('update:EmployeepromotionMarkDialogVisible',false)">完成</el-button>
		</span>
	</div>
</el-dialog>
</template>

<script>
	export default {
	name:"employeepromotionMark",
	props:['EmployeepromotionMarkDialogVisible'],
    data() {
      return{
//    	console.log(1)
      }
    }
  };
</script>

<style scoped>
	.marks{
		width:320px;
		height:250px;
		border-radius: 5px;
		padding-left: 20px;
		/*background: red;*/
		/*display: none;*/
		/*position: absolute;*/
	}
	.marks h3{
		height: 40px;
		line-height:40px;
		/*background: red;*/
	}
	.marks .attendance_bottom{
		height:140px;
		/*background: blue;*/
		/*margin-top:15px;*/
	}
	.marks .attendance_top{
		height:30px;
		line-height: 30px;
	}
	.marks .attendance_top span{
		margin-right:35px;
	} 
	.dialog-footer{
		padding-left:100px;
		text-align: center;
	}
	.el-button .el-button--default{
		text-align: center;
		margin-left:20px;
	}
	
</style>