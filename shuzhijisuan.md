public class shuzu {
	static int[] arr =
	    {
	            5, 2, -3, -10, 10, -7, 2, -2
	    };// 需要求的数组
	    static int maxIndex = arr.length - 1;// 数组的最大下标
	 
	    public static void main(String[] args)
	    {
	        findMaxArr2();
	        System.out.println("\n-------------");
	        findMaxArr3();
	    }
	 
	    // 1.三层for循环求解
	    // 2.二层for循环求解
	    static void findMaxArr2()
	    {
	        int max = arr[0];// 最大值
	        int sum;// 求和
	        int startIndex = 0;
	        int endIndex = 0;
	        for (int i = 0; i <= maxIndex; i++)
	        {
	            sum = 0;
	            for (int j = i; j <= maxIndex; j++)
	            {
	                sum += arr[j];
	                if (sum > max)
	                {
	                    max = sum;
	                    startIndex = i;
	                    endIndex = j;
	                }
	            }
	        }
	        System.out.println("最大值为：" + max);
	        printArr(startIndex, endIndex);
	    }
	 
	    // 3.时间复杂度为n
	    static void findMaxArr3()
	    {
	        int max = arr[0];// 最大值
	        int sum = 0;// 求和
	        int startIndex = 0;
	        int endIndex = 0;
	        for (int i = 0; i <= maxIndex; i++)
	        {
	            if (sum >= 0)
	            {
	                sum += arr[i];
	            }
	            else
	            {
	                sum = arr[i];
	                startIndex = i;// 最大子数组开始值
	            }
	            if (sum > max)
	            {
	                max = sum;
	                endIndex = i;// 最大子数组结束值
	            }
	        }
	        System.out.println("最大值为：" + max);
	        printArr(startIndex, endIndex);
	    }
	 
	    // 根据下标开始结束值，打印数组
	    static void printArr(int startIndex, int endIndex)
	    {
	        for (int i = startIndex; i <= endIndex; i++)
	        {
	            System.out.print(arr[i] + " ");
	        }
	    }
	 
	}
