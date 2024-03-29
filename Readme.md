##Joker

##Joker

![image-20220902160052965](https://image.perng.cn/image20220902160054.png)

### Version 1.0

### Introduction to tool principles

Use the **Http.sys** driver to operate urlacl. Since Http.sys is the basis of the IIS server, its priority is higher than that of IIS. It will not cause port bind conflicts and achieve the port taking effect. Since it is related to the external service port of the victim machine Similarly, it can achieve extremely high concealment. Because its effect after taking effect is very similar to the Joker in LOL, it was named Joker.

### Instructions

**The prerequisite for using this tool is the IIS environment with administrator rights**

#### 1. Reuse based on path

~~~powershell
Joker.exe "http://*:{PORT}/{PATH}"
~~~

![image-20220902160750422](https://image.perng.cn/image20220902160751.png)

You can directly use **Yi Jian** to connect, and the configuration is as follows:

![image-20220902161010316](https://image.perng.cn/image20220902161011.png)

​ *Fill in the connection password casually*

![image-20220902161210934](https://image.perng.cn/image20220902161212.png)

#### 2. Reuse based on HOST (strongly recommended)

~~~powershell
Joker.exe "http://{HOST}:{PORT}/"
~~~

![image-20220902161434903](https://image.perng.cn/image20220902161436.png)

Ant Sword configuration is as follows

![image-20220902161603406](https://image.perng.cn/image20220902161604.png)

![image-20220902161619869](https://image.perng.cn/image20220902161621.png)

**In this way, when port 80 is accessed normally, it is a normal business, and when port 80 is accessed with a special header, it is a backdoor program. **

 #### 3.Regeorg adaptation

Project JokerTunnel is an adapted version of Regeorg.

![image-20221107111636996](https://image.perng.cn/image-20221107111636996.png)

![image-20221107111724185](https://image.perng.cn/image-20221107111724185.png)

The client can use Regeorg to connect

### Secondary development

The handles of this project are concentrated in handle.h. Taking execution as an example, the incoming parameters are **Request body, RequestBody length and response content pointer**

![image-20220902162522544](https://image.perng.cn/image20220902162523.png)
