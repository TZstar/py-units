# pandas-unit

> By: Zeng Wei  
> E-mail: zengweihgc@163.com  
> 好记性不如烂笔头（A bad pen is better than a good memory!）  
> 希望整理出一些pandas的案例，以供大家讨论、练习、查阅！

---
## 1 目录

	1. 日期和时间序列整理；

## 2 pandas知识结构

### 2.1 series
	1. series
	

### 2.1 DataFrame
> 按照**增查删改+运算+高级**的分类模式，来划分结构。

	1. 增（创建）：
		- 创建新的df
		- 创建新的行列  
	2. 查（查找）：  
		- 索引和切片
		- 属性
	3. 删（删除）： 
		- 去重
		- 去除异常值   
	4. 改（修改）：
		- 替换值
		- 修改行列值
		- 重索引
		- 列标签重写
	5. 运算：
		- df 之间的运算
		- df 与 series 之间的运算  
	6. 高级：
		- 排序 (take,df.sort_index,df.sort_values)
		- 分类聚合 ()
		- 行列转置（pd.melt）
		- 函数应用（map,apply,transfer）   