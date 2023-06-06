# ディレクトリ作成
mkdir jspreadsheet

# vueの初期化
vue create .

# 起動
npm run serve

# インストール系統
# install jspreadsheet
yarn install
yarn add vuex
yarn add vuex-persist
yarn add vue-router
yarn add vuex-pathify
yarn add jspreadsheet
yarn add jspreadsheet vue

# install jexcel
yarn install
yarn add vuex
yarn add vuex-persist
yarn add jexcel
yarn add vue-router
yarn add vuex-pathify
yarn add jspreadsheet vue

# 実装予定
・保存機能
・SQL変更機能
・保存時にイベント発生

# Jspreadsheetとは
JavaScript で Excel 風スプレッドシートを実現するライブラリです。
jExcel という名前でしたが Jspreadsheet に名称変更したようです。
無償版(MITライセンス)の Jspreadsheet CE、有償版の Jspreadsheet Pro、クラウド版の Jspreadsheet Cloud があります。
同じ作者による Jsuites というライブラリを使用しています。
JS配列、JSON、CSV、XSLXファイルからデータを読み取ることができます。
Excel から Jspreadsheet に、またはその逆にデータをコピー＆ペーストすることができます。
プラグイン機能によりカスタムカラムやカスタムエディターを拡張することができます。
ここでは Jspreadsheet CE v4 について説明します。# jspreadsheet-vue
