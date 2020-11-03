<template>
<div class="hello">
  <button @click="sendTargetPicker">Send Sample</button>
</div>
</template>

<script>
import {
  onMounted
} from "vue";
import liff from "@line/liff";
export default {
  name: "HelloWorld",
  setup() {
    onMounted(async () => {
      try {
        await liff.init({
          // liffId: process.env.VUE_APP_SHARE_ID,
          liffId: "1511013263-mRKaGAyM",

        });
        if (!liff.isLoggedIn())
          liff.login({
            redirectUri: window.location.href,
          });
      } catch (err) {
        console.log(`liff.state init error ${err}`);
      }
    });
    async function sendTargetPicker() {
      if (!liff.isLoggedIn()) {
        liff.login({
          redirectUri: window.location.href,
        });
      }
      if (liff.isApiAvailable("shareTargetPicker")) {
        try {
          // {"type":"bubble","size":"mega","header":{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"vertical","contents":[{"type":"text","color":"#ffffff66","size":"sm","text":"eqweqweqw"},{"type":"text","text":"Akihabara","color":"#ffffff","size":"xl","flex":4,"weight":"bold"}]},{"type":"box","layout":"vertical","contents":[{"type":"text","text":"TO","color":"#ffffff66","size":"sm"},{"type":"text","text":"Shinjuku","color":"#ffffff","size":"xl","flex":4,"weight":"bold"}]}],"paddingAll":"20px","backgroundColor":"#0367D3","spacing":"md","height":"154px","paddingTop":"22px"},"body":{"type":"box","layout":"vertical","contents":[{"type":"text","text":"Total: 1 hour","color":"#b7b7b7","size":"xs"},{"type":"box","layout":"horizontal","contents":[{"type":"text","text":"20:30","size":"sm","gravity":"center"},{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF454D","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"Akihabara","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"Walk 4min","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"64px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"text","text":"20:34","gravity":"center","size":"sm"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","width":"12px","height":"12px","borderWidth":"2px","borderColor":"#6486E3"},{"type":"filler"}],"flex":0},{"type":"text","text":"Ochanomizu","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#6486E3"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"Metro 1hr","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"64px"},{"type":"box","layout":"horizontal","contents":[{"type":"text","text":"20:40","gravity":"center","size":"sm"},{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","width":"12px","height":"12px","borderColor":"#6486E3","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"Shinjuku","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px"}]}}
          const MessageObj = {"type":"flex","altText":"小組聚會通知","contents":     {"type":"bubble","size":"mega","header":{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"vertical","contents":[{"type":"text","text":"11.04 (三) 承恩堂週三職青小組","color":"#ffffff66","size":"sm"},{"type":"text","text":"挖掘寶藏-聖誕主題查經","color":"#ffffff","size":"xl","flex":4,"weight":"bold"}]}],"paddingAll":"20px","backgroundColor":"#E80755","spacing":"md","paddingTop":"22px"},"body":{"type":"box","layout":"vertical","contents":[{"type":"text","text":"* 若需請假,請私訊師母或正和","color":"#b7b7b7","size":"xs"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"破冰：正和","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"~08:00","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"敬拜：師母","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"~08:20","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"靈修分享：恩新","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"~08:30","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"主題：聖誕主題查經","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"~09:30","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"separator","margin":"10px"},{"type":"text","text":"* 本週點心預備是媁媁","size":"sm","style":"normal","wrap":true,"position":"relative","align":"start","weight":"regular"},{"type":"text","text":"* 本週也將為11月份壽星們慶生❤️","size":"sm","style":"normal","wrap":true,"position":"relative","align":"start","weight":"regular"},{"type":"text","text":"* 為幫助11/8教會大合照,請明天大家抵達後,一同將會堂裡的木椅移動到招待處","size":"sm","style":"normal","wrap":true,"position":"relative","align":"start","weight":"regular"}]}}   }
          //const MessageObj = {"type":"flex","altText":"您有新訊息","contents":       {"type":"bubble","hero":{"type":"image","url":"https://miro.medium.com/max/2000/1*uSxzrxRE6JnXI2FtrL3okg.png","size":"full","aspectRatio":"20:13","aspectMode":"cover","action":{"type":"uri","uri":"https://line.me/R/ti/p/%40linegametw"}},"body":{"type":"box","layout":"vertical","contents":[{"type":"text","text":"快來加入LINEGAME學院","weight":"bold","align":"center","size":"xl"},{"type":"box","layout":"vertical","margin":"lg","spacing":"sm","contents":[{"type":"box","layout":"baseline","spacing":"sm","contents":[{"type":"text","text":"玩LINE GAME,累計經驗值，拿徽章換獎勵超簡單! 只要1分鐘就能完成專屬學生證，現在就加入","wrap":true,"color":"#666666","size":"sm","flex":5}]}]}]},"footer":{"type":"box","layout":"vertical","spacing":"sm","contents":[{"type":"button","style":"link","height":"sm","action":{"type":"uri","label":"進入學院製作學生證","uri":"https://lin.ee/dbmFATs"}},{"type":"button","style":"link","height":"sm","action":{"type":"uri","label":"加入FB粉絲團獲得最新訊息","uri":"https://lin.ee/uDxrbh"}},{"type":"spacer","size":"sm"}],"flex":0}}         }
          alert(MessageObj);
          const picker = await liff.shareTargetPicker(
            [MessageObj],
            //[
            // // {type: "text", text: "Hello, World112"},
            // {"type":"flex","altText":"this is a flex message","contents":{"type":"bubble","direction":"ltr","hero":{"type":"image","url":"https://game-lguniv.line-scdn.net/Campaign/lgydsg/onepieceevent/03.jpg","align":"center","size":"full","aspectRatio":"1:1","aspectMode":"cover","backgroundColor":"#FFFFFF"},"body":{"type":"box","layout":"vertical","contents":[{"type":"text","text":"你是航海王的忠實粉絲嗎？你對草帽一夥的航海軌跡能夠如數家珍嗎？趕快來參加粉絲挑戰賽，證明你的航海王粉絲度，再把有機會抽中紀念角色的「週刊少年JUMP」轉蛋券x3帶回家！","margin":"xl","align":"center","wrap":true},{"type":"separator","margin":"md"},{"type":"text","text":"※「週刊少年JUMP」轉蛋券將於活動結束後另行發送。","margin":"xl","align":"center","wrap":true}]},"footer":{"type":"box","layout":"vertical","contents":[{"type":"button","action":{"type":"message","label":"考試開始","text":"考試開始"},"color":"#047196","style":"primary"}]}}}
            // ]
            );
          if (picker) {
            // succeeded in sending a message through TargetPicker
            console.log(`[${picker.status}] Message sent!`);
            alert(`[${picker.status}] Message sent!`);
          } else {
            const [majorVer, minorVer] = (liff.getLineVersion() || "").split(
              "."
            );
            if (parseInt(majorVer) == 10 && parseInt(minorVer) < 11) {
              console.log(
                "TargetPicker was opened at least. Whether succeeded to send message is unclear"
              );
            } else console.log("TargetPicker was closed!");
          }
        } catch (error) {
          // something went wrong before sending a message
          console.log(error);
          console.log("Flex Message got some error");
          liff.closeWindow();
        }
      } else console.log("Please login...");
    }
    return {
      sendTargetPicker,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
