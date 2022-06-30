# API

## 全局配置

` Vue.config ` 是一个对象，包含Vue的全局配置。可以在启动应用之前修改下列property：



#### silent

* **类型**： ` boolean`

* **默认值**：`false`

* **用法**：

  ``` javascript
  Vue.conifg.silent = ture
  ```

  取消Vue所有的日志与警告。





#### optionMergeStrategies 

* **类型 **：`{[key: string]: Function}`

* **默认值** : `{}`

* **用法** :

  ```javascript
  Vue.config.optionMergeStrategies._my_option = function (parent, chlid, vm) {
      return chlid + 1
  }
  
  const Profile = Vue.extend({
      _my_option: 1
  })
  
  //Profile.options._my_option = 2
  ```

  自定义合并策略的选项。

  合并策略选项分别接受在父实例和子实例上定义的该选项的只作为第一个和第二个参数，Vue实例上下文被作为第三个参数传入。

* **参考[自定义选项的混入策略](https://www.baidu.com/)**



#### devtools

* **类型**: `boolean`

* **默认值**: `ture` (生产版为`flase`)

* **用法**:

  ```  javascript
  Vue.config.errorHandler = function(err,vm,info){
      // handle error
      // `info`是 Vue特定的错误信息，比如错误在生命周期钩子
      //旨在2.2.0+ 可用
  }
  ```

  指定组件的渲染和观察期间未捕获错误的处理函数。这个处理函数被调用时，可获取错误信息和Vue实例。

  > 从2.2.0起，这个钩子也会铺货组件生命周期钩子里的错误。同样的，当这个钩子是`undefined` 时，被捕获的错误会通过`console.error` 输出而避免应用崩溃。

