#jinja2
```
ansible 会将j2模板中用 {{ }} 引起来的变量填入值放到相应的位置
```
#GFW
```
使用ignore_errors子句跳过一些无关紧要的故障
```
#become
打开become就等于开启了sudo，不用时应该关掉：
```
become=False
```
#tasks之间的关系
```
在一条shell中cd过的路径不会传递给下一条task。
新的task还是会从$HOME目录开始
```
