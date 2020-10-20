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

          const MessageObj = {"type":"flex","altText":"小組聚會通知","contents":       {"type":"bubble","size":"mega","header":{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"vertical","contents":[{"type":"text","text":"10.21 (三) 承恩堂週三職青小組","color":"#ffffff66","size":"sm"},{"type":"text","text":"專業分享聚會","color":"#ffffff","size":"xl","flex":4,"weight":"bold"}]}],"paddingAll":"20px","backgroundColor":"#0367D3","spacing":"md","paddingTop":"22px"},"body":{"type":"box","layout":"vertical","contents":[{"type":"text","text":"* 若需服事調整或請假,請私訊正和,謝謝~","color":"#b7b7b7","size":"xs"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"破冰：名謹","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"08:00","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"敬拜：宣君","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"08:20","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"靈修分享：正和,詩婷","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"08:30","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"vertical","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"cornerRadius":"30px","height":"12px","width":"12px","borderColor":"#EF45DD","borderWidth":"2px"},{"type":"filler"}],"flex":0},{"type":"text","text":"主題分享：梁逢烈弟兄","gravity":"center","flex":4,"size":"sm"}],"spacing":"lg","cornerRadius":"30px","margin":"xl"},{"type":"box","layout":"horizontal","contents":[{"type":"box","layout":"baseline","contents":[{"type":"filler"}],"flex":1},{"type":"box","layout":"vertical","contents":[{"type":"box","layout":"horizontal","contents":[{"type":"filler"},{"type":"box","layout":"vertical","contents":[],"width":"2px","backgroundColor":"#B7B7B7"},{"type":"filler"}],"flex":1}],"width":"12px"},{"type":"text","text":"09:30","gravity":"center","flex":4,"size":"xs","color":"#8c8c8c"}],"spacing":"lg","height":"24px"},{"type":"separator","margin":"10px"},{"type":"text","text":"講者介紹 : 梁逢烈弟兄是承恩堂的會友，目前任職於德州儀器，他將會跟社青們分享他的家庭與職涯發展的心路歷程","size":"md","style":"normal","wrap":true,"position":"relative","align":"start","weight":"regular"}]}  }   }
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
