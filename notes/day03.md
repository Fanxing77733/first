枚举，aop等还需细究
公共字段填充，如创建人创建时间这些可以复用的东西
可以使用aop
使用aop包含自定义注解，aop类
自定义注解用来识别需要aop的方法
aop类里面包括各种通知等


第二天，研究了一下代码，研究了反射
比如getDeclaredFields()来说
Declared指拿到所有的,包括私有变量，但是是只能看到，不能使用，使用得暴力反射
没有Declared指拿到public的
有s指拿到所有
没有s拿到单个

暴力反射就是指将权限设为true，就可以访问私有的成员变量setAccessible(true)

拿外卖的反射来理解
Method setCreateTime = entity.getClass().getDeclaredMethod("setCreateTime", LocalDateTime.class);
setCreateTime.invoke(entity, now);

Method和invoke是一对的。METHOD拿到方法和传参类型，invoke是传参实现
entity.getClass() 获取字节码文件用于反射
("setCreateTime", LocalDateTime.lass)前者是方法名，后者是数据类型.class,表示拿到该类型的一个数据对象


