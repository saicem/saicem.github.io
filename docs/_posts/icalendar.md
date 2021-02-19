# 关于icalendar

`iCalendar`，是一种标准的互联网日历格式，文件以`.ics`后缀。让用户能够在各种计算机和各种程序之间创建和共享电子日历。目前已受众多应用支持。如outlook，gmail，iCloud日历，华为日历，小米日历。使用webcal协议可以从网络订阅日历，这使得日历能有更丰富的应用。

详情可参考[iCalendar.org](https://icalendar.org/)或[RFC 5545](https://tools.ietf.org/html/rfc5545)
RFC看的挺难受的，你或许需要一个看RFC的[教程](https://zhuanlan.zhihu.com/p/44635072)

## 例子
```ical
BEGIN:VCALENDAR
VERSION:2.0
PRODID:cal@0121904950722
BEGIN:VEVENT
UID:20210109T172659Z-0121904950722-1
SUMMARY:通用学术英语
LOCATION:博学北楼(原新4)-312
DESCRIPTION:汪鹭
DTSTAMP:20210109T172659Z
DTSTART:20210426T000000Z
DTEND:20210426T013500Z
RRULE:FREQ=WEEKLY;INTERVAL=1;BYDAY=MO;COUNT=1
END:VEVENT
END:VCALENDAR
```
一个日历必备的属性有`VERSION`,`PRODID`。
而其中的组件必须有`UID`。
至于你编写的ical文件是否符合标准可参考[iCalendar验证器](https://icalendar.org/validator.html)
# 组件

## Event

[Event Component](https://icalendar.org/iCalendar-RFC-5545/3-6-1-event-component.html)

```ical
BEGIN:VEVENT                                    # 事件开始标识
UID:20210109T172659Z-0121904950722-1            # UID 只要不同就好了
SUMMARY:通用学术英语                             # 事件概要
LOCATION:博学北楼(原新4)-312                     # 事件发生地点
DESCRIPTION:汪鹭                                # 事件发生的详细信息
DTSTAMP:20210109T172659Z                        # 时间戳 实际随便写
DTSTART:20210426T000000Z                        # 事件开始时间
DTEND:20210426T013500Z                          # 事件结束事件
RRULE:FREQ=WEEKLY;INTERVAL=1;BYDAY=MO;COUNT=1   # 事件循环条件
END:VEVENT                                      # 事件结束标识
```

## To-Do

[To-Do Component](https://icalendar.org/iCalendar-RFC-5545/3-6-2-to-do-component.html)

## Journal

[Journal Component](https://icalendar.org/iCalendar-RFC-5545/3-6-3-journal-component.html)

## Alarm

[Alarm Component](https://icalendar.org/iCalendar-RFC-5545/3-6-6-alarm-component.html)

## Time Zone

[Time Zone Component](https://icalendar.org/iCalendar-RFC-5545/3-6-5-time-zone-component.html)

# 额外内容

## 如何设定时区

针对单个事件
```
DTSTART;TZID=America/New_York:19980119T020000
```
针对全部事件见组件[Time Zone](#Time-Zone)

`TZID` 属性参数不能被用于 `DATE` `DATE-TIME` `TIME` 的属性，因为他们被特定为UTC.（国际协调时间）

# 注意事项

## 需要注意的一个问题

不完全按格式来写有时能被成功读取，但也可能会让你的`icalendar`文件在被读取时出现意想不到的问题。

## 格式惯例

所有日历组件都是大写的且以字母"V"开头。例如"VEVENT"指事件，"VTODO"指待办，"VJOURNAL"指日志。而属性参数通常用小写表示。

## Content Lines

iCalendar 对象被组织成单独的文本行，称为 Content Lines。Content Lines被换行符分割，并且应该不超过75个octet。 （不包括换行符）
> 1 octet = 8 bit

你可以使用行“折叠”技术来将一行内容拆分为多行。即在一个换行符后接一个空白符(SPACE or HTAB)。如下
```ical
DESCRIPTION:This is a long description that exists on a long line.
```

```ical
DESCRIPTION:This is a lo
 ng description
  that exists on a long line.
```

## 编码

icalendar默认的字符集为 utf-8

# 其它

- [iCalendar验证器](https://icalendar.org/validator.html)
- [RRULE生成工具](https://icalendar.org/rrule-tool.html)
- [维基百科](https://en.wikipedia.org/wiki/List_of_applications_with_iCalendar_support)
- [在 Outlook.com 中导入或订阅日历](https://support.microsoft.com/zh-cn/office/%E5%9C%A8-outlook-com-%E4%B8%AD%E5%AF%BC%E5%85%A5%E6%88%96%E8%AE%A2%E9%98%85%E6%97%A5%E5%8E%86-cff1429c-5af6-41ec-a5b4-74f2c278e98c)
- [使用 iCloud 日历订阅](https://support.apple.com/zh-cn/HT202361)
- [华为日历订阅日历](https://club.huawei.com/thread-24908693-1-1.html)