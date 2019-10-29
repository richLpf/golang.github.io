# time

> 获取时间
> 获取基本时间
```
package main
import (
	"time"
	"fmt"
)
func main() {
	// 获取当前时间 
	now := time.Now()
	fmt.Println("now", now)
	fmt.Println("now type", reflect.TypeOf(now))
	// 获取党建时间戳
	timestamp := now.Unix()
	fmt.Println("timestamp", timestamp)
	fmt.Println("timestamp type", reflect.TypeOf(timestamp))  // int64
}
```
注意：
- 获取的时间时区为CST
- 存储数据库最好的方法是unix时间戳
- 时间戳可以用来生成随机数

* 下面省略上面定义包和引入的包，直接展示函数 * 

> 获取年月日, 时分秒

```
func main() {
	now := time.Now()
	// 年
	year := now.Year()
	month := int(now.Month())
	day := now.Day()
	hour := now.Hour()
	minute := now.Minute()
	second := now.Second()
	fmt.Println("时间为", year, month, day, hour, minute, second)
	//fmt.Print
}
```

> 时间格式化
```
func timeFormat() {
	now := time.Now()
	str := now.Format("2006-01-02 15:04:05")
	fmt.Println("str", str)
}
```

#### time的常用方法

`语法： func Date(year int, month Month, day, hour, min, sec, nsec int, loc *Location) Time`

*将年月日时分秒纳秒时间转化成对应时区的时间格式*

``` 
date := time.Date(2019, 10, 1, 10, 2, 2, 100, time.UTC)
fmt.Println("date", date) 
```


```
func TryFunc() {

	
	// func Parse(layout, value string)(Time, error)
	str1, err := time.Parse("2006-01-02 15:04:05", "2019-10-10 12:00:12") // 将字符串时间转化成时间格式，utc时区
	fmt.Println("str1 and err", str1, err)

	//func Now() Time
	now := time.Now()
	// func(t Time)Clock()(hour, min, sec int)
	hour, min, sec := now.Clock()
	fmt.Println("result", hour, min, sec) // 获取对应时间的时分秒
}
```
* 官方文档 https://studygolang.com/pkgdoc

注意： 授人以渔不如授人以渔，time的操作其实还是比较简单的，在开发中比较常见，所以写下基础知识部分。希望可以帮助到你。