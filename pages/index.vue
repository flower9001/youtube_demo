<template lang="pug">
  div
    Header/
    main.container
      ul#tabs.pt-3.px-0.d-flex.justify-content-start.justify-content-lg-center.overflow-hidden( :class="{ active: isDown }" @mousedown="mouseDown" @mosuedown="isDown = false" @mouseleave="isDown = false" @mousemove="mousemove")
        li.d-inline.mx-2(v-for="(tab, index) in tabs" :key="index")
          a( href="#" )
            span.badge.border.rounded-pill.bg-light.text-dark.fz-14.px-3.py-2(  :class="{ dark: nowTab === tab }" @click.prevent="nowTab = tab" ) {{ tab }}       
      article.row.g-3
        section.col-sm-6.col-md-4.col-xl-3.mb-4(v-for="(video, index) in videos" :key="index")
          a.video(href="#" @mouseleave="video.show = !video.show" @mouseenter="video.show = !video.show")
            .position-relative  
              img.w-100(:src="video.picture")/     
              .d-flex.flex-column.position-absolute.top-0.end-0.mx-2
                a.showIcon.my-1( href="#" )
                  i.far.fa-clock.fa-lg.bg-dark.text-white.d-flex.justify-content-center.align-items-center.p-3( :class="{ hide: video.show }" )
                a.showIcon.my-1( href="#" )
                  i.fas.fa-list.fa-lg.bg-dark.text-white.d-flex.justify-content-center.align-items-center.p-3( :class="{ hide: video.show }" )
              p.position-absolute.bg-dark.text-white.px-1.time {{ video.time }}  
            .row.mt-3.mx-0
              .col-1.col-sm-2.p-0.me-3.me-md-2.me-lg-0
                img.rounded-circle( :src="video.user_icon", height="36px" )
              .col.info.p-0
                h2.fz-14.videoTitle {{ video.name }}
                p.mb-0 {{ video.username }}
                p.mb-0 觀看次數： {{ video.num }} • {{ video.date }}
              .col-1
                a( href="#" )
                  i.fas.fa-ellipsis-v( :class="{ hide: video.show }" )
    Footer/
</template>

<script>
import Header from "~components/Header"
import Footer from "~components/Footer"
import girl from "~assets/images/girl.jpg"
import music_icon from "~assets/images/music_icon.jpg"
import ghost from "~assets/images/ghost.png"
import ghost_icon from "~assets/images/ghost_icon.jpg"
import cat from "~assets/images/cat.png"
import idle_icon from "~assets/images/idle_icon.jpg"
import suraimu from "~assets/images/suraimu.png"
import muse_icon from "~assets/images/muse_icon.jpg"

