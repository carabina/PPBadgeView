# PPBadgeView

iOS Custom Badge, Support UIView, UITabBarItem, UIBarButtonItem

iOS自定义Badge组件, 支持UIView, UITabBarItem, UIBarButtonItem以及子类

![](https://img.shields.io/badge/platform-iOS-red.svg)   ![](https://img.shields.io/badge/language-Objective--C%2FSwift%203.0-orange.svg) ![](https://img.shields.io/cocoapods/v/PPBadgeView.svg?style=flat) ![](https://img.shields.io/cocoapods/dt/PPBadgeView.svg) ![](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)  [![](https://img.shields.io/badge/weibo-jkpang--%E5%BA%9E-red.svg)](http://weibo.com/5743737098/profile?rightmod=1&wvr=6&mod=personinfo&is_all=1)


![iPhone](https://github.com/jkpang/PPBadgeView/blob/master/Picture/PPBadgeView.gif)

## Requirements 要求
* iOS 8+
* Xcode 8+

## Installation 安装
### 1.手动安装:
##### 下载 PPBadgeView Demo
* Objective-C : 拖入PPBadgeView/objc文件夹中的.h与.m文件, #import "PPBadgeView.h" 开始使用
* Swift : 拖入PPBadgeView/swift文件夹中的.swift文件开始使用

### 2.CocoaPods安装:
 * Objective-C :  `pod 'PPBadgeView'` then `#import <PPBadgeView.h>`
 * Swift :        `pod 'PPBadgeViewSwift' ` then `import PPBadgeViewSwift`

如果发现pod search PPBadgeView/PPBadgeViewSwift 不是最新版本，在终端执行pod setup命令更新本地spec镜像缓存(时间可能有点长),重新搜索就OK了

## Usage 使用方法
##### 1. Objective-C :
```objc
view = UIView, UITabBarItem, UIBarButtonItem及其子类

// 添加带文本内容的Badge, 默认右上角, 红色, 18pts
[view pp_addBadgeWithText:@"99+"];

// 添加带数字的Badge, 默认右上角,红色,18pts
[view pp_addBadgeWithNumber:1];

// 添加带颜色的小圆点, 默认右上角, 红色, 8pts
[view pp_addDotWithColor:nil];

/**
 设置Badge的高度,因为Badge宽度是动态可变的,通过改变Badge高度,其宽度也按比例变化,方便布局
 (注意: 此方法需要将Badge添加到控件上后再调用!!!)
 
 @param points 高度大小
 */
[view pp_setBadgeHeightPoints:25];

/**
 设置Badge的偏移量, Badge中心点默认为其父视图的右上角
 
 @param x X轴偏移量 (x<0: 左移, x>0: 右移)
 @param y Y轴偏移量 (y<0: 上移, y>0: 下移)
 */
[view pp_moveBadgeWithX:-7 Y:5];

/**
 设置Bage的属性
 */
[view pp_setBadgeLabelAttributes:^(PPBadgeLabel *badgeLabel) {
        badgeLabel.backgroundColor = [UIColor redColor];
        badgeLabel.font =  [UIFont systemFontOfSize:13];
        badgeLabel.textColor = [UIColor blueColor];
    }];

// 数字增加/减少, 注意:以下方法只适用于Badge内容为纯数字的情况
[view pp_decrease];
[view pp_increase];
```

##### 2. Swift :
```swift
view = UIView, UITabBarItem, UIBarButtonItem及其子类

// 添加带文本内容的Badge, 默认右上角, 红色, 18pts
view?.pp_addBadge(text: "99+");

// 添加带数字的Badge, 默认右上角,红色,18pts
view?.pp_addBadge(number: 1);

// 设置Badge的高度,因为Badge宽度是动态可变的,通过改变Badge高度,其宽度也按比例变化,方便布局
// (注意: 此方法需要将Badge添加到控件上后再调用!!!)
view?.pp_setBadgeHeight(points: 21.0);

/// 设置Badge的偏移量, Badge中心点默认为其父视图的右上角
///
/// - Parameters:
///   - x: X轴偏移量 (x<0: 左移, x>0: 右移)
///   - y: Y轴偏移量 (y<0: 上移, y>0: 下移)
view?.pp_moveBadge(x: -7, y: 5)

// 自定义badge的属性: 字体大小/颜色, 背景颜色...(默认系统字体13,白色,背景色为系统badge红色)
view?.pp_setBadgeLabel(attributes: { (badgeLabel) in
      badgeLabel.font = UIFont.systemFont(ofSize: 13)
      badgeLabel.textColor = UIColor.blue
})

// 数字增加/减少, 注意:以下方法只适用于Badge内容为纯数字的情况
view?.pp_decrease()
view?.pp_increase()
```

#### 更多的用法请查看Demo
===

## CocoaPods更新日志
* 2017.06.21(tag:1.0.0)--初始化到CocoaPods;
## 联系方式:
* Weibo : [@jkpang-庞](http://weibo.com/5743737098/profile?rightmod=1&wvr=6&mod=personinfo&is_all=1)
* Email : jkpang@outlook.com
* QQ群 : 323408051

![PP-iOS学习交流群群二维码](https://github.com/jkpang/PPCounter/blob/master/PP-iOS%E5%AD%A6%E4%B9%A0%E4%BA%A4%E6%B5%81%E7%BE%A4%E7%BE%A4%E4%BA%8C%E7%BB%B4%E7%A0%81.png)


