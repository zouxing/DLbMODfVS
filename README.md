# Deep Learning based Moving Object Detection for Video Surveillance



## 構想

移動物偵測在計算機視覺是一門十分基礎且重要的研究項目，因為它屬於計算機視覺的前期應用，偵測到移動物之後，後期可以把這項技術應用到許多層面。

目前的輸出方式都是一個二值分割圖(如圖一)，只使用白點作為前景物並沒有辦法辨識出前景物的類別以及不同個體。我們希望能夠建構出一個新的模型，除了辨識移動物的位置，還要能檢測出移動物的類別。
	
    	
        	
               
<p align="center">
<img src="https://raw.githubusercontent.com/zouxing/DLbMODfVS/master/markdown/%E6%A7%8B%E6%83%B32.jpg" width="637" height="358"  >
</p>

<p align="center">
圖一
</p>


## 項目應用類型與範圍


我們的項目可以應用在任何需要移動物偵測的項目上。如圖二所示，以視訊監控來說，能偵測出監視器畫面中移動的目標物並且濾除掉因動態背景而產生的誤偵測。同樣地，偵測出畫面移動物的位置與類別，能夠進一步的做移動物的位置追蹤。

移動物偵測是計算機視覺中基底、上游的項目，任何項目需要移動物偵測都能使用到我們的產品。
 
  
  	

<p align="center">
<img width="551" height="150" src="https://raw.githubusercontent.com/zouxing/DLbMODfVS/master/markdown/%E6%87%89%E7%94%A81.jpg" >
</p>

<p align="center">
圖二
</p>

## 實機運作方式


* 輸入以下指令以執行訓練
	* 請注意，使用GTX 1080ti 需要花費約8~9小時，如果您只需要重現我們的結果，可以直接跳至下一個步驟使用我們已經訓練好的權重進行測試。	

  ```
  python2 tools/train_net.py \
  --cfg experiments/fast_rcnn_R-50-FPN_1x.yaml \
  OUTPUT_DIR experiments/result
  ```

 		
* 輸入以下指令以執行測試
  ```
  python2 tools/test_net.py \
  --cfg experiments/fast_rcnn_R-50-FPN_1x.yaml \
  TEST.WEIGHTS experiments/result/train/voc_2007_trainval/generalized_rcnn/model_final.pkl
  ```
* 輸入以下指令以將測試結果視覺化
  ```
  python2 tools/visualize_results.py \
  --dataset voc_2007_test \
  --detections experiments/detections.pkl \
  --output-dir experiments \
  ```

## 成果展現

請注意，以下影片只包含結果展現，如果您需要包括產品應用、產品特色之類更詳細的資訊請點擊報名表上給予的影片連結，謝謝！

<p align="center">
<a href="http://www.youtube.com/watch?feature=player_embedded&v=6-TI9M423KU" target="_blank"><img src="http://img.youtube.com/vi/6-TI9M423KU/0.jpg"  alt="D" width="500" height="281" border="10" /></a>
</p>
