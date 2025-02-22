---
title: はじめに
description: "Nuxt.js は Vue アプリケーションを作成するフレームワークです。ユニバーサルアプリケーション、静的に生成されるアプリケーション、シングルページアプリケーションの中から作成するアプリケーションを選ぶことができます。"
---

> Nuxt.js は Vue アプリケーションを作成するフレームワークです。ユニバーサルアプリケーション、静的に生成されるアプリケーション、シングルページアプリケーションの中から作成するアプリケーションを選ぶことができます。

## Nuxt.js とは何か？

サーバサイドとクライアントサイドのディストリビューションを抽象化しつつ **UI レンダリングすること**に焦点を当てています。

私たちのゴールは、メインプロジェクトの基礎として利用したり、既存の Node.js ベースのプロジェクトに追加したりできるような柔軟なフレームワークを作成することです。

Nuxt.js は**サーバーサイドレンダリング**をもっと楽しめるように Vue.js アプリケーションの開発に必要な設定をあらかじめプリセットしています。

加えて、_nuxt generate_ と呼ばれる別の開発オプションも提供しています。これは**静的に生成された** Vue.js アプリケーションを構築します。
私たちはこのオプションが、マイクロサービスなウェブアプリケーションの開発において次なる大きな一歩になり得ると信じています。

さらに、Nuxt.js はシングルページアプリケーション（`spa` モード）を手早く作成する際にも使えます。バックオフィスのアプリケーションとして動きつつ、Nuxt の機能を使うのに便利です。

フレームワークとして、Nuxt.js はクライアントサイドとサーバーサイド間の開発を手助けするたくさんの機能を備えています。例えば、非同期でのデータのやり取りや、ミドルウェアとしての利用、レイアウト機能などがあります。

## どのように動作するか？

![Vue with webpack and Babel](https://i.imgur.com/avEUftE.png)

Nuxt.js はリッチなウェブアプリケーションを構築するために下記のものを含んでいます:

- [Vue 2](https://vuejs.org/)
- [Vue Router](https://router.vuejs.org/ja/)
- [Vuex](https://vuex.vuejs.org/ja/)（[ストアオプション](/guide/vuex-store)を利用している場合に限る）
- [Vue Server Renderer](https://ssr.vuejs.org/ja/)（[`mode: 'spa'`](/api/configuration-mode) を利用している場合を除く）
- [vue-meta](https://github.com/declandewet/vue-meta)

すべて合わせてもわずか **57kB min+gzip** です。（Vuex 利用時は 60kB）

バンドルやソースコードの分割やミニファイ化するために内部で [webpack](https://github.com/webpack/webpack)、[vue-loader](https://github.com/vuejs/vue-loader) と [babel-loader](https://github.com/babel/babel-loader) を使います。

## 主な機能

- Vue ファイルで記述できること（`*.vue`）
- コードを自動的に分割すること
- サーバーサイドレンダリング
- 非同期データをハンドリングするパワフルなルーティング
- 静的ファイルの配信
- [ES2015+](https://babeljs.io/docs/en/learn/) のトランスパイレーション
- JS と CSS のバンドル及びミニファイ化
- `<head>` 要素（`<title>`、`<meta>` など）の管理
- 開発モードにおけるホットリローディング
- プリプロセッサ: Sass, Less, Stylus など
- HTTP/2 push headers ready
- モジュール構造で拡張できること

## 図解

下の図は、サーバーサイドで処理が実行されたときや、ユーザーが `<nuxt-link>` を通して遷移したときに Nuxt.js によって何が呼び出されるかを表しています:

![nuxt-schema](/nuxt-schema.svg)

## サーバーサイドレンダリング（ユニバーサル SSR）

Nuxt.js をプロジェクトの UI レンダリング全体を担うフレームワークとして使うことができます。

`nuxt` コマンドを実行すると開発サーバーが起動します。このサーバーはホットリローディング及び [Vue Server Renderer](https://ssr.vuejs.org/ja/) を備えており、アプリケーションが自動的にサーバーサイドレンダリングするよう設定されています。

### シングルページアプリケーション（SPA）

もし何らかの理由でサーバーサイドレンダリングを使いたくない、あるいはアプリケーションを静的にホスティングする必要があるときは `nuxt --spa` を使って、シンプルに SPA モードを使うことができます。_generate_ 機能と組み合わせて使うことで、Node.js ランタイムや特別なサーバー処理を利用する必要なしに、SPA のパワフルなデプロイを実現できます。

コマンドについてより深く理解するには [コマンド](/guide/commands) を参照してください。

既にサーバーがあるならば Nuxt.js をミドルウェアとして追加することができます。ユニバーサルなウェブアプリケーションの開発に Nuxt.js を利用する際、制限は何ひとつありません。 [Nuxt.js をプログラム的に使う](/api/nuxt) ガイドを参照してください。

## 静的ファイルの生成

`nuxt generate` コマンドにより Nuxt.js に大きなイノベーションがやってきました。

アプリケーションをビルドする際、ルートやストアにあるファイル全てに対し HTML を生成します。

<div>
  <a href="https://vueschool.io/courses/static-site-generation-with-nuxtjs?friend=nuxt" target="_blank" class="Promote">
    <img src="/static-site-generation-with-nuxtjs.png" alt="Static Site Generation with Nuxt.js by vueschool"/>
    <div class="Promote__Content">
      <h4 class="Promote__Content__Title">Nuxt.js による静的サイト生成</h4>
      <p class="Promote__Content__Description">ホスティングコストを削減しながら、パフォーマンスと SEO の両方を向上させるために静的サイトを生成する方法（プリレンダリング）を学びます。</p>
      <p class="Promote__Content__Signature">ビデオコースは Nuxt.js での開発をサポートするために VueSchool によって作られました｡</p>
    </div>
  </a>
</div>

例えば、以下のファイル構成だった場合:

```bash
-| pages/
----| about.vue
----| index.vue
```

次のファイルが生成されます:

```
-| dist/
----| about/
------| index.html
----| index.html
```

この方法により、生成されたウェブアプリケーションをどの静的ウェブサイトホスティングにもホストできます！

最も良い例はこのウェブサイト自体です。このサイトは [Netlify](https://www.netlify.com) で生成されホストされています。[ソースコード](https://github.com/nuxt/nuxtjs.org)を参照してください。

[docs repository](https://github.com/nuxt/docs) をアップデートするたびに手動でアプリケーションを生成したくないので、Netlify のフックへのトリガーにします：

1. [nuxtjs.org リポジトリ](https://github.com/nuxt/nuxtjs.org)をクローンする
2. `npm install` で依存関係のあるパッケージをインストールする
3. `npm run generate` を実行する
4. `dist` ディレクトリに配置する

これで自動化された**静的に生成されたウェブアプリケーション**ができます。:)

さらに `nuxt generate` で生成、CDN でホストされた E コマースのウェブアプリケーションを考えてみましょう。このアプリケーションは商品が在庫切れもしくは再入荷されるたびに再生成されます。ユーザーがアプリケーションを遷移している間に、在庫の状態が（再生成のおかげで）最新になるのです。もはや、サーバーで複数のインスタンスやキャッシュを持つ必要はないのです！

<div class="Alert">

Netlify へデプロイする方法についての詳細は [Netlify へデプロイするには？](/faq/netlify-deployment) を参照してください。

</div>
