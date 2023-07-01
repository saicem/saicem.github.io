# icalendar

## 关于icalendar

`iCalendar`，是一种标准的互联网日历格式，文件以`.ics`后缀。让用户能够在各种计算机和各种程序之间创建和共享电子日历。目前已受众多应用支持。如果邮箱支持 ExChange 协议则可以同步邮箱的日程信息，使用 `CalDAV` 协议可以从网络订阅日历。

详情可参考 [RFC 5545](https://icalendar.org/RFC-Specifications/iCalendar-RFC-5545/)
如果你对 RFC 文档看的头疼。

- [How to Read an RFC](https://www.mnot.net/blog/2018/07/31/read_rfc)
- [如何阅读RFC文档](https://juejin.cn/post/6844903716051484679)

## 一个完整的例子

```ical
BEGIN:VCALENDAR
VERSION:2.0
PRODID:-//saicem//iwut
BEGIN:VEVENT
UID:00000000-0000-0000-0000-000000000000
DTSTAMP:20210109T172659Z
SUMMARY:通用学术英语
LOCATION:博学北楼(原新4)-312
DESCRIPTION:汪鹭
DTSTART:20210426T000000Z
DTEND:20210426T013500Z
RRULE:FREQ=WEEKLY;INTERVAL=1;BYDAY=MO;COUNT=1
END:VEVENT
END:VCALENDAR
```

一个日历必备的属性有`VERSION`,`PRODID`。
而其中的组件必须有`UID`。
至于你编写的ical文件是否符合标准尝试使用 [iCalendar Validator](https://icalendar.org/validator.html)

## Event 组件

```ical
BEGIN:VEVENT                                    ; 事件开始标识
UID:00000000-0000-0000-0000-000000000000        ; 只要唯一即可
DTSTAMP:20210109T172659Z                        ; 生成时间
SUMMARY:通用学术英语                              ; 事件概要
LOCATION:博学北楼(原新4)-312                      ; 事件地点
DESCRIPTION:汪鹭                                 ; 事件描述
DTSTART:20210426T000000Z                        ; 事件开始时间
DTEND:20210426T013500Z                          ; 事件结束事件
RRULE:FREQ=WEEKLY;INTERVAL=1;BYDAY=MO;COUNT=1   ; 事件循环条件
END:VEVENT                                      ; 事件结束标识
```

考虑发生一整日的事件

```ical
DTSTART;VALUE=DATE:20070628                    ; 事件开始日期
DTEND;VALUE=DATE:20070709                      ; 事件结束日期
```

更多例子参考 [Event Component](https://icalendar.org/iCalendar-RFC-5545/3-6-1-event-component.html)

## 如何设定时区

仅支持三种格式

```ics
DTSTART:19970714T133000                       ; Local time
DTSTART:19970714T173000Z                      ; UTC time
DTSTART;TZID=America/New_York:19970714T133000 ; Time zone reference
```

`TZID` 属性参数仅仅可用于 `DTSTART` `DTEND`，其他必须为 UTC.

[What's VTIMEZONE used for in icalendar? Why not just UTC time?](https://stackoverflow.com/questions/42919630/whats-vtimezone-used-for-in-icalendar-why-not-just-utc-time)

## 设定事件循环条件

直接看 [recurrence-rule](https://icalendar.org/iCalendar-RFC-5545/3-3-10-recurrence-rule.html)

## 注意事项

- icalendar 默认的字符集为 UTF-8
- 不完全按格式来写有时能被成功读取，但为了确保你的 iCal 文件能够稳定使用请确保你编写的文件符合规范。

## Content Lines

> 实际上不被遵守的标准

iCalendar 对象被组织成单独的文本行，称为 Content Lines。Content Lines被换行符分割，并且应该不超过75个octet。（不包括换行符）
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

## 支持

- [在 Outlook.com 中导入或订阅日历](https://support.microsoft.com/zh-cn/office/%E5%9C%A8-outlook-com-%E4%B8%AD%E5%AF%BC%E5%85%A5%E6%88%96%E8%AE%A2%E9%98%85%E6%97%A5%E5%8E%86-cff1429c-5af6-41ec-a5b4-74f2c278e98c)
- [使用 iCloud 日历订阅](https://support.apple.com/zh-cn/HT202361)

## 其它

- [iCalendar 验证器](https://icalendar.org/validator.html)
- [RRULE 生成工具](https://icalendar.org/rrule-tool.html)
- [维基百科](https://en.wikipedia.org/wiki/List_of_applications_with_iCalendar_support)
