# 1111
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        body {
            font-family: "黑体";
            background: skyblue;
        }
        button {
            border: none;
            outline-style: none;
            border-radius: 3px;
        }

        .box {
            width: 500px;
            margin: 20px auto;
            margin-bottom: 30px;
            text-align:center;
        }
        .bbox{
            width: 500px;
            height: 30px;
            text-align:center;
            margin-bottom: 30px;
        }
        h1{
            font-family: 黑体;
        }

        .boxBox {
            width: 100%;
            height: 35px;
            border-radius: 10px;
            border: 1px solid gray;
            margin-bottom: 15px;
        }

        .boxBox div {
            float: left;
            width: 80px;
            height: 100%;
            border-radius: 10px 0 0 10px;
            text-align: center;
            line-height: 35px;
            color: black;
            background: #DFDFDF;
        }

        .boxBox input {
            width: 410px;
            height: 100%;
            outline-style: none;
            border: none;
            box-sizing: border-box;
            padding-left: 10px;
            background: skyblue;
        }

        .btn {
            height: 35px;
        }

        .btn button {
            width: 150px;
            height: 100%;
            margin-right: 10px;
        }

        #preserve {
            background: blue;
            color: white;
        }

        #reset{
            background: white;
            border: 1px solid gray;
        }

        .tab {
            width: 500px;
            margin: 0 auto;
        }

        th {
            border-top: 1px solid gray;
            height: 40px;
        }

        .tab td {
            border-top: 1px solid gray;
            height: 40px;
            text-align: center;
            font-size: 14px;
        }

        .revamp{
            background: green;
        }

        .cancel{
            background: red;
            color: white;
        }


        .box2 {
            width: 600px;
            padding-left: 35px;
            padding-right: 35px;
            background: skyblue;
            position: absolute;
            left: 25%;
            top: 8px;
            display: none;
            border-radius: 140px;
            padding-bottom: 20px;
            box-shadow: 10px 10px 10px black;

        }

        .revampBtn {
            text-align: right;
        }

        #shut {
            width: 65px;
            background: white;
            border: 1px solid gray;
            height: 35px;
            color: black;
        }

        #saveChange {
            width: 150px;
            height: 35px;
            background:orange;
            color: white;
            margin-left: 15px;
        }
    </style>
</head>
<body id="bigBack">

<div class="box">
     <div class="bbox">
    <h1>表单 Subtext for header</h1>
</div>
    <div class="boxBox">
        <div>姓名</div>
        <input type="text" placeholder="请输入姓名" class="userName">
    </div>
    <div class="boxBox">
        <div>联系电话</div>
        <input type="text" placeholder="请输入手机号" class="phone">
    </div>
    <div class="boxBox">
        <div>学历</div>
        <input type="text" placeholder="请输入学历" class="educC">
    </div>
    <div class="boxBox">
        <div>年龄</div>
        <input type="text" placeholder="请输入年龄" class="age">
    </div>
    <div class="boxBox">
        <div>期望薪资</div>
        <input type="text" placeholder="您的期望薪资是？" class="money">
    </div>
    <div class="btn">
        <button id="preserve">保存</button>
        <button id="reset">重置</button>
    </div>
</div>
<div class="box box2">
    <div class="hintText">
        <h3>请修改信息</h3>
    </div>
    <div class="boxBox">
        <div>姓名</div><input type="text" placeholder="请输入姓名" class="userName revampName">
    </div>
    <div class="boxBox">
        <div>联系电话</div><input type="text" placeholder="请输入手机号" class="phone revampPhone">
    </div>
    <div class="boxBox">
        <div>学历</div><input type="text" placeholder="请输入学历" class="educC revampeducC">
    </div>
    <div class="boxBox">
        <div>年龄</div><input type="text" placeholder="请输入年龄" class="age revampAge">
    </div>
    <div class="boxBox">
        <div>期望薪资</div><input type="text" placeholder="您的期望薪资是？" class="moneyrevamp">
    </div>
    <div class="revampBtn">
        <button id="shut">关闭</button>
        <button id="saveChange">保存修改</button>
    </div>
</div>
<table class="tab"
       cellspacing="0" cellspacing="0" ;>
    <tr>
        <th>姓名</th>
        <th>联系电话</th>
        <th>学历</th>
        <th>年龄</th>
        <th>期望薪资</th>
        <th>操作</th>
    </tr>
    <tr>
        <td>Steven.Jobs</td>
        <td>13701364084</td>
        <td>大学辍学</td>
        <td>45</td>
        <td>$2300000</td>
        <td>
            <button class="revamp">修改</button>
            <button class="cancel">删除</button>
        </td>
    </tr>
