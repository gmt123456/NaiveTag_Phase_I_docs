# MINECODE使用指南

[TOC]

## 数据集

任务必须以`zip`压缩文件形式上传。

要求`zip`文件根目录下：

一个名为`data`的文件夹，其中放置所有图片。

一个`task.json`文件，描述任务形式。

### Json文件格式

1. 对图片整体标问题

```json
{
  "task-type": 100,
  "format": "jpg",
  "classes": ["name1", "name2", ...],
  "description": "这是任务描述"
}
```

2. 对图片整体注问题

```Json
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
  "image/xxx/161250001.jpg": [
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
    	[xx, xx],
    	[xx, xx], 
    	...
  	]
  }, 
  "filename2": {
  	"pos": [
    	[xx, xx],
    	[xx, xx], 
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
    	[xx, xx],
    	[xx, xx], 
    	...
  	]
  }, 
  "filename2": {
    "label": "xxxx",
  	"pos": [
    	[xx, xx],
    	[xx, xx], 
    	...
  	]
  }, 
  ...
}
```

### 