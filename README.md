<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title> Indian Poker </title>

<style>
body{
    text-align:center;
    font-family:sans-serif;
    background:#ADD8E6;
}
button{
    padding:10px 20px;
    margin:10px;
    font-size:16px;
}
#card{
    font-size:24px;
    margin:20px;
    padding:20px;
    border:2px solid black;
}
</style>
</head>
<body>

<h1>ホロライブ インディアンポーカー</h1>

<h3>ルール選択</h3>
<select id="rule">
    <option value="1">身長（高い順）</option>
    <option value="2">誕生日（早い順）</option>
    <option value="3">デビュー順（早い順）</option>
</select>

<br>

<label>
<input type="checkbox" id="showData">
数値をすぐ表示する
</label>

<br>

<button onclick="drawCard()">カードを引く</button>

<div id="card"></div>

<button onclick="reveal()">数値を表示</button>

<script>

const cards = [
["アキ・ローゼンタール","162cm","2/17","2018/6/1"],
["赤井はあと","154cm","8/10","2018/6/2"],
["白上フブキ","155cm","10/5","2018/6/1"],
["夏色まつり","152cm","7/22","2018/6/1"],
["湊あくあ","148cm","12/1","2018/8/8"],
["紫咲シオン","145cm","12/8","2018/8/17"],
["百鬼あやめ","152cm","12/13","2018/9/3"],
["癒月ちょこ","165cm","2/14","2018/9/4"],
["大空スバル","154cm","7/2","2018/9/16"],
["大神ミオ","160cm","8/20","2018/12/7"],
["猫又おかゆ","152cm","2/22","2019/4/6"],
["戌神ころね","156cm","10/1","2019/4/13"],
["兎田ぺこら","153cm","1/12","2017/7/17"],
["不知火フレア","158cm","4/2","2019/8/7"],
["白銀ノエル","158cm","11/24","2019/8/8"],
["宝鐘マリン","150cm","7/30","2019/8/11"],
["天音かなた","149cm","4/22","2019/12/27"],
["桐生ココ","180cm","6/17","2019/12/28"],
["角巻わため","151cm","6/6","2019/12/29"],
["常闇トワ","150cm","8/8","2020/1/3"],
["姫森ルーナ","140cm","10/10","2020/1/4"],
["雪花ラミィ","158cm","11/15","2020/8/12"],
["桃鈴ねね","159cm","3/2","2020/8/13"],
["獅白ぼたん","166cm","9/8","2020/8/14"],
["尾丸ポルカ","153cm","1/30","2020/8/16"],
["ラプラス・ダークネス","139cm","5/25","2021/11/26"],
["鷹嶺ルイ","161cm","6/11","2021/11/27"],
["博衣こより","153cm","3/15","2021/11/28"],
["沙花叉クロヱ","148cm","5/18","2021/11/29"],
["風真いろは","156cm","6/18","2021/11/30"],
["音乃瀬奏","153cm","4/20","2023/9/9"],
["一条莉々華","162cm","5/12","2023/9/9"],
["火威青","171cm","2/27","2023/9/9"],
["儒烏風亭らでん","159cm","2/4","2023/9/10"],
["轟はじめ","155cm","6/7","2023/9/10"],
["響咲リオナ","160cm","5/29","2024/11/9"],
["虎金妃笑虎","172cm","7/25","2024/11/9"],
["水宮枢","145cm","6/16","2024/11/9"],
["輪堂千速","168cm","7/8","2024/11/9"],
["綺々羅々ヴィヴィ","161cm","8/27","2024/11/9"]
];

let currentCard = null;

function drawCard(){
    const rule = parseInt(document.getElementById("rule").value);
    const show = document.getElementById("showData").checked;

    let index = Math.floor(Math.random() * cards.length);
    currentCard = cards[index];

    if(show){
        document.getElementById("card").innerHTML =
            currentCard[0] + "<br>" + currentCard[rule];
    }else{
        document.getElementById("card").innerHTML =
            currentCard[0];
    }
}

function reveal(){
    if(currentCard){
        const rule = parseInt(document.getElementById("rule").value);
        document.getElementById("card").innerHTML =
            currentCard[0] + "<br>" + currentCard[rule];
    }
}

</script>

</body>
</html>
