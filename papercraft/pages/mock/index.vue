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

    v-text typography
    h1.display-3 タイトル
    h2.display-2 見出し1
    h3.display-1 見出し2
    //- h4.display-1 見出し3
    //- h5.headline headline
    //- h6.title title
    .subheading 濃い字
    //- .body-2
    .body-1 普通のテキスト
    .caption 画像キャプション

    v-text 一枚画像
    v-img(src="http://placekitten.com/750/500")

    v-text カルーセル
    v-carousel(height="300")
      v-carousel-item
        v-img(src="http://placekitten.com/750/750")
      v-carousel-item
        v-img(src="http://placekitten.com/750/751")
      v-carousel-item
        v-img(src="http://placekitten.com/750/752")

    v-text ボタン色
    div
      v-btn(color="primary") primary
      v-btn(color="secondary") secondary
      v-btn(color="accent") accent
      v-btn(color="success") Success
      v-btn(color="error") Error
      v-btn(color="warning") Warning
      v-btn(color="info") Info
    v-text ボタンデザイン
    div
      v-btn(flat) flat
      v-btn() default
      v-btn(depressed) depressed
      v-btn(outline) outline
      v-btn(round) round
      v-btn(block) block
    v-text アイコンボタン
    div
      v-btn(icon): v-icon(color="pink") favorite
      v-btn(icon): v-icon(color="orange") star
      v-btn(icon): v-icon(color="green") cached
    div
      v-btn(fab color="pink"): v-icon(color="white") favorite
      v-btn(fab color="orange"): v-icon(color="white") star
      v-btn(fab color="green"): v-icon(color="white") cached
    v-text カード
    v-container
      v-card
        v-img(src="http://placekitten.com/750/400")
        v-card-title(primary-title) 農業やりませんか？YESか農家で答えてください
        v-action
          v-btn YES
          v-btn 農家
    v-container
      v-card
        v-card-title テキストだけだとこんな感じ<br>テキストテキストテキストテキストテキストテキスト

    v-text リスト
    v-container
      v-list.pa-2
        template(v-for="item in news")
          v-list-tile-content
            v-list-tile-title {{item.title}}
            v-list-tile-sub-title {{item.text}}
          v-divider
    v-text テーブル
    v-container
      v-data-table(:headers="tabledata.headers" :items="tabledata.items" hide-actions="false")
        template(v-slot:items="props")
          td {{props.item.name}}
          td {{props.item.kind}}
          td {{props.item.cal}}
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
      {title:"タイトル１", text:"テキストテキストああああ"},
      {title:"タイトル２", text:"テキストテキストいいいい"},
      {title:"タイトル３", text:"テキストテキストうううう"},
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
