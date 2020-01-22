<template lang="pug">
  .content
    v-toolbar
      v-toolbar-title
        v-img(src="/img/mf/mf_logo.png" width="180")
      v-spacer
      v-menu(offset-y)
        template(v-slot:activator="{ on }")
          v-btn(icon v-on="on")
            v-icon menu
        v-list
          v-list-tile
            v-list-tile-title トップ
          v-list-tile
            v-list-tile-title 企業情報
          v-list-tile
            v-list-tile-title アクセス
    v-breadcrumbs(:items="breadcrumbs" divider=">")
    v-carousel(height="157")
      v-carousel-item
        v-img(src="/img/material/jojo_23.png")
      v-carousel-item
        v-img(src="/img/material/jojo_24.png")
      v-carousel-item
        v-img(src="/img/material/jojo_25.png")
    h1.display-1 野郎・オブ・クラッシャー！！
    v-container
      v-card
        v-img(src="/img/material/jojo_02.png")
        v-card-title(primary-title) 見てらっしゃい、アンタなんてパパにひねりつぶされるから！
        v-action
          v-btn YES
          v-btn NO
    v-container
      v-list.pa-2
        template(v-for="item in news")
          v-list-tile-content
            v-list-tile-title {{item.title}}
            v-list-tile-sub-title {{item.text}}
          v-divider
    div
      v-btn(color="primary")  1.心臓病
      v-btn(color="secondary") 2.チャックノリス
      v-btn(color="accent") 3.癌
    v-container
      v-card
        v-card-title 容疑者は男性、190cm、髪は茶、筋肉モリモリマッチョマンの変態だ

    v-footer
      span &copy; 2019 fork
</template>

<style lang="stylus">
  p
    font-size 20px
    color red
</style>

<script>
export default {
  data: ()=> ({
    breadcrumbs: [
      {text: "TOP", href:"#", disabled: false},
      {text: "パン", href:"#", disabled: false},
      {text: "くず", href:"#", disabled: true},
    ],
    news: [
      {title:"チャック・ノリス", text:"は玉ねぎを泣かせる"},
      {title:"チャック・ノリス", text:"は時計をしない。彼が今、何時何分かを決めるのだ"},
      {title:"チャック・ノリス", text:"は死を恐れてなどいない。死が彼を恐れているのだ"},
    ],
    tabledata: {
      headers:[
        {text:"名前",value:"name"},
        {text:"種類",value:"kind"},
        {text:"カロリー",value:"cal"}
      ],
      items:[
        {name:"ピザ",kind:"焼き物",cal:"ゼロ（トマトソースは野菜なので）"},
        {name:"エビフライ",kind:"揚げ物",cal:"ゼロ（カロリーは熱に弱いので）"},
        {name:"ドーナツ",kind:"スイーツ",cal:"ゼロ（カロリーが集まる中心に穴が空いているので）"},
      ]
    }
  })
}
</script>
