使用注解前要在配置文件中加入`<context:annotation-config/>`,或者使用 `<context:component-scan base-package="pack.pack"/>`

这样后就会自动注册`AutowiredAnnotationBeanPostProcessor,CommonAnnotationBeanPostProcessor,PersistenceAnnotationBeanPostProcessor,RequiredAnnotationBeanPostProcessor`

然后才可在程序中使用`@Autowired,@Required`等



在配置文件中使用 context 命名空间之前，必须在 &lt;beans&gt;元素中声明 context 命名空间。

```
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/context
        http://www.springframework.org/schema/context/spring-context.xsd">
<context:annotation-config/>
</beans>
```



