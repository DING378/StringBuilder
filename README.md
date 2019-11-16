# JAVA实验报告 字符串实验
# 一、实验目的
掌握字符串String及其方法的使用
掌握异常处理结构  
# 二、业务要求
内容：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能函数，并运行。达到如下功能：  
1.	每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”  
2.	允许提供输入参数，统计古诗中某个字或词出现的次数  
3.	考虑操作中可能出现的异常，在程序中设计异常处理程序    
输出：
汉皇重色思倾国，御宇多年求不得。
杨家有女初长成，养在深闺人未识。
天生丽质难自弃，一朝选在君王侧。
回眸一笑百媚生，六宫粉黛无颜色。
春寒赐浴华清池，温泉水滑洗凝脂。
侍儿扶起娇无力，始是新承恩泽时。
云鬓花颜金步摇，芙蓉帐暖度春宵。
春宵苦短日高起，从此君王不早朝。
…………  
注意： 输入的内容，利用main方法中的args数组传递

# 三、实验步骤
1.打开eclipse--创建项目StringBuilder--包名cn.itcase_01--类名StringBufferDemo  
2.创建一个StringBuilder类的对象，通过对象名.append()方法添加古诗。创建一个字符串  
3.利用for循环遍历：每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”；输出结果将StringBuilder转化成字符串，这层循环价格异常捕获，如果循环出错，就捕获异常  
4.定义功能（允许提供输入参数，统计古诗中某个字或词出现的次数）getCount  
5.getCount中先定义一个统计变量，初始化值是0，然后先在大串中查找一次小串第一次出现的位置，在循环，如果索引不是-1，说明存在，统计变量++，最后返回count  
6.getCount()方法完成后，在StringBuilder类中调用，并实现最终的功能查找  

# 四、核心代码。
1.每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
		for (int i = 0; i < str.length(); i++) {
			if (i * 7 + 7 > str.length()) {
				str2 += str.substring(i * 7, str.length());
				break;
			}
			if ((i * 7) % 2 == 0) {
				str2 += str.substring(i * 7, i * 7 + 7) + "，";
			} else {
				str2 += str.substring(i * 7, i * 7 + 7) + "。" + "\n";
			}
		}  
  2. 定义一个统计变量，初始化值是0
		int count = 0;
		// 先在大串中查找一次小串第一次出现的位置
		int index = maxString.indexOf(minString);
		// 索引不是-1，说明存在，统计变量++
		while (index != -1) {
			count++;
			// 把刚才的索引+小串的长度作为开始位置截取上一次的大串，返回一个新的字符串，并把该字符串的值重新赋值给大串
			int startIndex = index + minString.length();
			maxString = maxString.substring(startIndex);
			// 继续查
			index = maxString.indexOf(minString);
		}
		return count;  
   
   # 运行结果
   
 
