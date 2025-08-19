# HTTPのRequestとResponseについて

### 1. HTTPRequestについて
- HeaderとBodyがある
- Headerはリクエストの付加的な情報を含めることが出来る
  - Host: 自分のHostアドレス
  - User-Agent: 使用しているブラウザなどの情報
  - Cookie: ブラウザに保存している情報
  - Barere: 認証するためのパスワードなど
- BodyはGetの時は空、Postの時はリクエストパラメータを設定する(KeyValue or JSON)
- Getメソッド
  - データ取得用のメソッド
  - パラメータはURLの後ろに?Key1=Value1&Key2=Value2の形式で指定する
    - 例）Bingで「NSS」を検索すると以下のような形式になる
      ```
      https://www.bing.com/search?q=NSS&form=ANNH01&refig=ff4b60e5f7684f79901b5d8022d5f377&pc=DCTS&adppc=EDGEESS
      ``````
- Postメソッド
  - データ送信用のメソッド
  - パラメータはBodyに含まれる
    - Key&Value形式（HttpのForm）
    - Json形式(apiとか)
- Putメソッド
- Deleteメソッド

### 2. HTTPResponseについて
- ステータスラインでResponseCodeが返ってくる
  - 200番台は正常終了
  - 300番台はリダイレクト系
  - 400番台はエラー系
  - 500番台はエラー系（サーバーの内部エラー）
- Headerはレスポンスの付加的な情報を含めることが出来る
  - Content-Type: HTML or JSON
  - Content-Length: Responseのサイズ
- Body
  - Content-Typeがtext/htmlの場合はHTMLが返ってくる⇒ブラウザが解釈して画面表示
  - Content-Typeがtext/jsonの場合はJsonが返ってくる

### 3. 補足
- ステートレスとは？
  - セッションを使用しない。SmileのアプリはLoginした情報をSessionに保存しているので？
- Curlコマンド
  ```bash
  # -iオプションはResponseのHeaderを表示する
  curl -i https://www.bing.com/
  ```