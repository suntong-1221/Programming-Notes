
<a name="XnE7k"></a>
## 一、插入排序


![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1655439478861-43407048-d7f2-458a-aa97-54f2266c3f8a.png#clientId=u193b7f5a-2f3e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=1402&id=u8c9ea28c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=2804&originWidth=1910&originalType=binary&ratio=1&rotation=0&showTitle=false&size=202765&status=done&style=none&taskId=ue2a7848e-4468-437b-bb80-fd89bfc1086&title=&width=955)
<a name="sswYr"></a>
### 如何用插入排序排一个乱序的数组？
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1655439938790-70c45005-cc13-4146-bfc8-decc3e1bc319.png#clientId=ufec047c6-f2cf-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=694&id=uc8f17ba9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1388&originWidth=1168&originalType=binary&ratio=1&rotation=0&showTitle=false&size=221824&status=done&style=none&taskId=u000b8299-936b-42e1-897d-dbafa18a80d&title=&width=584)
<a name="ueE1m"></a>
### 代码：
```c
void InsertSort(int* a, int n)
{
	for (int i = 0; i < n - 1; ++i)
	{
		// [0,end]有序，把end+1位置的值插入，保持有序
		int end = i;
		int tmp = a[end + 1];
		while (end >= 0)
		{
			if (tmp < a[end])
			{
				a[end + 1] = a[end];
				--end;
			}
			else
			{
				break;
			}
		}
		a[end + 1] = tmp;
	}
}
```
<a name="E99PE"></a>
## 二、希尔排序

<a name="TlBUN"></a>
### ![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1655441577097-5c22b62b-3c38-4703-860b-1d5b6d4e479a.png#clientId=ufec047c6-f2cf-4&crop=0&crop=0&crop=1&crop=0.8674&from=paste&height=891&id=ued2a655d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1780&originWidth=1427&originalType=binary&ratio=1&rotation=0&showTitle=false&size=249312&status=done&style=none&taskId=ufd256feb-1d33-4dff-aded-8f04ebc9e78&title=&width=714)
<a name="Blbal"></a>
### 问题：如和控制红、蓝、褐三组依次插入排序？
<a name="nBqh1"></a>
### 方法1代码：
```c
void ShellSort(int *a, int n)
{
    int gap=3;
    for(int i=0;i<gap;i++)
    {
        for (int i = 0; i < n - gap; i+=gap)
        {
            // [0,end]有序，把end+1位置的值插入，保持有序
            int end = i;
            int tmp = a[end + gap];
            while (end >= 0)
            {
                if (tmp < a[end])
                {
                    a[end + gap] = a[end];
                    end-=gap;
                }
                else
                {
                    break;
                }
            }
            a[end + gap] = tmp;
        }
    }
}
```
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1655442548277-dd17807f-b92c-4b5a-9115-a60b39358e4b.png#clientId=ufec047c6-f2cf-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=829&id=u931687e9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1658&originWidth=1567&originalType=binary&ratio=1&rotation=0&showTitle=false&size=256140&status=done&style=none&taskId=uf5819589-c5d2-42b4-aec7-1bedafef77a&title=&width=783.5)
<a name="L0IHl"></a>
### 方法2代码：
```c
void ShellSort(int *a, int n)
{
    int gap=n;
    while(gap>1)
    {
        gap=gap/3+1;
        for (int i = 0; i < n - gap; i++)
        {
            // [0,end]有序，把end+1位置的值插入，保持有序
            int end = i;
            int tmp = a[end + gap];
            while (end >= 0)
            {
                if (tmp < a[end])
                {
                    a[end + gap] = a[end];
                    end-=gap;
                }
                else
                {
                    break;
                }
            }
            a[end + gap] = tmp;
        }   
    }
}
```
<a name="cQWdg"></a>
## 三、冒泡排序
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1655186851282-20576097-9f21-4a30-b0ce-6dc53076b4c5.png#clientId=uf7b4fa47-4375-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=740&id=u13e22ffe&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1479&originWidth=1578&originalType=binary&ratio=1&rotation=0&showTitle=false&size=102147&status=done&style=none&taskId=u326c1aef-f817-4886-aac3-afc29b99d9d&title=&width=789)

<a name="lm2L5"></a>
## 四、快速排序

![](https://cdn.nlark.com/yuque/0/2022/jpeg/29247941/1656209766329-53fee13d-6691-4d72-a060-e3e8486f96b2.jpeg)


挖坑<br />前后指针<br />快排优化问题

- 三数取中
- 小区间优化

全局变量的声明和定义<br />快排非递归

- 栈 层序
- 队列  

这个地方

<a name="La6D1"></a>
### 1、Hoare
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1655187096359-9c4e53f2-d69d-46b0-9eb3-79e327bfefa2.png#clientId=uf7b4fa47-4375-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=2981&id=uc52f5631&margin=%5Bobject%20Object%5D&name=image.png&originHeight=5961&originWidth=1854&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1144836&status=done&style=none&taskId=u3f4b45a9-ff71-48e6-9e73-8d63188cd5f&title=&width=927)
<a name="Om4Sd"></a>
### 为什么左key 右先走？ 相遇情况
结论：因为要保证相遇的位置比key小，或者就是key的位置

- 右遇到左
- 左遇到右

<a name="LOnMc"></a>
### 霍尔代码：
```c
int PartSort1(int *a, int begin, int end)
{
    int left=begin, right=end;
    int keyi=begin;
    while(left<right)
    {
        while(left<right&&a[right]>=a[keyi])
        {
            right--;
        }

        while (left<right&&a[left]<=a[keyi])
        {
            left++;
        }
        Swap(&a[left],&a[right]);
    }
    Swap(&a[keyi],&a[left]);
    return left;
}
```
<a name="X3bjT"></a>
### 2、挖坑
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1656719897209-d3e123e9-16c0-4487-8619-f3885ff6b52e.png#clientId=u1f30c0e8-2345-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=3774&id=ud80c0f04&margin=%5Bobject%20Object%5D&name=image.png&originHeight=7547&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=593922&status=done&style=none&taskId=ud00f8a07-2f49-438a-a5d0-5cc0d23241f&title=&width=960)
<a name="B4HYO"></a>
### 挖坑代码：
```c
int PartSort2(int* a, int begin, int end)
{
    int left=begin, right=end;
    int hole=begin;
    int temp=a[begin];
    while(left<right)
    {
        while (left<right&&a[right]>=temp)
        {
            right--;
        }
        a[hole]=a[right];
        hole=right;
        while(left<right&&a[left]<=temp)
        {
            left++;
        }
        a[hole]=a[left];
        left=hole;
    }
    a[hole]=temp;
    return hole;
}
```
<a name="IRtPN"></a>
### 3、前后指针

![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1656719940732-38e33dd7-7773-4c23-9953-23963068fb03.png#clientId=u1f30c0e8-2345-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=2095&id=ud1ac6514&margin=%5Bobject%20Object%5D&name=image.png&originHeight=4189&originWidth=1858&originalType=binary&ratio=1&rotation=0&showTitle=false&size=849715&status=done&style=none&taskId=u1cf63f32-f3a1-4079-8d3a-12d8fa9c5cd&title=&width=929)
<a name="oQlkX"></a>
### 前后指针代码：
```c
int PartSort3(int *a, int begin ,int end)
{
    int keyi=begin;
    int prev=begin;
    int cur=prev+1;
    while (cur<=end)
    {
        if(a[cur]<a[keyi]&& ++prev !=cur)
            Swap(&a[prev],&a[cur]);
        cur++;
    }
    Swap(&a[prev],&a[keyi]);
    keyi=prev;
    return keyi;
}
```
<a name="w1s8D"></a>
### 递归小区间优化

```c
void QuickSort(int *a, int begin, int end)
{
    if(begin>=end)
    {
        return;
    }
    if(end-begin<10)
    {
        InsertSort(a+begin, end-begin+1);
    }
    else
    {
        int keyi=PartSort2(a, begin,end);
        QuickSort(a, 0, keyi-1);
        QuickSort(a, keyi+1, end);
    }
    

}
```
<a name="Yv9bc"></a>
### 快排非递归写法

思路：入区间，pop区间，入子区间<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1656945292003-9c879d79-507c-40d5-8270-35195920743e.png#clientId=u4ddaef66-dd81-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=1810&id=u05fff46a&margin=%5Bobject%20Object%5D&name=image.png&originHeight=3619&originWidth=1790&originalType=binary&ratio=1&rotation=0&showTitle=false&size=244453&status=done&style=none&taskId=u8623a0d3-1ace-46e1-b3a2-6fb5a56efbf&title=&width=895)<br />队列相当于层序遍历<br />栈相当于前序遍历
```c
void QuickSortNonR(int *a, int begin, int end)
{
    Stack st;
    StackInit(&st);
    StackPush(&st, end);
    StackPush(&st, begin);
    while (!StackEmpty(&st))
    {
        int left=StackTop(&st);
        StackPop(&st);
        int right=StackTop(&st);
        StackPop(&st);
        int keyi=PartSort3(a, left, right);
        
        if(keyi+1<right)
        {
            StackPush(&st, right);
            StackPush(&st, keyi+1);
        }
        if(left<keyi-1)
        {
            StackPush(&st, keyi-1);
            StackPush(&st, left);
        }


    }
    StackDestroy(&st);
}
```
<a name="E6WqG"></a>
### 
<a name="LG11D"></a>
### 快排时间复杂度
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1656338343879-d73bb3a2-d73a-40f6-821f-f601aa5671f3.png#clientId=u9f8d5d90-8bad-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=485&id=u0a4abf7e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=969&originWidth=1526&originalType=binary&ratio=1&rotation=0&showTitle=false&size=53087&status=done&style=none&taskId=u4f131b89-e610-452e-8066-71e0275cc12&title=&width=763)

N个数如果每次都可以接近二分的话，高度为logN层<br />每一层遍历N个数，确定一个数的正确位置，那么整体的时间复杂度（最好情况）：O(NlogN)<br />最坏情况？<br />![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1656339129940-9e77de6e-ac75-4b6c-8337-abef8ef17519.png#clientId=u9f8d5d90-8bad-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=638&id=udfd83382&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1275&originWidth=1567&originalType=binary&ratio=1&rotation=0&showTitle=false&size=52314&status=done&style=none&taskId=ue75083e9-e4c6-4b83-8ac1-296f22e3e4d&title=&width=783.5)


如果待排序的数组本身为升序，每次取的key值为最左边的元素<br />![](https://cdn.nlark.com/yuque/__latex/03267f2efd3add6250afeed6b57ca9c3.svg#card=math&code=1%2B2%2B3%2B....%2BN-3%2BN-2-N-1%2BN%3D%28N%2B1%29%2AN%2F2%20%5Capprox%20N%5E2&id=bfmde)

时间复杂度上升到O(N^2)的级别







<a name="Y57hl"></a>
## 五、选择排序
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1655270730767-dbf292c0-5a3c-49c6-b3db-def31c149432.png#clientId=ufc09babb-f93e-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=964&id=u563f784c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1927&originWidth=1869&originalType=binary&ratio=1&rotation=0&showTitle=false&size=376144&status=done&style=none&taskId=u4a6b648c-9683-477a-920d-b2e52ce38b4&title=&width=934.5)

自己写的：
```c
void SelectSort(int* a, int n)
{
    int left=0,right=n-1;
    while(left<right)
    {
        int mini=left;
        int maxi=right;
        for(int i=left;i<=right;i++)
        {
            if(a[i]>a[maxi])
            {
                maxi=i;
            }
            if(a[i]<a[mini])
            {
                mini=i;
            }
        }
        Swap(&a[right], &a[maxi]);
        if(right==mini)
        {
            mini=maxi;
        }
        Swap(&a[left], &a[mini]);
        left++;
        right--;
    }
}
```
<a name="HbvMZ"></a>
### 标准代码：
```c
void SelectSort(int* a, int n)
{
	assert(a);
	int begin = 0, end = n - 1;
	while (begin < end)
	{
		int mini = begin, maxi = begin;
		for (int i = begin + 1; i <= end; ++i)
		{
			if (a[i] < a[mini])
				mini = i;

			if (a[i] > a[maxi])
				maxi = i;
		}
		Swap(&a[begin], &a[mini]);

		// 如果begin和maxi重叠，那么要修正一下maxi的位置
		if (begin == maxi)
		{
			maxi = mini;
		}

		Swap(&a[end], &a[maxi]);
		++begin;
		--end;
	}
}
```
<a name="lDbuq"></a>
## 六、堆排序
[堆-堆排序](https://www.yuque.com/atong-2ix2b/bau4ad/yrkgv5?view=doc_embed)
<a name="Gqdmv"></a>
## 七、归并排序
> 思路：左区间有序，右区间有序，合并有序

<a name="dlUiZ"></a>
### 1、递归
递归过程如下图所示，当区间大于1时，平均成左右区间，当递归到只有一个数的时候，一个数就是有序的

![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1657085642097-e2a66e7d-663f-48f0-b20c-07a54b674aaa.png#clientId=u9897932b-03f1-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=955&id=udaa9b16e&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1909&originWidth=1708&originalType=binary&ratio=1&rotation=0&showTitle=false&size=141509&status=done&style=none&taskId=ucf05e359-1e14-4bd6-b604-1290926a7e9&title=&width=854)
<a name="aLvws"></a>
### 递归代码：
```c
void _MergeSort(int* a, int begin, int end, int* tmp)
{
    if(begin>=end)
        return;
    int mid=(begin+end)/2;

    _MergeSort(a,begin, mid,tmp);
    _MergeSort(a,mid+1,end,tmp);

    //归并
    int begin1=begin, end1=mid;
    int begin2=mid+1, end2=end;
    int i=begin1;
    while (begin1<=end1&&begin2<=end2)
    {
        if(a[begin1]<a[begin2])
        {
            tmp[i++]=a[begin1++];
        }
        else
        {
            tmp[i++]=a[begin2++];
        }
    }
    while (begin1<=end1)
    {
        tmp[i++]=a[begin1++];
    }
    while(begin2<=end2)
    {
        tmp[i++]=a[begin2++];
    }
    memcpy(a+begin, tmp+begin, sizeof(int)*(end-begin+1));
}
void MergeSort(int*a, int n)
{
    int* tmp=(int*)malloc(sizeof(int)*n);
    assert(tmp);
    _MergeSort(a,0,n-1,tmp);

    free(tmp);
}
```
<a name="h8LQm"></a>
### 2、非递归
![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1657512358357-a037d6e7-849a-4e1c-8ef6-c65fcd208cea.png#clientId=ud1d7516f-34f7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=820&id=u1d0f2a48&margin=%5Bobject%20Object%5D&name=image.png&originHeight=1639&originWidth=1842&originalType=binary&ratio=1&rotation=0&showTitle=false&size=139326&status=done&style=none&taskId=u2d399c69-e021-46d1-ae3b-25897ec97d1&title=&width=921)
> 非递归思路：开始一一有序，归并成两两有序，两两有序归并成44有序，44有序归并成88有序，依次类推。


<a name="VPayK"></a>
### 非递归代码：
```c
void MergeSortNonR(int* a, int n)
{
    int* tmp=(int*)malloc(sizeof(int)*n);
    assert(tmp);
    int gap=1;
    while (gap<n)
    {
        for(int i=0;i<n;i+=2*gap)
        {
            int begin1=i, end1=i+gap-1;
            int begin2=i+gap, end2=i+2*gap-1;
            printf("--(%d,%d)--",begin1,end1);
            printf("--(%d-%d)--",begin2,end2);
            if(end1>=n||begin2>=n)
            {
                break;
            }
            else if(end2>=n)
            {
                end2=n-1;
            }
            int m=end2-begin1+1;
            int j=begin1;
            while (begin1<=end1&&begin2<=end2)
            {
                if(a[begin1]<a[begin2])
                {
                    tmp[j++]=a[begin1++];
                }
                else
                {
                    tmp[j++]=a[begin2++];
                }
            }
            while (begin1<=end1)
            {
                tmp[j++]=a[begin1++];
            }
            while(begin2<=end2)
            {
                tmp[j++]=a[begin2++];
            }
            memcpy(a+i, tmp+i, sizeof(int)*m);
        }
     
        gap*=2;
    }
    
    free(tmp);
}
```
<a name="xEJN2"></a>
## 八、计数排序


![image.png](https://cdn.nlark.com/yuque/0/2022/png/29247941/1657512855940-e8cc0685-b28e-448d-932d-b2b1ff0d4e70.png#clientId=ud1d7516f-34f7-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=498&id=u7fe56acb&margin=%5Bobject%20Object%5D&name=image.png&originHeight=996&originWidth=1438&originalType=binary&ratio=1&rotation=0&showTitle=false&size=44665&status=done&style=none&taskId=u205a1898-d922-4f17-bb27-9ef88c234e9&title=&width=719)
<a name="rpH9T"></a>
### 计数排序代码：
```c
void CountSort(int*a, int n)
{
    int max=a[0],min=a[0];
    for(int i=0;i<n;i++)
    {
        if(a[i]>max)
        {
            max=a[i];
        }
        if(a[i]<min)
        {
            min=a[i];
        }
    }
    int m=max-min+1;
    int* arr=(int*)malloc(sizeof(int)*m);
    memset(arr, 0, m*4);

    for(int i=0;i<n;i++)
    {
        arr[a[i]-min]++;
    }
    int j=0;
    for(int i=0;i<m;i++)
    {
        while(arr[i]--)
        {
            //printf("%d ",i+min);
            a[j++]=i+min;
        }
    }
}

```
