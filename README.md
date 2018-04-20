browser-sync start -s
nodeppt start -p 9091

title: getSelector
speaker: wangjianfeng
url: https://github.com/ksky521/nodePPT
transition: slide
[slide]
# getSelector
###### wangjianfeng

[slide]
# 如何通过node节点获取对应的selector {:&.flexbox.vleft}
[magic data-transition="circle"]
![/img1.png](/img1.png)
====
![/img2.png](/img2.png)
[/magic]

[slide]
# 获取selector的规则及优先级 {:&.flexbox.vleft}
1. 向上冒泡遇到*有id | body*节点 **停止查找** {:&.moveIn}
2. > *没有兄弟*节点（独生子）| 虽有兄弟节点但*nodeName唯一* 返回 **nodeName**
3. > 节点*有className且唯一* 返回 **className**
4. > 节点*有className但不唯一* 返回 **nth-child**
5. 其余情况 返回 **nth-child**
6. 回到第1步

[slide]
### *没有兄弟*节点（独生子）| 虽有兄弟节点但*nodeName唯一* 返回 **nodeName**
----
 ```html

  <div>
    <span>xxx</span>
  </div>

  <div>
    <span>xxx</span>
    <span>xxx</span>
    <a href=''>xxx</a>
  </div>
```

[slide]
### 节点*有className且唯一* 返回 **className**
----
 ```html

  <div>
    <span class='a'>xxx</span>
    <span class='b'>xxx</span>
    <a href=''>xxx</a>
  </div>
```

[slide]
### 节点*有className但不唯一* 返回 **nth-child**
----
 ```html

  <div>
    <span class='a'>xxx</span>
    <span class='a'>xxx</span>
    <a href=''>xxx</a>
  </div>

  <div>
    <span class='a b'>xxx</span>
    <span class='b a'>xxx</span>
    <a href=''>xxx</a>
  </div>

  <div>
    <span class='a'>xxx</span>
    <span class='b a'>xxx</span>
    <a href=''>xxx</a>
  </div>
```

[slide]
## 写一个自己的getSelector
----
demo：http://10.129.193.94:9091/index.html
----
Github：https://github.com/921/qa/blob/master/getselector.js

[slide]
#谢谢！
