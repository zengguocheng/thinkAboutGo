## http.ResponseWriter 返回使用
> 在使用http.HandleFunc 方法的时候给接口w http.ResponseWriter 指定返回值时可以使用下列两种方法
### 1. fmt.Fprintf(w, "URL.Path = %q\n", r.URL.Path)
### 2. io.WriteString(w, "Hello World\n")

------
## 使用HTTP/2 协议
> 构建web服务器时，如果需要使用https协议需要把Http.ListenAndServe 更换成http.ListenAndServeTLS
> 使用方法为：http.ListenAndServeTLS(":10443", "cert.pem", "key.pem", nil)


------
## 生成pem 文件
### 1. openssl genrsa -out key.pem
### 2. openssl req -new -key key.pem -out cert.pem
### 3. openssl req -x509 -days 365 -key key.pem -in cert.pem -out certificate.pem




------
## 导入包
> 引入其他包时使用方法
### 1. 使用绝对路径  src 开始的整个路径 例如： github.com/change_sou/ch2/tempconv
### 2. 使用相对路径 例如: ./xxx
### 3. 给包指定别名  mytemp github.com/change_sou/ch2/tempconv



---------
## 文件分开处理
> 构建项目时main.go 文件中只做做简单的处理，把所有路由全部放在controller 包中，controller包通过调用model包 然后model 调用dao
