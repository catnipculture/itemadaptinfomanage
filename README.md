# itemadaptinfomanage
Java：192 基于SSM框架的失物招领信息管理系统
> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

系统有管理员，用户。

​

系统中的核心用户是管理员，管理员登录后，通过管理员功能来管理后台系统。主要功能有：首页、个人中心、用户管理、失物招领管理、物品类型管理、失物认领管理、物品挂失管理、寻物论坛、系统管理等功能。

用户包括：首页、个人中心、失物招领管理、失物认领管理、物品挂失管理、寻物论坛等功能。

**演示视频：**[**点击查看**](https://pan.baidu.com/s/1mZciwcyubYAW-G5BE8cL8Q?pwd=mxqv)

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

前端：vue

# 使用说明

1.使用Navicati或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)


# 运行截图

## 功能模块截图

![img](https://i-blog.csdnimg.cn/img_convert/4aa804661057004fb4a617d6d5789fc4.png)

![image20241222003328541](https://i-blog.csdnimg.cn/img_convert/2da481c989a1e9aea85ad688c537610d.png)

#### 项目截图

前台

![图片11](https://i-blog.csdnimg.cn/img_convert/a39a1fc4b9ae32ec84144cad340c2827.png)

![图片12](https://i-blog.csdnimg.cn/img_convert/f72e93d4151fa55e493b8497842e4dac.png)

后台

![图片6](https://i-blog.csdnimg.cn/img_convert/de0ebbe96642f51ae15fbe1036cafabc.png)

![图片7](https://i-blog.csdnimg.cn/img_convert/5f74197b5f2a12744a82aef7850be6c4.png)

![图片8](https://i-blog.csdnimg.cn/img_convert/066cd3477eb87c2925d281844fdb3dcc.png)

![图片9](https://i-blog.csdnimg.cn/img_convert/e1343e52163b78442a27bed0bf19613f.png)

![图片10](https://i-blog.csdnimg.cn/img_convert/0bc9fb8ba10cb906caf20ad0d54b61dd.png)

### 代码

```
  StringFilterPredicate filterPredicate = new StringFilterPredicate();
        filterPredicate.setOperation(StringFilterPredicate.StringOperation.IN);
        filterPredicate.setValue(new FilterPredicateValue<>(String.join(",", tenantNameList)));

        keyFilter.setPredicate(filterPredicate);
        keyFilters.add(keyFilter);

        // Prepare list of queried tenanat attributes
        List<EntityKey> attributes = List.of(
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.PROVINCE),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.CITY),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.CONTACT),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.TENANT_STATUS),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.DISTRICT),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.MODIFIER_ID),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.MODIFY_TIME),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.ADDRESS_DETAIL),
                new EntityKey(EntityKeyType.ATTRIBUTE, TenantConstants.DESCRIPTION)
        );

        // Prepare page link
        EntityDataPageLink entityDataPageLink = new EntityDataPageLink(tenantList.size(), 0, "", null);
        // Create entity query with provided entity filter, key filter, queried fields and page link
        EntityDataQuery dataQuery =
                new EntityDataQuery(typeFilter, entityDataPageLink, null, attributes, keyFilters);

        PageData<EntityData> entityPageData = client.findEntityDataByQuery(dataQuery);
```
