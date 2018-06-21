# SwiftDate 使用教程

~~~
	// 日期转字符串
    func dateToString() {
        let date = DateInRegion(absoluteDate: Date())
        let timeStr = date.string(format: DateFormat.custom("yyyy-MM-dd HH:mm:ss"))
        print(timeStr)
    }
    
   // 字符串转日期
       func stringToDate() {
        let date = DateInRegion(string: "2016-12-13 18:30:00", format: DateFormat.custom("yyyy-MM-dd HH:mm:ss"))
        print(date as Any)
        
        let timeStr = date?.string(format: DateFormat.custom("yyyy-MM-dd HH:mm:ss"))
        print(timeStr as Any)
    }
    
    // 获取年月日
       func Ymd() {
        let date = DateInRegion(absoluteDate: Date())
        print("\(date.year)" + " 年 "  + "\(date.month)" + " 月 " + "\(date.day)" + " 日 " + "\(date.hour)" + " 时 "  + "\(date.minute)" + " 分 " + "\(date.second)" + " 秒 " )
    }
    
    // 今天星期几
      func testWeek() {
        let date = DateInRegion(absoluteDate: Date())
        print("今天是 " + date.weekdayName)
        print("\(date.month)" + " 月有" + "\(date.monthDays)" + " 天")
    }  
    
    // 日期比较时间戳 
     fileprivate func timeInterval() {
        guard let oldDate = DateInRegion(string: "2018-06-20 15:10:00", format: DateFormat.custom("yyyy-MM-dd HH:mm:ss")) else {
            return
        }
        
        let currentDate = DateInRegion(absoluteDate: Date())
        let timeInterval = DateTimeInterval.init(start: oldDate.absoluteDate, end: currentDate.absoluteDate)
        
        print("\(oldDate) 与 \(currentDate) 时间差 \(timeInterval.duration)")
    }
~~~