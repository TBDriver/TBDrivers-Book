layout: draft
title: 一个vector矩阵生成器
author: 闰土
tags:
  - vector
categories:
  - C++
date: 2023-05-20 14:58:00
---
半天时间写的，用于int转vec矩阵    
<!--more-->
```c++
vector< vector <int> > generateVecs ( initializer_list< int > List) {
	vector < vector<int> > tempVec;
	vector <int> inTempVec;
	for ( auto beg = List.begin(); beg != List.end(); beg++ ) {
		if (*beg) {
			inTempVec.push_back(*beg);
		}
		else{
			tempVec.push_back(inTempVec);
			inTempVec.resize(0);
		}
	}
	return tempVec;
}
```
数组中用0为向量的分割。   
代码来来回回改了好多版都不满意，用stdargs太臃肿了（笑   
性能尚未测试，应该还能优化awa   
如果有其他数据类型的需要，应该略微改下代码就行了x   
实际使用例如下：   
```c++
#include <vector>
#include <iostream>
using namespace std;

vector< vector <int> > generateVecs ( initializer_list< int > List) {
	vector < vector<int> > tempVec;
	vector <int> inTempVec;
	for ( auto beg = List.begin(); beg != List.end(); beg++ ) {
		if (*beg) {
			inTempVec.push_back(*beg);
		}
		else{
			tempVec.push_back(inTempVec);
			inTempVec.resize(0);
		}
	}
	return tempVec;
}

int main() {
    vector< vector<int> > tempVec = generateVecs({ 3, 2, 1, 0, 1, 1, 1, 0, 2, 2, 2, 3, 0 });
    /*
    实际tempVec值:
    3 2 1
    1 1 1
    2 2 2 3
    */
    return 0;
}
```