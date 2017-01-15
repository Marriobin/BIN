<html>
<head>
<script charset="UTF-8">
//在下面的括号内写入抽签内容，每个内容需要用双引号包括
var names=new Array(
	"6600","10400","10700","13700","14900","5400","3600","7200","4800","6000","4200","3300","12500","8400","8900","2400","6900","13100","12200","3000","9800","900","14300","5100","11300","600","9500","9200","6300","11000","7800","7500","11600","2700","1800","2100","5700","3900","1500","1200","10100","4500","8100","11900"
	);
var answers=new Array(
	"21700","34100","35100","44900","48900","17700","11800","23600","15700","19700","13800","10800","41100","27600","29100","7900","22600","43000","40100","9800","32100","3000","46900","16700","37100","2000","31100","30100","20700","36100","25600","24600","38100","8900","5900","6900","18700","12800","4900","3900","33100","14800","26600","39100"
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
	show="米制: "+c;
	names.splice(a,1);
	document.getElementById("demo").innerHTML=show;
	document.getElementById("demo2").innerHTML="请点击答案";
}
function displayAnswer()
{	
	if(c=="Null")
	{
		document.getElementById("demo2").innerHTML="没有了";
		return;
	}
	var ans=dic[c];
	answer="英制："+ans;
	document.getElementById("demo2").innerHTML=answer;
}
</script>
</head>
	<body>
		<div id="box">
			<table width="100%" height="100%">
				<tr>
					<td align="center">
						<h1>米制高度层</h1>
						<p id="demo">请点击开始</p>
						<button type="button" onclick="RandomSelect()">开始									</button>
						<button type="button" onclick="displayAnswer()">答案
						</button>
						<p id="demo2">请点击答案</p>
					</td>
				</tr>
			</table>
		</div>
	</body>
</html>
