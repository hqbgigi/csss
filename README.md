# 组件说明

## 组件分支说明

* ##### 组件主分支为dev，在主项目里只需要拉取dev代码

  1. ###### 初次拉取组件执行：

     git subtree add --prefix=src/businessComponent http://192.168.1.231/custom-components/business-module.git dev

  2. ###### 组件代码有更新，在主项目里需要更新组件最新代码执行：

     git subtree pull --prefix=src/businessComponent http://192.168.1.231/custom-components/business-module.git dev
     注：需要合并到dev分支涉及的组件内容为通用的，如需额外增加不同的功能，需创建新的项目分支，在主项目里可以直接拉取新分支
     git subtree pull --prefix=src/businessComponent http://192.168.1.231/custom-components/business-module.git (xxxx分支名)


## 组件说明

1. ##### 组件文件夹命名需要具有语义性，分为页面级(功能级)、栏目级这三种。参考template文件夹

   ###### 1、页面级：以xxxPage命名。 类似于监控中心，命名以monitoringCenterPage为例；

   ###### 2、栏目级：以xxxColumn命名。 类似于大屏在线率，命名以screenOnlineRateColumn为例；

   ###### 3、一个组件一个文件夹，在文件夹下创建api文件夹，存放该组件需要涉及到的api.js文件;

   ###### 4、组件里的api使用：凡是读取组件里的api，在页面中使用以xxxComp。eg: api文件为device.js， 调用api为deviceComp去使用

2. ##### 组件文件的要求：

   ###### 1、组件的index.vue 页面的name命名以组件的命名一致；

   ###### 2、组件里的字段需要语义化，命名规范遵循驼峰格式，需要写注释；

   ##### 3、方法命名规则：

   ######   3.1、直接加载数据以load开头。eg: loadScreenData;

   ######   3.2、处理数据的方法以handle开头。 eg: handleRiverData;

   ######   3.3、获取数据的方法以get开头。 eg: getDict;

   ######   3.4、设置某个对象\值的方法以set开头。 eg: setColor;

   ##### 4、每个方法需要写注释，涉及传参，需要标明参数的类型和参数的来源。

     eg: loadRiverData(subjectCode)
      ' /**

      * @description 方法描述：获取该主题下的图层
        @param subjectCode: String  主题的code
            */'

        ##### 5、每个组件需要写说明文档：

        ######   5.1、版本号、负责人、时间；

        ######   5.2、组件的使用示例，包含传参和参数的类型；

        ######   5.3、接口描述：组件涉及到接口名称;

        ######   5.4、注释代码片段：打开vsc的设置-->用户代码片段 -->新建全局代码片段 --> 复制下面代码即可, @Author 需要改成自己的名字， func 是js文件函数的注释, descr 是文件的描述, func1 是vue页面的方法描述 ;

        ```
          {
              "Print to desc": {
                "scope": "javascript,typescript",
                "prefix": "descr",
                "body": [
                  "/*",
                  "* @Description: $0",
                  "* @Author: ",
                  " * @Date: $CURRENT_YEAR-$CURRENT_MONTH-$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND",
                  "* @LastEditTime: $CURRENT_YEAR-$CURRENT_MONTH-$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND",
                  "*/"
                ],
                "description": "注解"
              },
              "Print to func": {
                "scope": "javascript,typescript",
                "prefix": "func",
                "body": [
                  "/**",
                  " * @function: $1",
                  " * @desc: $2",
                  " * @param {$3} $4 $5",
                  " * @return {$6} $7",
                  " * @Author: ",
                  " * @Date: $CURRENT_YEAR-$CURRENT_MONTH-$CURRENT_DATE $CURRENT_HOUR:$CURRENT_MINUTE:$CURRENT_SECOND",
                  " */"
                ],
                "description": "注解"
              },
              "Print to func1": {
                "scope": "javascript,typescript",
                "prefix": "func1",
                "body": [
                  "/**",
                  " * @desc: $2",
                  " * @param {$3} $4 $5",
                  " */"
                ],
                "description": "注解"
              }
            }
        ```

        

      * 
