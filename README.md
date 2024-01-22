# PySpark
## What is Spark ? 
Spark是一個針對大數據處理設計的開源分散式計算系統 ( distribute compute engine )。

Spark 採用的是 In-memory 運算技術，運算的資料存在於記憶體之中，相對於使用硬碟等儲存媒介的運算框架（ex. Hadoop）而言， Spark 具有運算速度的優勢。

Spark 在運算時，將中間產生的資料暫存在記憶體中，因此可以加快執行速度。尤其需要反覆操作的次數越多，所需讀取的資料量越大，則越能看出 Spark 的效能 ( 而 Hadoop 每次做完一次運算就必須做硬碟 I/O )

- Spark 的核心由 Scala 驅動
- 處理資料的方法有三種 : RDD, DataFrame, SparkSQL

## What is PySpark ?
用 Python 呼叫 Spark。

在 PySpark 我們把資料切割成 RDD/DataFrame 來進行處理。DataFrame 可以用 SQL 的方式去操作，表內的資料分散在各個 partition 之內，所以對列表內的欄位做操作時很自然的可以把每個操作分別派給不同 partition 去操作。

但相對的 sync 的成本就高，所以要避免用純 python 的角度去思考，比如 collect 回來成 list 再用 python 操作就是很低效的做法，每個 partition 內可能會有多筆資料，partition 內的資料處理是 Serial 的

---------------------------

- PySpark Tutorial for Beginners: https://github.com/coder2j/pyspark-tutorial
- 零經驗也可的 PySpark 教學: https://myapollo.com.tw/blog/pyspark-1/
- (PySpark版)如何完成從頭到尾完成一個資料科學專案: https://medium.com/jackys-blog/pyspark%E7%89%88-%E5%A6%82%E4%BD%95%E5%AE%8C%E6%88%90%E5%BE%9E%E9%A0%AD%E5%88%B0%E5%B0%BE%E5%AE%8C%E6%88%90%E4%B8%80%E5%80%8B%E8%B3%87%E6%96%99%E7%A7%91%E5%AD%B8%E5%B0%88%E6%A1%88-dbf0a6ec9f59
- Pyspark 筆記: https://hackmd.io/@Rance/SJHi3KluB
