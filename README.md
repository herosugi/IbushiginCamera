# IbushiginCamera
IbushiginCamera for GR-LYCHEE - OpenCV

# いぶし銀カメラ
2018/02/24 [FlashAir Developers Summit 2018](https://flashair-developers.com/ja/about/events/summit2018/) 場所:LODGE - Yahoo Japan  
[GR-LYCHEE - Mbed](https://os.mbed.com/platforms/Renesas-GR-LYCHEE/)  
[GR-LYCHEE - GADGET RENESAS](https://os.mbed.com/platforms/Renesas-GR-LYCHEE/)  
[GR-LYCHEE - CORE](http://www.core.co.jp/product/m2m/gr-lychee/)  
[AS-289R2 Thermal Printer Shield - Mbed](https://os.mbed.com/components/AS-289R2-Thermal-Printer-Shield/)  
[AS-289R2 Thermal Printer Shield - NADA ELECTRONICS](http://www.nada.co.jp/as289r2/)  
[FlashAir W-04 - TOSHIBA](https://flashair-developers.com/ja/discover/overview/w04/)  

![IbushiginCamera](https://github.com/NADA-ELECTRONICS/IbushiginCamera/blob/master/photo1.jpg)

# Mbed CLI & GR-LYCHEE OpenCV Sample
[GR-Boards_OpenCV_sample](https://github.com/d-kato/GR-Boards_OpenCV_sample)  
[GR-LYCHEE用オフライン開発環境の手順](https://os.mbed.com/users/dkato/notebook/offline-development-lychee-langja/)  

# 接続
GR-LYCHEE (D13) - シャッターSW  
GR-LYCHEE (D1)  - AS-289R2 Thermal Printer Shield  

# 主な処理
シャッターSWが押されるとカメラで取得したグレースケール画像cv::Mat dstにコピー  
グレースケール画像サイズをcv:resizeで384xautoに変換  
cv::imwriteでxxx_gray.bmpをFlashAirに保存  
cv::Mat dstをディザリング処理で2値化  
cv::flipで反転(デモが反転印字の為)  
cv::imwriteでxxx_color2.bmpをFlashAirに保存  
FlashAirのxxx_color2.bmpファイルを読み出しながらAS-289R2 Thermal Printer Shieldにuart送信  

# 今後
FlashAirにLuaスクリプト設置してゴニョゴニュしてみます。
