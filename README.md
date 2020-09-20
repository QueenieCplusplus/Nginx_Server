# Nginx Server
伺服器的設定

 * 可承受的用戶端最大數量
 
         Client = worker_process * worker_connections / 2
         
         其中 worker_connections 是指每條工作處理程序同時連接用戶端的最大數量。
         建議設定為 65535，約莫一條工作處理程序可以做 65535 條連結到相應的用戶端，除以來回一趟，約莫服務 32467 個用戶端。
         此工作處理程序連結數量需要小於 open file resource limit (工作處理程序可以開啟的檔案控制代碼數量)，建議將此資源限制數量設定為 2390251。

 * 設定請求的根目錄
 
 * location 的 URI

 * 最大連線數
      
 * MIME-Type
      
 * time_out
 
     * keepalive_timeot
     
     * send_timeout
     
            設定伺服器回應用戶端的逾時間，這時間是指伺服器和用戶端建立連線後，某活動之後的時間，
            倘若此時間過後，用戶端無任何活動（伺服器等待用戶端回應超過此時間），伺服器則關閉連線 
            (L5 Session Layer 會議層含 Socket 通訊端)。
 
 * buffer_size
 
     * getconf PAGESIZE
     
            設定伺服器允許用端端請求標頁首的緩衝區大小，預設為 1 KB（根據系統分頁大小可調整不同）
     
     * client_header_buffer_size
     
            用戶端可能因為 cookie 中寫入較大的值，引發用戶端請求標頁首大於預設的 1 KB ，
            為了改善伺服器支援的功能，建議預設值調整為 4 KB。
      
 * 單連接請求數上限
      
 * 造訪權限設定
      
 * CPU
      
 * Core
      
 * sigpending 事件訊號佇列長度的上限
 
        每一個工作處理程序有自己事件訊號佇列用於暫存用戶端請求發生訊號，倘若超過長度上限，伺服器會轉用 poll 處理尚未處理的用戶端請求。為了確保用戶端平行處理請求數量和伺服器執行環境處理能力，建議預設為 1024。

