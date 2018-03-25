# NaiveTag 部署文档

[TOC]

## 部署方法

请直接访问[NaiveTag](http://139.196.75.242:8080/naive/index.html)。上传时间可能会较长，请耐心等待

## 使用方法

1. 选择合适的数据集（我们在VariousDataSet文件目录中已经准备好了样例数据集）进行上传

   ![2](pic\select.png)

2. 进入主界面后选择一张图片进入标注界面（填写完所有的信息后才能切换图片以及点击保存）

   ![3](pic\main.png)

3. 保存后会自动返回主界面，此时可以选择查看历史标注

   ![history](pic\history.png)

4. 点击一张图片即进入修改界面

## 数据要求

### 压缩包格式

任务必须以`zip`压缩文件形式上传。要求`zip`文件根目录下：

- 压缩包中第一个文件夹命名应和压缩包命名一致，且文件命名要求为英文命名

  ![dataset0](pic\dataset0.png)


- 根文件夹中有两个文件，一个名为`data`的文件夹，其中放置所有图片。一个`task.json`文件，描述任务形式。

  ![dataset1](pic\dataset1.png)

  ​

### task.json 格式描述

1. 对图片整体标问题

```json
{
  "task-type": 100,
  "format": "jpg",
  "classes": ["name1", "name2", ...], //任务标签
  "description": "这是任务描述"
}
```

2. 对图片整体注问题

```json
{
  "taskType": 101,
  "format": "jpg",
  "description": "这是任务描述"
}
```

3. 对图片单框标问题

```json
{
  "taskType": 200,
  "format": "jpg",
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

4. 对图片单框注问题

```json
{
  "taskType": 201,
  "format": "jpg",
  "description": "这是任务描述"
}
```

5. 对图片进行多框标问题

```json
{
  "taskType": 300,
  "format": "jpg",
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

6. 对图片多框注问题

```json
{
  "taskType": 301,
  "format": "jpg",
  "description": "这是任务描述"
}
```

7. 对图片进行边界标

```json
{
  "taskType": 400,
  "format": "jpg",
  "description": "这是任务描述"
}
```

8. 对图片进行边界标并注

```json
{
  "taskType": 401,
  "format": "jpg",
  "classes": ["name1", "name2", ...],
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

### 