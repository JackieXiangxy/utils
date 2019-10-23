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



