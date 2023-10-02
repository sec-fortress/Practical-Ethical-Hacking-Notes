## **Overview**

`gowitness` is a website screenshot utility written in Golang, that uses Chrome Headless to generate screenshots of web interfaces using the command line.


## **Installation**

```bash
$ go mod init gowitness
$ go get -u gorm.io/gorm
$ go get -u github.com/sensepost/gowitness
```

If this doesn't work use **pimpmykali** with menu option **1 fix_missing**

## **General Usage**


```bash
$ gowitness single <website>
```

You should now see a **screenshots** folder created in the present working directory of where this tool was ran
#### **Example**

I screenshot [https://sec-fortress.github.io](https://sec-fortress,github.io) using this tool and here is the result


![](https://i.imgur.com/Z2hmysF.png)
