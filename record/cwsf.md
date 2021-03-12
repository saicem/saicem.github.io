---
title: cwsf的爬虫记录<br>
date: 2021-02-20 19:32:31
---
>爬虫基础不在本篇讨论范围内。
如果关于如何爬取网页还有疑问，请参考其它教程。

## 分析

[![yYf9Wd.png](https://s3.ax1x.com/2021/02/06/yYf9Wd.png)](https://imgchr.com/i/yYf9Wd)

映入眼帘的比较难搞的就是这个验证码了，不过验证码只有数字且数字没有变形，图形没有奇怪的干扰元素，比较好处理。

其余的，请求表单没有加密，看样子难点就只有这个验证码了。

## 验证码处理

爬取验证码

将图片进行灰度化，二值化，并去掉边框后得到易于处理的格式。

[![yYfBOx.png](https://s3.ax1x.com/2021/02/06/yYfBOx.png)](https://imgchr.com/i/yYfBOx)

```
pathGray = './Image_gray/'
pathPng = './Image_png/'

def Greb2Gray():
  // 遍历爬取的验证码图片 获得其文件名列表
  lsFile = os.listdir(pathPng)
  // 遍历文件名
  for file in lsFile:
    // 以灰度图读取爬取的验证码图片
    im_gray = cv2.imread('./Image_png/' + file,0)
    // 二值化处理
    ret, im_inv = cv2.threshold(im_gray, 127, 255, cv2.THRESH_BINARY_INV)
    // 去边框
    cutImage = im_inv[1:19, 1:69]
    // 存储图片 file文件名带有后缀，需要将后缀改为jpg格式
    cv2.imwrite(pathGray + file.split('.')[0] + '.jpg', cutImage)
```

## 咕咕咕
