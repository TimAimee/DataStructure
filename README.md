
# DataStructure
数据结构

## 0.时间复杂度与空间复杂度

* 时间复杂度  
    * 什么是时间复杂度
    * 如何计算时间复杂度
* 空间复杂度  
    * 什么是空间复杂度
    * 如何计算空间复杂度

## 1.数组

* 什么是数组
* 在Java中的体现
* 利与弊

## 2.链表

* 什么是链表
* 链表的分类
    * 单向链表
    * 双向链表
    * 单向循环链表
    * 双向循环链表
* 链表的操作
    * 添加（添加首部，添加尾部，插入中间）
    * 删除（删除首部，删除尾部，删除中间）
* 在Java中的体现
* 衍生其他数据结构  
  * 堆栈
  * 队列
* 实际应用场景
* 利与弊  

## (总结)数组&&链表的区别
* 内存连续性
* 时间复杂度与空间复杂
* 业务数据的处理
    * 插入
    * 查找


## 3.堆栈 

* 什么是堆栈 
* 实际应用场景
  * LRU缓存 
  * 解释计算器
  * 浏览器进退网页
* 在Java中的体现

## 4.队列 

* 什么是堆栈 
* 实际应用场景
* 在Java中的体现

## (总结)堆栈 &&队列的区别

## 5.递归

* 什么是递归
    * "递"
    * "归"
* 什么样的问题可以用递归解决
    * 大问题划小问题
    * 所有小问题解决的方式是一致的
    * 存在结束条件
* 实际应用场景
     * 走楼梯问题
     * 生兔子问题
* 利与弊

## 6.排序入门

* 基本概念  
  * 有序度
      * 向一个数组从左向右取两个数据组成所有有可能的组合，如{a,b,c}可以组成{a,b},{b,c},{c,b},若右边的数据大于左边的数据则称为有序。有序度则是有序的个数
  * 满有序度
      * 向一个数组从左向右取两个数据组成所有有可能的组合，如{a,b,c}可以组成{a,b},{b,c},{c,b},若所有的组合都是有序的则是满有序度，个数为n(n-1)/2
  * 逆序度
      * 逆序度=满有序度-有序度
  * 原地排序
      * 在排序过程中不申请多余的存储空间，只利用原来存储待排数据的存储空间进行比较和交换的数据排序
  * 稳定性
      * 一个数组存在两个相同的数值，d若在排序过程中，两个数值的位置保持不变则是稳定的，反之是不稳定的
* 排序算法的判断标准  
  * 执行效率
      * 时间复杂度(最好情况、最坏情况、平均情况、系数、常数、低阶)
      * 比较&交换的次数
  * 内存消耗
      * 空间复杂度
  * 稳定性

## 7.冒泡排序

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
        * O(n)
    * 稳定性  
        * 稳定的


## 8.插入排序

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
        * O(n)
    * 稳定性  
        * 稳定的,取无序的首下标与插入有序的末端

## 9.选择排序

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
        * O(n)
    * 稳定性  
        * 不稳定的,取最小元素与有序的末端进行交换

## (总结)冒泡&&插入&&选择算法的区别  

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


## 10.归并排序

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

## 11.快速排序

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

## (总结)归并&&快排的区别

* 相同点  
    * 解决的问题都是采用分治的思想  
    * 平均的时间复杂度都是O(nlog(n))   
* 不同点 
    * 归并步骤是至下而上的，而快排的步骤是至上而下的  
    * 归并排序是稳定的排序算法，而快速排序不是稳定的算法   

