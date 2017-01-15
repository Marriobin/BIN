<html>
<head>
<script charset="UTF-8">
//在下面的括号内写入抽签内容，每个内容需要用双引号包括
var names=new Array(
	"1","2","3","4","5","6","7","8"
	);
var answers=new Array(
	"赵","钱","孙","李","鸡","毛","蒜","皮"
	);
var dic=new Array();
for(i=0;i<names.length;i++){
	dic[names[i]]=answers[i];
}
var c;//a表示dic中的键值
function RandomSelect()
{	
	if(names.length==0){
		c="Null";
		show="没有了";
		document.getElementById("demo").innerHTML=show;
		document.getElementById("demo2").innerHTML="没有了";
		return;
	}
	var a=parseInt(Math.random(0)*(names.length));
	c=names[a];
	show="序号: "+c;
	names.splice(a,1);
	document.getElementById("demo").innerHTML=show;
	document.getElementById("demo2").innerHTML="暂无";
}
function displayAnswer()
{	
	if(c=="Null")
	{
		document.getElementById("demo2").innerHTML="没有了";
		return;
	}
	var ans=dic[c];
	answer="答案："+ans;
	document.getElementById("demo2").innerHTML=answer;
}
</script>
</head>
	<body>
		<div id="box">
			<table width="100%" height="100%">
				<tr>
					<td align="center">
						<h1>抽奖</h1>
						<p id="demo">等待点击</p>
						<button type="button" onclick="RandomSelect()">开始抽奖
						</button>
						<button type="button" onclick="displayAnswer()">显示答案
						</button>
						<p id="demo2">暂无</p>
					</td>
				</tr>
			</table>
		<div>
	</body>
</html>
