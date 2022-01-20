### **K-Nearest Neighbor**

#### 算法核心

- 近朱者赤近墨者黑

通用步骤：

1）计算距离（常用欧几里得距离/马氏距离）

2）距离升序排列

3）取前k个

4）加权平均

k的选取：k太大，就会导致分类模糊；k太小，首个例的影响，就会导致波动较大。

如何选取k?

1）经验（多次实验，找出最符合的k值）

2）均方根误差法

影响knn的两个方面：k的取值，求距离的方法

```
#导入csv包
import csv 
import random            #避免测试总是那几个数据的巧合，打乱csv包
#读取csv的包
with open('Prostate_Cancer.csv','r') as file         #打开csv包,'r'文本读取，'w'文本写入
reader=csv.Dict.Reader(file)

#for row in reader:             循环每一行
	#print(row)   
datas=[row for row in reader]     #将每一行的数据存入到datas里

#分组，1/3训练集，2/3测试集
random.shuffle[datas]      #打乱顺序
n = len(datas) //3     #取整
test_set=data[0:n]
train_set=data[n:]

#KNN
#距离
def distance(d1,d2):    #欧氏距离
	res=0               #为了求和准备的
	#建立元组
	for key in ("radius","	texture	perimeter","	area","	smoothness","	compactness	symmetry","	fractal_dimension")
	res+=(float(d1[key])-float(d2[key]))**2           #将字符串转成浮点型数字，csv里的都是字符串
K=5   #取k为5
def knn(data):
	#1.距离：
	res=[
		{"result":train['diagnosis_result'],"distance":distance(data,train)}
	for train in train_set :
	]
	#2.排序--升序
	res = sorted(res,key=lambda item:item["distance"])
	
	#3.取前k个
	res2=res[0:k]
	
	
	#4.加权平均
	result={'B':0,'M':0}
	
	#总距离
	sum=0
	for r in res2:
		sum+=r['distance']     #循环求总距离
	for r in res2:
		result[r['result']]+=1-r['distance']/sum     #给result加权,距离近的权重高
	if result['B']>result['M']:
		return 'B'
	else :
		return 'M'
	
	#测试阶段
correct=0
for test in test_set:
	result=test['diagnosis_result']
	result2=knn[test]
if result == result2:           #测试结果跟实际结果相同的个数---》准确率
	correct+=1
print(correct)
prinnt(len(test_set))
print ("准确率:{:2f}%".format{100*correct/len(test_set)}z
```







均方根误差法:是观测值与真值偏差的平方和观测次数n比值的平方根。方根误差对一组测量中的特大或特小误差反映非常敏感，所以，均方根误差能够很好地反映出测量的精密度。均方根误差，当对某一量进行多次的测量时，取这一测量列真误差的均方根差(真误差平方的算术平均值再开方)，称为标准偏差，以σ表示。σ反映了测量数据偏离真实值的程度，σ越小，表示测量精度越高，因此可用σ作为评定这一测量过程精度的标准。



