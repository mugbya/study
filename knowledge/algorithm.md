2. 请用递归实现一个字符串反转

   ```python
   def reverse(_str):
       if len(_str) == 1:
           return _str
       else:
           return reverse(_str[1:]) + _str[0]
   ```

3. 重复的DNA序列。
	
	所有 DNA 由一系列缩写为 A，C，G 和 T 的核苷酸组成，例如：“ACGAATTCCG”。在研究 DNA 时，识别 DNA 中的重复序列有时会对研究非常有帮助。

	编写一个函数来查找 DNA 分子中所有出现超多一次的10个字母长的序列（子串）。

	示例:

		输入: s = "AAAAACCCCCAAAAACCCCCCAAAAAGGGTTT"
		
		输出: ["AAAAACCCCC", "CCCCCAAAAA"]

	 ```
	class Solution(object):
	    def findRepeatedDnaSequences(self, s):
	        """
	        :type s: str
	        :rtype: List[str]
	        """
	        res = []
	        if len(s) > 50000:
	            return []
	        for index in range(len(s) - 9):
	            _str = s[index:index + 10]
	            if _str in s[index + 1:] and _str not in res:
	                res.append(_str)
	        return res
	 ```
