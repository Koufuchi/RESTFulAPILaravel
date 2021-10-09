使用 Larevel 實作 RESTful API

部署方式:
1. 將 .env.example 複製改名為 .env 並填入你自己的 mysql 相關資料
2. 產生 APP_KEY 並填入
3. 重建 composer, npm 相關套件
4. 產生公鑰和私鑰
5. 重建資料庫 $ php artisan migrate
6. 建立假資料 $ php artisan db:seed

使用說明:
已寫有 Swagger 文件，在專案部署完成後用瀏覽器打開 http://{你設定的路由}/api/documentation 即有各項說明。
由於寫有身分認證的關係不能直接執行，請執行以下步驟:
1. 首頁點擊 Create New Client 建立新的客戶端，並在 Redirect URL 處填入 http://{你設定的路由}/auth/callback
2. 首頁點擊 Create New Token 建立 Access Tokens，並記住系統給你的 token 值，如果沒記住請重新建一個。(token 進資料表有加密過，所以無法直接從資料表複製)
3. 在 Swagger 文件瀏覽想測試的 API，並將相關資料填入 Postman，並在 Headers 設定 key 為 Authorization，value 輸入「Bearer {系統給的token}」
4. 以上步驟完成就可以使用 Postman 測試所有 API 了