export default {
  data() {
    return {
      tabs: ["全部", "音樂", "直播中", "卡通", "烹飪節目", "寵物", "動作冒險遊戲", "最新上傳"],
      videos: [
        {
          name: "終於找到這首一直喊“吶吶吶”的歌了，前奏超燃，太好聽了！",
          username: "番茄音乐秀",
          num: "64萬次",
          date: "2 個月前",
          time: "3:15",
          picture: girl,
          user_icon: music_icon,
          show: true
        },
        {
          name: "關於我轉生變成史萊姆這檔事(S2) 第43話【開宴的信號】｜Muse木棉花 動畫 線上看",
          username: "Muse木棉花-TW",
          num: "22萬次",
          date: "3 天前",
          time: "23:43",
          picture: suraimu,
          user_icon: muse_icon,
          show: true
        },
        {
          name: "【惡魔貓男】貓奴注意！貓的制裁降臨人間！貢獻社會的時刻到了！來自底層廢物的覺醒 化身黑暗使者！feat. 飯糰、甜約翰 曼達｜反正我很閒",
          username: "反正我很閒",
          num: "207萬次",
          date: "1 年前",
          time: "3:44",
          picture: cat,
          user_icon: idle_icon,
          show: true
        },
        {
          name: "【微鬼畫】在家也可能遇到!多出來的腳步聲",
          username: "微疼",
          num: "20萬次",
          date: "23 小時前",
          time: "9:03",
          picture: ghost,
          user_icon: ghost_icon,
          show: true
        },
        {
          name: "終於找到這首一直喊“吶吶吶”的歌了，前奏超燃，太好聽了！",
          username: "番茄音乐秀",
          num: "64萬次",
          date: "2 個月前",
          time: "3:15",
          picture: girl,
          user_icon: music_icon,
          show: true
        },
        {
          name: "關於我轉生變成史萊姆這檔事(S2) 第43話【開宴的信號】｜Muse木棉花 動畫 線上看",
          username: "Muse木棉花-TW",
          num: "22萬次",
          date: "3 天前",
          time: "23:43",
          picture: suraimu,
          user_icon: muse_icon,
          show: true
        },
        {
          name: "【惡魔貓男】貓奴注意！貓的制裁降臨人間！貢獻社會的時刻到了！來自底層廢物的覺醒 化身黑暗使者！feat. 飯糰、甜約翰 曼達｜反正我很閒",
          username: "反正我很閒",
          num: "207萬次",
          date: "1 年前",
          time: "3:44",
          picture: cat,
          user_icon: idle_icon,
          show: true
        },
        {
          name: "【微鬼畫】在家也可能遇到!多出來的腳步聲",
          username: "微疼",
          num: "20萬次",
          date: "23 小時前",
          time: "9:03",
          picture: ghost,
          user_icon: ghost_icon,
          show: true
        },
        {
          name: "終於找到這首一直喊“吶吶吶”的歌了，前奏超燃，太好聽了！",
          username: "番茄音乐秀",
          num: "64萬次",
          date: "2 個月前",
          time: "3:15",
          picture: girl,
          user_icon: music_icon,
          show: true
        },
        {
          name: "關於我轉生變成史萊姆這檔事(S2) 第43話【開宴的信號】｜Muse木棉花 動畫 線上看",
          username: "Muse木棉花-TW",
          num: "22萬次",
          date: "3 天前",
          time: "23:43",
          picture: suraimu,
          user_icon: muse_icon,
          show: true
        },
        {
          name: "【惡魔貓男】貓奴注意！貓的制裁降臨人間！貢獻社會的時刻到了！來自底層廢物的覺醒 化身黑暗使者！feat. 飯糰、甜約翰 曼達｜反正我很閒",
          username: "反正我很閒",
          num: "207萬次",
          date: "1 年前",
          time: "3:44",
          picture: cat,
          user_icon: idle_icon,
          show: true
        },
        {
          name: "【微鬼畫】在家也可能遇到!多出來的腳步聲",
          username: "微疼",
          num: "20萬次",
          date: "23 小時前",
          time: "9:03",
          picture: ghost,
          user_icon: ghost_icon,
          show: true
        },
        {
          name: "終於找到這首一直喊“吶吶吶”的歌了，前奏超燃，太好聽了！",
          username: "番茄音乐秀",
          num: "64萬次",
          date: "2 個月前",
          time: "3:15",
          picture: girl,
          user_icon: music_icon,
          show: true
        },
        {
          name: "關於我轉生變成史萊姆這檔事(S2) 第43話【開宴的信號】｜Muse木棉花 動畫 線上看",
          username: "Muse木棉花-TW",
          num: "22萬次",
          date: "3 天前",
          time: "23:43",
          picture: suraimu,
          user_icon: muse_icon,
          show: true
        },
        {
          name: "【惡魔貓男】貓奴注意！貓的制裁降臨人間！貢獻社會的時刻到了！來自底層廢物的覺醒 化身黑暗使者！feat. 飯糰、甜約翰 曼達｜反正我很閒",
          username: "反正我很閒",
          num: "207萬次",
          date: "1 年前",
          time: "3:44",
          picture: cat,
          user_icon: idle_icon,
          show: true
        },
        {
          name: "【微鬼畫】在家也可能遇到!多出來的腳步聲",
          username: "微疼",
          num: "20萬次",
          date: "23 小時前",
          time: "9:03",
          picture: ghost,
          user_icon: ghost_icon,
          show: true
        },
      ],
      nowTab: "全部",
      isDown: false,
      startX: null,
      scrollNow: null,
      moveAfter: null,
      move: null,
      nowX: "",
    }
  },
  components: { 
    Header,
    Footer,
  },
  methods: {
    mouseDown(e){
      this.isDown = true;
      this.scrollNow = document.getElementById("tabs").scrollLeft;
      this.startX = e.pageX;
    },
    mousemove(e) {
      if (!this.isDown){return};
      this.moveAfter = e.pageX;
      this.move = this.moveAfter - this.startX;
      this.nowX = document.getElementById("tabs").scrollLeft = this.scrollNow - this.move;
    }
  },
}
</script>
