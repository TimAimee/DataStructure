# 数据结构与算法之美学习笔记
![数据结构与算法之美](https://github.com/TimAimee/DataStructure/blob/master/IMG_3154.JPG)

* [基本数据结构](#基本数据结构)
    * [00.时间复杂度与空间复杂度](#时间复杂度与空间复杂度)
    * [01.数组](#数组)
    * [02.链表](#链表)
    * [03.递归](#递归)
    * [04.总结 数组&&链表的区别](#数组链表的区别)
* [常用数据结构](#常用数据结构)
    * [05.堆栈](#堆栈)
    * [06.队列](#队列)
* [排序算法](排序算法)
    * [07.基本概念](#基本概念)
    * [08.原地排序](#原地排序)
        * [08.01 冒泡排序](#冒泡排序)
        * [08.02 插入排序](#插入排序) 
        * [08.03 选择排序](#选择排序)
        * [08.04 总结 冒泡&&插入&&选择算法的区别](#冒泡插入选择的区别)
    * [09.分治思想排序](#分治思想排序)
        * [09.01 归并排序](#归并排序)
        * [09.02 快速排序](#快速排序)
        * [09.03 总结 归并&&快排的区别](#归并快排的区别)
    * [10.线性排序](#线性排序)
        * [10.01 桶排序](#桶排序)
        * [10.02 计数排序](#计数排序)
        * [10.03 基数排序](#基数排序)
        * [10.04 总结 桶&&计数&&基数的区别](#桶计数基数的区别)
    * [11.排序算法的最佳实践及优化](#排序算法的最佳实践及优化)
* [查找算法](#查找算法)
    * [12.二分法查找](#二分法查找)
    * [13.跳表查找](#跳表查找)
* [14.散列表](#散列表)
* [进群交流](#进群交流)
* [学习优惠码](#优惠码)

# <span id="基本数据结构">基本数据结构</span>

## <span id="时间复杂度与空间复杂度">00.时间复杂度与空间复杂度</span>

* 时间复杂度  
    * 什么是时间复杂度
        * 时间复杂度是一个函数,表示执行一段程序需要的时间
    * 如何计算时间复杂度
        * 从理论上来说，执行一段程序需要的时间是不能算出来的，同样一段代码，运行的时间也跟硬件的配置以及cpu的占用情况有关;
        假定一个算法中的语句执行次数为n，,n称为问题的规模，当n不断变化时，时间频度T(n)也会不断变化,
        若有某个辅助函数f(n),使得当n趋近于无穷大时，T(n)/f(n)的极限值为不等于零的常数，则称f(n)是T(n)的同数量级函数。
        记作T(n)=Ｏ(f(n)),称Ｏ(f(n)) 为算法的渐进时间复杂度，简称时间复杂度。
* 空间复杂度  
    * 什么是空间复杂度
        * 表示执行一段程序需要的内存,它也是问题规模n的函数。渐近空间复杂度也常常简称为空间复杂度
    * 如何计算空间复杂度
        * 当一个算法的空间复杂度为一个常量，即不随被处理数据量n的大小而改变时，可表示为O(1)；
        当一个算法的空间复杂度与以2为底的n的对数成正比时，可表示为O(log2n)；
        当一个算法的空间复杂度与n成线性比例关系时，可表示为0(n).

## <span id="数组">01.数组</span>

* 什么是数组
    * 数组是计算机最简单的数据结构，创建一个数组需要连续的空间，可以使用数组的下标来快速的访问对应下标的数据
* 在Java中的体现  
    * T[]{T可以是常见的String,Int,Float,...,也可以是自定义的Object}
    * ArrayList也是基于数组的集合对象
* 利与弊
    * 好处在于随机访问数据更加高效
    * 缺点在于开辟一个数组需要连续的空间

## <span id="链表">02.链表</span>

* 什么是链表
    * 链表是一种基本的数据结构，一个链表是由多个结点构成的数据结构，每个结点分为两部分(数据+指针)，指针是指向前驱结点/后驱结点，不同的指针类型可以构成不同的链表
* 链表的分类
    * 单向链表
        * 结点内部只有一个指针，且是指向前驱结点 
    * 双向链表
        * 结点内部包含两个指针，一个指向前驱结点，一个指向后驱结点  
    * 单向循环链表
        * 在单向链表上，再加上一个特性，尾结点的下个指针指向头结点
    * 双向循环链表
        * 在双向链表表上，再加上一个特性，尾结点的下个指针指向头结点
* 链表的操作
    * 添加（添加首部，添加尾部，插入中间）
    * 删除（删除首部，删除尾部，删除中间）
* 在Java中的体现
    * LinkList
    * LinkHashMap
    * 其他
* 衍生其他数据结构  
  * 堆栈
  * 队列
* 利与弊  
  * 好处在于方便数据的插入且不需要连续的内存空间
  * 弊端相对于数组，在存储相同数据的情况下，链表需要更多内存

## <span id="递归">03.递归</span>

* 什么是递归  
    * "递":向下调用方法的过程叫做递  
    * "归":向上返回数据的过程叫做归  
* 什么样的问题可以用递归解决  
    * 大问题划小问题  
    * 所有小问题解决的方式是一致的  
    * 存在结束条件  
* 实际应用场景  
    * 走楼梯问题  
        * 即一个N阶的楼梯，每次能走1～2阶，问走到N阶一共多少种走法，f(n)=f(n-1)+f(n-2),f(0)=1,f(1)=1;  
    * 生兔子问题
        * 有一对兔子，从出生后第四个月起每个月都生一对兔子，小兔子长到第四个月后每个月又生一对兔子。假如兔子都不死，计算第十个月兔子的总数？，f(n)=f(n-1)+f(n-2),f(1)=f(2)=1  
* 利与弊  
    * 好处 1：简单方便解决复杂难理解的问题  
    * 弊端 1：层级太深的话会导致堆栈溢出，解决办法是可以限制层深,也可以用hash表存储计算过的值，这样递归也可以快速一点  


## <span id="数组链表的区别">04.总结 数组&&链表的区别</span>
* 内存连续性
    * 数组要求内存连续，链表不要求数组连续 
* 内存的占用
    * 数组的结构比较简单，只要保存数据，而链表的结构较为复杂，除了要保存数据外，还需额外的空间用来保存指针
* 业务数据的处理  
    * 插入    
        * 数组插入涉及数据的移动，数组长度越大，插入所需要的时间复杂度为O(n)  
        * 链表的插入时间复杂度为O(1),只涉及到指针的变化  
    * 访问  
        * 数组可直接通过下标访问，时间复杂度为O(1)  
        * 单纯的链表，对数据的访问需要遍历指针，时间复杂度为O(n)  

# <span id="常用数据结构">常用数据结构</span>

## <span id="堆栈">05.堆栈</span>

* 什么是堆栈 
	* 堆栈是后进后出的一种数组结构，底层可以用数组或链表实现;
*  实际应用场景
    * LRU缓存  
    	* 若要实现最少最近的原则来保存缓存，则可以考虑以堆栈的方式实现  
    * 解释计算器
        * 若要计算**字符串**"5*3+3+9"的值，则可以考虑以堆栈的方式实现 
    * 浏览器进退网页
    	* 浏览器的前一步，后一步也是可以用堆栈实现的业务 
* 在Java中的体现
    * Stack类   
    	*  **push()**方法，是通过将元素追加的数组的末尾中,即将元素推入栈中
    	*  **peek()**方法，是返回数组末尾的元素,即取出栈顶元素，不执行删除
    	*  **  pop()**方法 ，是取出数组末尾的元素，然后将该元素从数组中删除,取出栈顶元素，并将该元素从栈中删除

## <span id="队列">06.队列</span>

* 什么是队列  
  * 队列是一种操作受限制的线性表, 它是一个先进先出的数据结构，它只允许在表的前端（front）进行删除操作，而在表的后端（rear）进行插入操作。进行插入操作的端称为队尾，进行删除操作的端称为队头;
* 实际应用场景  
  * 线程池 
* 在Java中的体现   
  * Queue类
    * add        增加一个元索
    * remove   移除并返回队列头部的元素
    * element  返回队列头部的元素
    * offer       添加一个元素并返回true
    * poll         移除并返问队列头部的元素
    * peek       返回队列头部的元素 
    * put         添加一个元素 
    * take        移除并返回队列头部的元素   

# <span id="排序算法">排序算法</span>


## <span id="基本概念">07.基本概念</span>

* 基本概念  
  * 有序度
      * 向一个数组从左向右取两个数据组成所有有可能的组合，如{a,b,c}可以组成{a,b},{b,c},{c,b},若右边的数据大于左边的数据则称为有序。有序度则是有序的个数
  * 满有序度
      * 向一个数组从左向右取两个数据组成所有有可能的组合，如{a,b,c}可以组成{a,b},{b,c},{c,b},若所有的组合都是有序的则是满有序度，个数为n(n-1)/2
  * 逆序度
      * 逆序度=满有序度-有序度
  * 原地排序
      * 在排序过程中不申请多余的存储空间，只利用原来存储待排数据的存储空间进行比较和交换的数据排序，记为O(1)
  * 稳定性
      * 一个数组存在两个相同的数值，d若在排序过程中，两个数值的位置保持不变则是稳定的，反之是不稳定的
* 排序算法的判断标准  
  * 执行效率
      * 时间复杂度(最好情况、最坏情况、平均情况、系数、常数、低阶)
      * 比较&交换的次数
  * 内存消耗
      * 空间复杂度
  * 稳定性

## <span id="原地排序">08.原地排序</span>

### <span id="冒泡排序">08.01 冒泡排序</span>

* 基本原理  
    * 依次将每相邻的两个数据进行比较，若大数在前，则将两者交换位置，
    * 每次交换到最后一个数时，保证了最大的数在末端，  
    * 若将数据分布为有序和无序两部分，则每循环比较一次，末端数据总是有序，其他数据为无序
    * 有序数据长度在增长，无序数据长度在减少，即每次循环比较的次数都在减少
* 示例流程
    * 原始数据为：A={3,1,5,2,6,4}，
    * 步骤一,开始第一次循环交换，第一次{3,1}交换
        * {1,3,5,2,6,4}
    * 步骤二,第二次{3,5}不交换
        * {1,3,5,2,6,4}  
    * 步骤三,第三次{5,2}交换
        * {1,3,2,5,6,4}
    * 步骤四,第四次{5,6}不交换
        * {1,3,2,5,6,4}  
    * 步骤五,第五次{6,4}交换，第一次循环结束,保证最大数6在后面
        * {1,3,2,5,4,6}
    * 步骤六,开始第二次循环交换{1,3,2,5,4} 重复以上步骤
        * {1,2,3,4,5,6}
    * 结束
* 动画展示
  
  ![](https://thumbnail0.baidupcs.com/thumbnail/d4c88b8cc620af6af67c33910899fcf7?fid=1965631489-250528-458105244136871&time=1540569600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-FyS2bT%2FdkpaL9G2OxnE3a78d87c%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6934845282502043385&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video)
  
* 实现代码
 ```java
 public static void bubbleSort(int[] arr) {
    int temp = 0;
    // i是每次需要排序的长度
    for (int i = arr.length - 1; i > 0; --i) { 
        // j是从第一个元素到第i个元素
        for (int j = 0; j < i; ++j) { 
            if (arr[j] > arr[j + 1]) {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
```
* 性能分析 
    * 执行效率
        * 最差情况O(n^2) 
        * 最好情况O(n)
        * 平均情况O(n^2)
    * 内存消耗
        * O(1)
    * 稳定性  
        * 稳定的


### <span id="插入排序">08.02 插入排序</span>

* 基本原理
    * 若将数据分布为有序和无序两部分，首端数据总是有序，其他数据为无序，开始的有序数据长度为0，无序数据长度为数组的长度 
    * 依次向无序数据中取最近的一个数，经过与首端的数据依次比较，然后插入到有序数组中，实现的方式将插入的位置后的数据都依次后移一位  
    * 有序数据长度在增长，无序数据长度在减少，即每次可能要循环移动的数据长度在增长
* 示例流程
    * 原始数据为：A={3,1,5,2,6,4}，有序{},无序{3,1,5,2,6,4}
    * 步骤一,第一次选择3，放入有序末端,有序{3},无序{1,5,2,6,4}
        * {3,1,5,2,6,4}
    * 步骤二,第二次选择1,1小于3,将{3}后移,替换1,最终有序{1,3},无序{5,2,6,4} 
        * {1,3,5,2,6,4}  
    * 步骤三,第三次选择5,5大于3,不用移动,最终有序{1,3,5},无序{2,6,4} 
        * {1,3,5,2,6,4}
    * 步骤四,第四次选择2,将{3,5}后移,替换2,最终有序{1,2,3,5},无序{6,4} 
        * {1,2,3,5,6,4}  
    * 步骤五,第五次选择6,6大于5,不用移动,最终有序{1,2,3,5,6},无序{4}
        * {1,2,3,5,6,4}
    * 步骤六,第六次选择4,将{5,6}后移,替换4,最终{1,2,3,4,5,6},无序{} 
        * {1,2,3,4,5,6}
    * 结束
    
* 动画展示  

![](https://thumbnail0.baidupcs.com/thumbnail/6e67d1c722106442b422ee53e98575b3?fid=1965631489-250528-49163951976690&time=1540569600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-Q5Yehkq0nXe7FGY6FtIYFj70O0I%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6934729807979717223&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video)  

* 实现代码
 ```java
 public static void insertSort(int[] numbers){
        for (int i = 1; i < numbers.length; i++) {
            int currentNumber = numbers[i];
            int j = i - 1;
            while (j >= 0 && numbers[j] > currentNumber) {
                numbers[j + 1] = numbers[j];
                j--;
            }
            numbers[j + 1] = currentNumber;
        }
    }
```
* 性能分析 
    * 执行效率
        * 最差情况O(n^2) 
        * 最好情况O(n)
        * 平均情况O(n^2)
    * 内存消耗
        * O(1)
    * 稳定性  
        * 稳定的,取无序的首下标与插入有序的末端

### <span id="选择排序">08.03 选择排序</span>

* 基本原理
    * 若将数据分布为有序和无序两部分，首端数据总是有序，其他数据为无序，开始的有序数据长度为0，无序数据长度为数组的长度 
    * 依次向无序数据中取最小的一个数，放置到首端末尾，具体的实现方式是与首端末尾+1的数据进行交换
    * 有序数据长度在增长，无序数据长度在减少
* 示例流程
    * 原始数据为：A={3,1,5,2,6,4}，有序{},无序{3,1,5,2,6,4}
    * 步骤一,第一次选择1,放入有序末端,交换[3,1]位置,有序{1},无序{3,5,2,6,4}
        * {1,3,5,2,6,4}
    * 步骤二,第二次选择2,放入有序末端,交换[3,2]位置,,最终有序{1,2},无序{5,3,6,4} 
        * {1,2,5,3,6,4}  
    * 步骤三,第三次选择3,放入有序末端,交换[5,3]位置,最终有序{1,2,3},无序{5,6,4} 
        * {1,2,3,5,6,4}
    * 步骤四,第四次选择4,放入有序末端,交换[5,4]位置,最终有序{1,2,3,4},无序{6,5} 
        * {1,2,3,4,6,5}  
    * 步骤五,第五次选择5,放入有序末端,交换[6,5]位置,最终有序{1,2,3,4,5},无序{6} 
        * {1,2,3,4,5,6}
    * 步骤六,第六次选择6,放入有序末端,交换[6,6]位置,最终有序{1,2,3,4,5,6},无序{} 
        * {1,2,3,4,5,6}
    * 结束
* 动画展示  

![](https://thumbnail0.baidupcs.com/thumbnail/f20b8898585b3ca03843d93ce2c35a68?fid=1965631489-250528-352779506478042&time=1540569600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-uwMscw8i3s2C7GEhYQHvGEv2BdM%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6934812512989256390&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video)

* 实现代码
```Java
 public static void selectSort(int[] array){
    int aLength=array.length;
    for(int i=0;i<aLength;i++){
    	  //记录最小数据的位置
        int min=i;
        for(int j=i+1;j<aLength;j++){
            if(array[j]<array[min]){  
                min=j;
            }
        }
        //通过交换实现将最小数据放入有序末端，  
        int temp=array[i];
        array[i]=array[min];
        array[min]=temp;
    }
}
```
* 性能分析 
    * 执行效率
        * 最差情况O(n^2) 
        * 最好情况O(n^2)
        * 平均情况O(n^2)
    * 内存消耗
        * O(1)
    * 稳定性  
        * 不稳定的,取最小元素与有序的末端进行交换

### <span id="冒泡插入选择的区别">08.04 总结 冒泡&&插入&&选择算法的区别</span>

* 相同点  
    * 最差以及平均的时间复杂度都是O(n^2)  
    * 属于原地排序,空间复杂度都是O(1)  
    * 排序基本的思想是数据的比较，移动，替换  
* 示例流程  
    * 冒泡以及插入算法最好时间复杂度是O(n),  选择算法最好时间复杂度是O(n^2)
    * 冒泡以及插入算法是稳定的，选择算法是不稳定的  
    * 冒泡算法偏重数据的比较&&替换  
    * 插入算法偏重数据的比较&&移动  
    * 选择算法偏重的是数据的比较&&替换     

## <span id="分治思想排序">09.分治思想排序</span>

### <span id="归并排序">09.01 归并排序</span>

* 基本原理
    * 整体思想  
        * A.将一段数组递归的均分为相等的左右两部分，直到分到最后一个元素
        * B.然后将每一次均分的左右部分从下至上重新合并  
        * C.经过不断的合并，最终实现有序
    * 均分
        * 若A的长度为r,则取坐标为[0，r]，  
        * 1.采用分治的思想，均分为两部分[0,p],[p+1,r],p是[0,r]的中位数    
        * 2.同理又将[0,p]均分为[0,k]&[k+1,p];[p+1,r]均分为[p+1,q]&[q+1,r]，k、q均是对应数组的中位数
        * 3.一直均分到[i,j],当i<=j,
    * 合并
        * A[0,p]，B[p+1,r]，以i为A数组计数坐标，以j为B数组计数坐标，新建一个temp数组用到保存后数据   
        * 1.分别取A[i],A[j],然后二者取小，且小者的相应计数坐标加1
        * 2.重复以上操作，直到其中一个数组的数据取完，合并剩余一组到temp数组末端
        * 3.将temp中的元素全部拷贝到原数组中
* 示例流程
    * 原始数据为：A={3,1,5,2,7,6,4,8}，
    * 步骤一,第一次分治
        * {3,1,5,2}、{7,6,4,8}、
    * 步骤二,第二次分治
        * {3,1}、{5,2}、{7,6}、{4,8}  
    * 步骤三,第三次分治
        * {3},{1},{5},{2},{7},{6},{4},{8}    
    * 步骤四,第一次合并
        * {1,3}、{2,5}、{6,7}、{4,8}   
    * 步骤五,第二次合并
        * {1,2,3,5}、{4,6,7,8}、 
    * 步骤六,第三次合并
        * {1,2,3,4,5,6,7,8} 
    * 结束
* 动画展示  

![](https://thumbnail0.baidupcs.com/thumbnail/a29c0dd0186d1f8cef3c5ebdedf3e5a3?fid=1965631489-250528-849432608703125&time=1540569600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-CInmZuERDfNXBNlNTWV5EN%2B8ffw%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6934864169144824899&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video)

* 实现代码
```Java
    public static void sort(int []arr){
        //在排序前，先建好一个长度等于原数组长度的临时数组，避免递归中频繁开辟空间
        int []temp = new int[arr.length];
        sort(arr,0,arr.length-1,temp);
    }
   private static void sort(int[] arr,int left,int right,int []temp){
        if(left<right){
            int mid = (left+right)/2
            //左边归并排序，使得左子序列有序;
            sort(arr,left,mid,temp);
            //右边归并排序，使得右子序列有序
            sort(arr,mid+1,right,temp);
            //将两个有序子数组合并操作
            merge(arr,left,mid,right,temp);
        }
    }
    private static void merge(int[] arr,int left,int mid,int right,int[] temp){
        //左序列指针
        int i = left;
        //右序列指针
        int j = mid+1;
        //临时数组指针
        int t = 0;
        while (i<=mid && j<=right){
            if(arr[i]<=arr[j]){
                temp[t++] = arr[i++];
            }else {
                temp[t++] = arr[j++];
            }
        }
        while(i<=mid){
            //将左边剩余元素填充进temp中
            temp[t++] = arr[i++];
        }
        while(j<=right){
            //将右序列剩余元素填充进temp中
            temp[t++] = arr[j++];
        }
        t = 0;
        //将temp中的元素全部拷贝到原数组中
        while(left <= right){
            arr[left++] = temp[t++];
        }
    }
```
* 性能分析   
    * 执行效率
        * 最差情况O(n(logn)) 
        * 最好情况O(n(logn))
        * 平均情况O(n(logn))
    * 内存消耗
        * O(n)
        * 为什么不是n(logn)? 因为同一时间内只能执行一次，并释放临时内存       
    * 稳定性  
        * 稳定的

### <span id="快速排序">09.02 快速排序</span>

* 基本原理  
    * 整体思想  
        * A.将一段数据以基准数据为比较，不断分为两部分，左边小于基准数据，右边大于或等于基准数据，  
        * B.将左边部分重复A操作，将右边部分重复A操作，  
        * C.经过不断的划分排序，最终实现有序
    * 划分排序  
        * 若A的长度为r,则取坐标为[0，r]，  
        * 1.采用分治的思想，    
        * 2.以尾部数据A[r]为基准数据，  
        * 3.初使化i=0,j=0;以i坐标为替换坐标，j坐标为遍历数据坐标，每遍历一次，j=j+1，  
        * 4.若A[j]小于A[r]，与A[i]数据替换，每替换一次i=i+1，  
        * 5.当j遍历到r-1时，交换A[i]与A[r]，  
        * 6.最终实现坐标i左边的数据都是小于A[r]的，反之右边都是大于或等于A[r]的   
* 示例流程  
    * 原始数据为：A={3,1,5,2,6,4}，以i坐标为替换坐标，j坐标为遍历数据坐标，初使化数据i=j=0,r=5;
    * 步骤一，比较A[j]以及A[r],即比较3和4,符合条件，将i,j数据替换，即A[0]与A[0]替换，  将i坐标，j坐标同时加1，即i=j=1;
        * {3,1,5,2,6,4}
    * 步骤二，比较A[j]以及A[r],即比较1和4,符合条件，将i,j数据替换，即A[1]与A[1]替换，将i坐标，j坐标同时加1，即i=j=2;
        * {3,1,5,2,6,4}  
    * 步骤三，比较A[j]以及A[r],即比较5和4,不符合条件，将j坐标加1，i坐标不变，即i=2，j=3;
        * {3,1,5,2,6,4}    
    * 步骤四，比较A[j]以及A[r],即比较2和4,符合条件，将i,j数据替换，即A[2]与A[3]替换，将i坐标，j坐标同时加1，即i=3，j=4;
        * {3,1,2,5,6,4} 
    * 步骤五，比较A[j]以及A[r],即比较6和4,不符合条件，将j坐标加1，i坐标不变，即i=3，j=5;
        * {3,1,2,5,6,4} 
    * 步骤六,比较结束,将i,r数据替换, 实现第一次的划分排序
        * {3,1,2,4,6,5} 
    * 步骤七,将4左边的数据重复以上步骤, 实现第二次的划分排序
        * {3,1,2,4,6,5} 
        * {1,3,2,4,6,5} 
        * {1,2,3,4,6,5} 
    * 步骤八,将4右边的数据重复以上步骤, 实现第三次的划分排序
        * {1,2,3,4,5,6} 
    * 结束
 * 动画展示  
 
![](https://thumbnail0.baidupcs.com/thumbnail/d4e5d0a778dba725091d8317e6bac939?fid=1965631489-250528-63936477290856&time=1540569600&rt=sh&sign=FDTAER-DCb740ccc5511e5e8fedcff06b081203-C7Ni7BKFdZC6Dif%2B3OG%2BTXo1qcw%3D&expires=8h&chkv=0&chkbd=0&chkpc=&dp-logid=6934768471050065794&dp-callid=0&size=c710_u400&quality=100&vuk=-&ft=video)    

* 实现代码    
```Java
    //快速排序  
    public static void quickSort(int[] arr){   
      qsort(arr, 0, arr.length-1);  
    }  
    //递归   
    private static void qsort(int[] arr, int i, int r){  
        if (low < high){  
            //将数组分为两部分  
            int pivot=partition(arr, i, r);         
            //递归排序左子数组  
            qsort(arr, i, pivot-1);                   
            //递归排序右子数组  
            qsort(arr, pivot+1, j);                  
        }  
    }  
    //划分  
    private static int partition(int[] arr, int i, int i){  
        int pivot = arr[arr.length-1];    
        int i=0;  
        if(int j=0;j<arr.length-2;j++){  
            if(arr[j]<pivot){  
                swap(arr[i],arr[j]);
                i++
            }  
        }  
        //扫描完成，基准数据到位  
        swap(arr[i],arr[arr.length-1])  
        //返回的是基准数据的位置  
        return i;  
    }
```
 
* 性能分析  
    * 执行效率
        * 最差情况O(n^2) 
        * 最好情况O(n(logn))
        * 平均情况O(n(logn))
    * 内存消耗
        * O(n)
    * 稳定性  
        * 不稳定
        * 因为排序结束后，基准数据与A[i]进行了替换

### <span id="归并快排的区别">09.03 总结 归并&&快排的区别</span>

* 相同点  
    * 解决的问题都是采用分治的思想  
    * 平均的时间复杂度都是O(nlog(n))   
* 不同点 
    * 归并步骤是至下而上的，而快排的步骤是至上而下的  
    * 归并排序是稳定的排序算法，而快速排序不是稳定的算法   

   
## <span id="线性排序">10.线性排序</span>

### <span id="桶排序">10.01 桶排序</span>

* 基本原理  
    * 整体思想  
* 示例流程  
* 动画展示  
* 实现代码    
* 性能分析  
    * 执行效率
    * 内存消耗
    * 稳定性

    
### <span id="计数排序">10.02 计数排序</span>

* 基本原理  
    * 整体思想  
* 示例流程  
* 动画展示  
* 实现代码    
* 性能分析  
    * 执行效率
    * 内存消耗
    * 稳定性  

### <span id="基数排序">10.03 基数排序</span>

* 基本原理  
    * 整体思想  
* 示例流程  
* 动画展示  
* 实现代码    
* 性能分析  
    * 执行效率
    * 内存消耗
    * 稳定性

### <span id="桶计数基数的区别">10.04 总结 桶&&计数&&基数的区别</span>
* ++  
* ++

## <span id="排序算法的最佳实践及优化">11.排序算法的最佳实践及优化</span>
* ++
* ++

# <span id="查找算法">查找算法</span>

## <span id="二分法查找">12.二分法查找</span>

* 基本原理  
    * 整体思想  
* 示例流程  
* 动画展示  
* 实现代码    
* 执行效率

## <span id="跳表查找">13.跳表查找</span>

* 基本原理  
    * 整体思想  
* 示例流程  
* 动画展示  
* 实现代码    
* 执行效率
 
# <span id="散列表">14.散列表</span>

* 基本原理  
    * 整体思想  
* 示例流程  
* 动画展示  
* 实现代码    
* 执行效率 

## 参考
[BiliBili 排序演示](https://space.bilibili.com/39049488/#/channel/detail?cid=30972)  

# <span id="进群交流">进群交流</span>  
![进群交流](https://github.com/TimAimee/DataStructure/blob/master/1541471641338.png)  

# <span id="优惠码">学习优惠码</span>
![邀请码](https://github.com/TimAimee/DataStructure/blob/master/IMG_3155.JPG)
