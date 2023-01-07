# :desert_island: Product Recommendation Model: Deep Neural Network
### ＊ Introduction ＊
1. This model learns the `behavior patterns of different customers` in order to `predict the next product` that each customer is interested in. 

### ＊ Process ＊
1.  **[ Convert customers' browsing behaviors into vectors ]**
	1. Collect all browsing behavior data of each customer in the past year.
	2. Put the above data into the Word2Vec model in the Gensim package to get the vectors of browsing behaviors.  
		
2. **[ Construct dataset ]**
	1. `Data source:` all browsing behavior data of each customer in the previous two months.
	2. `Data preprocessing:` for each customer, it is necessary to average the vectors corresponding to all the behavior data within two months in order to represent the browsing behavior pattern. This result is also the input data of dnn model. 
	3. `Model learning/prediction target:` the latest product that customers browsed or want to browse.

3. **[ Build product recommendation model ]**
	1. `Model:` Use keras to build a deep neural networ (DNN).
	2. `Model's output:` the prediction vector for the product that the customer will browse next.
	3. `Product recommendation list:` Calculate the cosine similarity between the model's output and the vectors of all products, and sort them in descending order of similarity. The higher the similarity, the more interested the customer is in the product.
	4. If the product that is expected to be advertised is in the top K of the product recommendation list of some customers, those customers can be included in the advertising list.

-----

# :cherry_blossom: 商品推薦模型：深度神經網路
### ＊ 簡介 ＊
1. 此模型學習不同`顧客之行為模式`，以預測每個顧客`下一個感興趣的商品`。

### ＊ 流程 ＊
1. **[ 顧客瀏覽行為轉換成向量 ]**
	1. 蒐集過去一年每個顧客所有的瀏覽行為資料。
	2. 再將資料輸入Gensim套件中Word2Vec模型，即可將瀏覽或點擊某項商品的行為轉換成向量，以便建置後續模型。
	
2. **[ 建置資料集 ]**
	1. `資料來源：` 前兩個月每位顧客的所有瀏覽行為資料。
	2. `資料前處理：` 對於每一位顧客，都需將其在兩個月內的所有行為資料對應的向量相加後取平均，以代表該位顧客在兩個月內的瀏覽行為模式，此亦為模型之輸入值。
	3. `模型學習/ 預測目標：` 顧客最新(欲)瀏覽之商品。
	
3. **[ 建構商品推薦模型 ]**
	1. `模型：` 使用keras建立深度神經網路模型(deep neural network, DNN)。
	2. `模型輸出值：` 對於顧客下一個即將要瀏覽之商品的預測向量。
	3. `商品推薦清單：` 將模型輸出值與所有商品之向量計算餘弦相似度(cosine similarity)，並依照相似度由高到低進行排序，相似度越高，代表顧客對該商品越有興趣。
	4. 若預計投放廣告之商品在某些顧客的商品推薦清單前K名，則可將該顧客列入投放廣告名單中。


    
