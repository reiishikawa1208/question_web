<template>

<v-dialog max-width="600px">
    <v-btn slot="activator">
      <v-icon left>description</v-icon>
      <span>サイト説明</span>
    </v-btn>
    <v-card>
      <v-card-text>
        <p>このサイトは、エンジニアの為の質問サイトです。勉強や仕事で「わからないことを聞ける人がいない」という方の役に立てればと思い作成しました。全てのご質問にRAYが回答します。（<a href="https://rayy-blog.com/profile/" target="_blank">RAYのプロフィールはこちら</a>)</p>
        <h3>※注意点</h3>
        <ul>
          <li>RAYが知っている範囲で回答致します</li>
          <li>質問の内容によっては回答を拒否することがございます（ご了承ください）</li>
          <li>匿名での投稿となります</li>
          <li>回答日は遅くなる可能性がございます</li>
        </ul>
      </v-card-text>
    </v-card>
</v-dialog>

</template>
