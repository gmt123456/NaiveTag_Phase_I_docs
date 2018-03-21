# 详细设计描述文档

## 更新历史

| 修改人员 | 日期      | 变更原因             | 版本号 |
| -------- | --------- | -------------------- | ------ |
| 廖均达   | 2019-3-19 | 完成详细设计文档初稿 | 0.1    |

[TOC]

## 引言

### 编制目的

此文档用于指导后续软件构造，是了解系统的导航

### 产品概述

参见需求规格说明文档

## 结构视角

#### 用户界面层的分解

![用户界面跳转](pic\用户界面跳转.png)

#### 业务逻辑层的分解

## 信息视角

### json持久化格式

#### 标注信息

```json
{
  "task-type": 200,
  "format": "jpg",
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

4. 对图片单框注问题

```json
{
  "task-type": 201,
  "format": "jpg",
  "description": "这是任务描述"
}
```

5. 对图片进行多框标问题

```json
{
  "task-type": 300,
  "format": "jpg",
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

6. 对图片多框注问题

```json
{
  "task-type": 301,
  "format": "jpg",
  "description": "这是任务描述"
}
```

7. 对图片进行边界标

```json
{
  "task-type": 400,
  "format": "jpg",
  "description": "这是任务描述"
}
```

8. 对图片进行边界标并注

```json
{
  "task-type": 401,
  "format": "jpg",
  "description": "这是任务描述"
}
```

## 输出文件

输出文件的名称为`output.json`.

### 输出格式

1. 对图片整体标问题

```json
{
  "filename1": {
    "label": "xxxx"
  }, 
  "filename2": {
    "label": "yyy"
  }, 
  ...
}
```

2. 对图片整体注问题

```json
{
  "filename1": {
    "label": "xxxx"
  }, 
  "filename2": {
    "label": "yyy"
  }, 
  ...
}
```

3. 对图片单框标问题

```json
{
  "filename1": {
    "label": "xxxx",
    "pos": [xx, xx, xx, xx] //左，右，上，下，下同
  }, 
  "filename2": {
    "label": "yyy"
    "pos": [xx, xx, xx, xx]
  }, 
  ...
}
```

4. 对图片单框注问题

```json
{
  "filename1": {
    "label": "xxxx",
    "pos": [xx, xx, xx, xx]
  }, 
  "filename2": {
    "label": "yyy"
    "pos": [xx, xx, xx, xx]
  }, 
  ...
}
```

5. 对图片多框标问题

```json
{
  "filename1": [
    {
    "label": "xxxx",
    "pos": [xx, xx, xx, xx]
  	}, 
    {
    "label": "xxxx",
    "pos": [xx, xx, xx, xx]
  	}
  ], 
  "filename2": [
    {
    "label": "yyy"
    "pos": [xx, xx, xx, xx]
  	}
   ]
  , 
  ...
}
```

6. 对图片多框注问题

```json
{
  "filename1": [
    {
    "label": "xxxx",
    "pos": [xx, xx, xx, xx]
  	}, 
    {
    "label": "xxxx",
    "pos": [xx, xx, xx, xx]
  	}
  ], 
  "filename2": [
    {
    "label": "yyy"
    "pos": [xx, xx, xx, xx]
  	}
   ]
  , 
  ...
}
```

7. 对图片进行边界标

```json
{
  "filename1": {
  	"pos": [
    	[xx, xx, xx, xx],
    	[xx, xx, xx, xx], 
    	...
  	]
  }, 
  "filename2": {
  	"pos": [
    	[xx, xx, xx, xx],
    	[xx, xx, xx, xx], 
    	...
  	]
  }, 
  ...
}
```

8. 对图片进行边界标并注

```json
{
  "filename1": {
    "label": "xxxx",
  	"pos": [
    	[xx, xx, xx, xx],
    	[xx, xx, xx, xx], 
    	...
  	]
  }, 
  "filename2": {
    "label": "xxxx",
  	"pos": [
    	[xx, xx, xx, xx],
    	[xx, xx, xx, xx], 
    	...
  	]
  }, 
  ...
}
```

#### 数据集的说明文件

1. 对图片整体标问题

```json
{
  "task-type": 100,
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

2. 对图片整体注问题

```Json
{
  "task-type": 101,
  "description": "这是任务描述"
}
```

3. 对图片单框标问题

```json
{
  "task-type": 200,
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

4. 对图片单框注问题

```json
{
  "task-type": 201,
  "description": "这是任务描述"
}
```

5. 对图片进行多框标问题

```json
{
  "task-type": 300,
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

6. 对图片多框注问题

```json
{
  "task-type": 301,
  "description": "这是任务描述"
}
```

7. 对图片进行边界标

```json
{
  "task-type": 400,
  "description": "这是任务描述"
}
```

8. 对图片进行边界标并注

```json
{
  "task-type": 401,
  "description": "这是任务描述"
}
```
#### 

