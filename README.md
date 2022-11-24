package main

import (
	"fmt"
)

type 张三 struct {
	Borrow int //借款
	Refund int //存入
	Total  int //总和

}
type 李四 struct {
	Borrow int //借款
	Refund int //存入
	Total  int //总和
}

type homo struct {
	Borrow int //借款
	Refund int //存入
	Total  int //总和
}

func main() {
	var a 张三
	a.Borrow = 1000
	a.Refund = 500
	a.Total = a.Refund - a.Borrow

	var b 李四
	b.Borrow = 100
	b.Refund = 500
	b.Total = b.Refund - b.Borrow

	var c homo
	c.Borrow = 114514
	c.Refund = 111444
	c.Total = c.Refund - c.Borrow

	name := ""

	key := ""
	loop := true
	for {
		fmt.Print("\n")
		fmt.Println("------------------ 债务备忘录软件-----------------")
		fmt.Println("                   1 借债")
		fmt.Println("                   2 还债/存入")
		fmt.Println("                   3 总额和(模拟后台查看记录)")
		fmt.Println("                   4 欠债查询")
		fmt.Println("                   5 总览(模拟后台查看记录)")
		fmt.Println("                   6.退出系统 ")
		fmt.Println("请选择(1-6):")

		fmt.Scanln(&key)

		switch key {
		case "1":
			fmt.Println("请输入姓名")
			fmt.Scanln(&name)
			switch name {
			case "张三":
				fmt.Println("输入借款金额")
				var z int
				fmt.Scanln(&z)
				a.Borrow += z
				fmt.Print("借款金额：  ")
				fmt.Println(a.Borrow)
			case "李四":
				fmt.Println("输入借款金额")
				var z int
				fmt.Scanln(&z)
				b.Borrow += z
				fmt.Print("借款金额：  ")
				fmt.Println(b.Borrow)
			case "homo":
				fmt.Println("输入借款金额")
				var z int
				fmt.Scanln(&z)
				c.Borrow += z
				fmt.Print("借款金额：  ")
				fmt.Println(c.Borrow)
			}

			fmt.Println("输入借款金额")

		case "2":
			fmt.Println("请输入查询姓名")
			fmt.Scanln(&name)
			switch name {
			case "张三":
				fmt.Println("输入还款金额")
				var l int
				fmt.Scanln(&l)
				a.Refund += l
				fmt.Print("还款金额：  ")
				fmt.Println(a.Refund)
			case "李四":
				fmt.Println("输入还款金额")
				var l int
				fmt.Scanln(&l)
				b.Refund += l
				fmt.Print("还款金额：  ")
				fmt.Println(b.Refund)
			case "homo":
				fmt.Println("输入还款金额")
				var l int
				fmt.Scanln(&l)
				c.Refund += l
				fmt.Print("还款金额：  ")
				fmt.Println(c.Refund)

			}
		case "3":
			fmt.Println("请输入查询姓名")
			fmt.Scanln(&name)
			switch name {
			case "张三":

				fmt.Print("总金额：  ")
				fmt.Println(a.Total)
			case "李四":
				fmt.Print("总金额：  ")
				fmt.Println(b.Total)
			case "homo":
				fmt.Print("总金额：  ")
				fmt.Println(c.Total)
			}

		case "4":
			fmt.Println("请输入查询姓名")
			fmt.Scanln(&name)
			switch name {
			case "张三":
				if a.Total < 0 {
					fmt.Println("呜呜呜呜呜，很抱歉，《欠债中》")
					fmt.Print("余额")
					fmt.Print(a.Total)
				}
				if a.Total > 0 {
					fmt.Println("恭喜你，未欠债，可以放心挥霍")
					fmt.Print("余额")
					fmt.Print(a.Total)
				}

			case "李四":
				if b.Total < 0 {
					fmt.Println("呜呜呜呜呜，很抱歉，《欠债中》")
					fmt.Print("余额")
					fmt.Print(b.Total)
				}
				if b.Total > 0 {
					fmt.Println("恭喜你，未欠债，可以放心挥霍")
					fmt.Print("余额")
					fmt.Print(b.Total)
				}

			case "homo":
				if c.Total < 0 {
					fmt.Println("呜呜呜呜呜，很抱歉，《欠债中》")
					fmt.Print("余额")
					fmt.Print(c.Total)
				}
				if c.Total > 0 {
					fmt.Println("恭喜你，未欠债，可以放心挥霍")
					fmt.Print("余额")
					fmt.Print(c.Total)
				}
			}

		case "5":
			fmt.Println("------------------《总    览》 -----------------")
			fmt.Println("姓名----借款-还款-总额--------------------")
			fmt.Print("张三    ")
			fmt.Println(a.Borrow, a.Refund, a.Total)
			fmt.Print("李四    ")
			fmt.Println(b.Borrow, b.Refund, b.Total)
			fmt.Print("homo    ")
			fmt.Println(c.Borrow, c.Refund, c.Total)

		case "6":
			loop = false

		default:
			fmt.Println("您的输入不正确，请按提示输入正确的选项..")
		}
		if !loop {
			fmt.Println("您确定要退出么？" + "请输入y/n")
			judge := ""
			fmt.Scanln(&judge)
			switch judge {
			case "y":
				fmt.Println("您已退出......")
				break

			case "n":
				continue
			}

			break
		}

		defer fmt.Println("首次借款后，下次可还款存入")
	}

}
