---
title: IDEA注释模板
date: 2019-09-21 20:53:32
tags: IDEA
---

## IDEA类和方法注释模板的配置

参考博客： https://blog.csdn.net/qq_34581118/article/details/78409782

### 1.生成类注释
* 打开Preferences
* Editor -> File and Code Templates -> Files -> Class

![](/images/IDEA/idea-class-comment.png)

* 生成注解类模板
```
/**
* @program: ${PROJECT_NAME}
*
* @description: ${description}
*
* @author: Mr.Wang
*
* @create: ${YEAR}-${MONTH}-${DAY} ${HOUR}:${MINUTE}
**/
```

---

### 2.生成方法注释
* 打开Preferences
* Editor -> Live Templates -> 点击右边加号为自己添加一个Templates Group -> 然后选中自己的Group再次点击加号添加Live Templates
* 然后设置自己喜欢的快捷键 在Abbreviation里面 记得在Applicable in 里面勾选,起码也要勾选class
* 然后在Edit variables里面添加参数和返回值的自动取值
* 然后再你的方法上面直接输入/ + 你设置的Abbreviation快捷键 + tab键就直接生成了 （我设置的是/+ a + tab）

![](/images/IDEA/idea-function-comment.png)

* 生成方法注解模板
```
**
* @Description: $description$
* @Param: $params$
* @return: $returns$
* @Author: Mr.Wang
* @Date: $date$
*/
```
