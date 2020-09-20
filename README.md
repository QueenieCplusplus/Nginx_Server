# Nginx Server
伺服器的設定

 * 可承受的用戶端最大數量
 
         Client = worker_process * worker_connections / 2
         
         其中 worker_connections 是指每條工作處理程序同時連接用戶端的最大數量。
         建議設定為 65535，約莫一條工作處理程序可以做 65535 條連結到相應的用戶端，除以來回一趟，約莫服務 32467 個用戶端。
         此工作處理程序連結數量需要小於 open file resource limit (工作處理程序可以開啟的檔案控制代碼數量)，建議將此資源限制數量設定為 2390251。

 * 設定請求的根目錄

 * 最大連線數
      
 * MIME-Type
      
 * TimeOut
      
 * 單連接請求數上限
      
 * 造訪權限設定
      
 * CPU
      
 * Core
      
 * 事件訊號佇列長度的上限

