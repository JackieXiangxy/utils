# utils
### 统计一个字符串在一个文档中出现的次数

```java

	/**
	 * 统计一个字符串在一个文档中出现的次数
	 * 
	 * @param filePath
	 * @param strShow
	 * @return
	 */
	public static int getShowTimes(String filePath, String strShow) {
		StringBuilder sBuilder = new StringBuilder();
		String s1;
		int showTimes = 0, ss = 0;// 出现次数及每次跳过的字符
		try {
			BufferedReader readerIn = new BufferedReader(
					new InputStreamReader(new FileInputStream(new File(filePath))));
			while ((s1 = readerIn.readLine()) != null) {
				sBuilder.append(s1);
				sBuilder.append(" ");
			}
			readerIn.close();
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} catch (IOException e) {
			e.printStackTrace();
		}
		System.out.println(sBuilder.toString());
		while (sBuilder.indexOf(strShow, ss++) != -1) {
			showTimes++;
		}
		return showTimes;
	}

```

### 冒泡排序

```java

	/**
	 * 冒泡排序
	 * 
	 * @param num
	 */
	public static void bBubbleSort(int[] num) {
		for (int i = 0; i < num.length; i++) {
			for (int j = 0; j < num.length - 1 - i; j++) {
				if (num[j] > num[j + 1]) {
					int a = num[j + 1];
					num[j + 1] = num[j];
					num[j] = a;
				}
			}
		}
		for (int i : num) {
			System.out.print(i+" ");
		}
	}

```



### 简单排序

```java

	/**
	 * 简单排序
	 * @param num
	 */
	public static void sort(int[] num) {
		Arrays.parallelSort(num);
		for (int i : num) {
			System.out.print(i+" ");
		}
	}

```

### 数组实现队列



```java

/**
 * 使用数组模拟队列（先进先出）
 */
public class ArrayQueue {
    private int maxSize;//数组的最大容量
    private int front;//指向队列头
    private int rear;//指向队列尾
    private int arr[];//模拟队列

    /**
     * 队列初始化
     * @param maxSize
     */
    public ArrayQueue(int maxSize){
        this.maxSize=maxSize;
        this.arr=new int[maxSize];  //初始化队列的最大容量
        this.front=-1;//指向队列的头部，分析出front是指向队列头的前一个位置
        this.rear=-1;//指向队列的尾，指向队列尾的具体数据（即就是队列的最后一个数据）
    }

    /**
     * 判断是否已经满了
     * @return
     */
    public boolean isFull(){
        return rear==maxSize-1;
    }

    /**
     * 判断队列为空
     * @return
     */
    public boolean isEmpty(){
        return front==rear;
    }

    /**
     * 向队列中添加数据
     * @param n
     */
    public void addQueue(int n){
        if (isFull()){
            System.out.println("队列已满，无法添加数据");
            return ;
        }
        arr[++rear]=n;
    }

    /**
     * 获取队列中的全部数据
     * @return
     */
    public  int getQueue(){
        if (isEmpty()){
            throw new RuntimeException("队列为空，无法获取数据");
        }
        return arr[++front];
    }

    /**
     * 显示队列中数据
     */
    public void showQueue(){
        if (isEmpty()){
            System.out.println("队列为空，无法展示");
        }
        for (int i =0;i<arr.length;i++){
            System.out.print(" "+arr[i]);
        }
    }

}


```

