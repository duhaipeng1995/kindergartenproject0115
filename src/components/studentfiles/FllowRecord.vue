<template>
		<el-dialog
	  :visible.sync="FllowRecordDialogVisible"
	  center
	   width="500px"
	   height="480px">
	    <div class="marks">
			<h3>跟进记录</h3>
			<div class="response">
				<span>负责人 ：</span>
				<span>xxx</span>
			</div>
			<div class="content">
				<span>跟进记录</span>
				<div class="content_left">
					<span>意向 ：</span>
					<span>有意向</span>
				</div>
				<div class="date">
					date
				</div>
				<textarea class="txt"></textarea>
			</div>
			<div class="content">
				<span>跟进记录</span>
				<div class="content_left">
					<span>意向 ：</span>
					<span>有意向</span>
				</div>
				<div class="date">
					date
				</div>
				<textarea class="txt"></textarea>
			</div>
			<span slot="footer" class="dialog-footer">
		    <el-button @click="$emit('update:FllowRecordDialogVisible',false)">取 消</el-button>
		    <el-button type="primary" @click="$emit('update:FllowRecordDialogVisible',false)">确 定</el-button>
		</span>
	</div>
</el-dialog>
</template>

<script>
	export default {
	name:"fllowrecord",
	props:['FllowRecordDialogVisible'],
    data() {
      return{
//    	console.log(1)
      }
    }
  };
</script>

<style scoped>
	.marks{
		width:500px;
		height:480px;
		border-radius: 5px;
		/*background: red;*/
		/*display: none;*/
		/*position: absolute;*/
	}
	.marks h3{
		text-align: center;
		height:60px;
		line-height: 60px;
		/*background: blue;*/
		font-size:25px;
	}
	.marks .response{
		height:30px;
		line-height: 30px;
		/*background: blue;*/
		padding-left:60px;
		font-size:16px;
		color:#222222;
	}
	.content{
		height:158px;
		/*background: orange;*/
		line-height: 50px;
		padding-left:60px;
		/*background: #00BFFF;*/
	}
	.content>span{
		width:60px;
		/*background: #0E050B;*/
		float: left;
		margin-right:20px;
	}
	.content_left{
		width:120px;
		/*background: red;*/
		float: left;
		margin-left:30px;
	}
	.date{
		/*background: #157EFB;*/
		/*width:120px;*/
		float: left;
	}
	.content .txt{
		display: inline-block;
		width:320px;
		height:85px;
		margin-left:5px;
	}
	.marks h4{
		height:35px;
		padding-left:30px;
		font-size:26px;
		color:#222222;
		font-weight: 100;
	}
	.remarks{
		margin-left:78px;
		height:150px;
	}
	.marks textarea{
		width:200px;
		height:130px;
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