</table>
</body>
</html>
<script src="js/jquery-1.8.3.min.js"></script>
<script>
// 姓名
$(".userName").blur(function () {
    let value = $(this).val()
    let reg = /^[\u4E00-\u9FA5A]{2,4}$/
    changeStyle($(this), value, reg)
})
// 电话
$(".phone").blur(function () {
    let value = $(this).val()
    let reg = /^(13|15|16|17|18|19)\d{9}$/;
    changeStyle($(this), value, reg)
})
// 学历
$(".educC").blur(function () {
    let value = $(this).val()
    let reg = /^[\u4E00-\u9FA5A]{2}$/
    if (value == "小学" || value == "初中" || value == "高中" || value == "大专" || value == "本科" || value == "研究生" || value == "博士"|| value=="博士后") {
        changeStyle($(this), value, reg)
    } else {
        alert("请好好输")
        changeStyle($(this), value, reg)
    }
})
// 年龄
$(".age").blur(function () {
    let value = $(this).val()
    if (value.length > 3 || value.length < 0) {
        alert("输入错误")
    } else {
        let reg = /^[1-9]{1,2}$/;
        changeStyle($(this), value, reg)
    }
})
// 期望
$(".money").blur(function () {
    let value = $(this).val()
    let reg = /^\d{1,}$/;
    changeStyle($(this), value, reg)
})

// 提交
$("#preserve").click(function () {
    if ($(".userName").val() != "" && $(".phone").val() != "" && $(".educC").val() != "" && $(".age").val() != "" && $(".money").val() != "") {
        let tr = document.createElement("tr");
        tr.innerHTML = `<td>${$(".userName").val()}</td>
    <td>${$(".phone").val()}</td>
    <td>${$(".educC").val()}</td>
    <td>${$(".age").val()}</td>
    <td>${$(".money").val()}</td>
    <td>
        <button class="revamp">修改</button>
        <button class="cancel">删除</button>
    </td>`;
        $(".tab").append(tr)
    }
})
// 重置
$("#reset").click(function () {
    $(".userName").val("")
    $(".phone").val("")
    $(".educC").val("")
    $(".age").val("")
    $(".money").val("")
})
function changeStyle(obj, value, reg) {
if (value == "" || !reg.test(value)) {
    obj.parent().css({
        "border": "1px solid red"
    })
    obj.prev().css({
        "background": "pink",
        "color": "red"
    })
} else if (reg.test(value)) {
    obj.parent().css({
        "border": "1px solid green"
    })
    obj.prev().css({
        "background": "#70DB93",
        "color": "#238E23"
    })
}
}
// 点击修改
$(".tab").click(function (e) {
    let event = e || window.event
    let target = event.target || event.srcElement
    if (target.tagName == "BUTTON") {
        if (target.className == "revamp") {
            $(".box2").css({
                "display": "block"
            })
            $("#bigBack").css({
                "background": "rgba(52, 52, 52, 0.5)"
            })
            $(".box2").html($(".box1").html())
        }
    }
})
// 点击删除
$(".tab").click(function (e) {
    let event = e || window.event
    let target = event.target || event.srcElement
    if (target.tagName == "BUTTON") {
        if (target.className == "cancel") {
            target.parentNode.parentNode.remove()
        }
    }
})
// 点击关闭
$("#shut").click(function () {
    $(".box2").css({
        "display": "none"
    })
    $("#bigBack").css({
        "background": "none"
    })
})
// onblur颜色变化
function changeStyle(obj, value, reg) {
    if (value == "" || !reg.test(value)) {
        obj.parent().css({
            "border": "1px solid red"
        })
        obj.prev().css({
            "background": "pink",
            "color": "red"
        })
    } else if (reg.test(value)) {
        obj.parent().css({
            "border": "1px solid green"
        })
        obj.prev().css({
            "background": "#70DB93",
            "color": "#238E23"
        })
    }
}
// 保存修改
$("#saveChange").click(function () {
    let tr = document.createElement("tr");
    tr.innerHTML = `<td>${$(".revampName").val()}</td>
<td>${$(".revampPhone").val()}</td>
<td>${$(".revampeducC").val()}</td>
<td>${$(".revampAge").val()}</td>
<td>${$(".moneyrevamp").val()}</td>
<td>
    <button class="revamp">修改</button>
    <button class="cancel">删除</button>
</td>`;
    $(".tab").append(tr)
    $(".box2").css({
        "display": "none"
    })
})

</script>     
