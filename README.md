## 工厂模式
 - 工厂模式是一种创建对象的设计模式，它使用工厂方法来解决创建对象时需要某些条件或复杂操作的情况。
```
  /** 工厂模式 */

  class Jquery {
    selector = null
    constructor(selector) {
      this.selector = selector
      const els = document.querySelectorAll(selector)

      for(let i = 0; i < els.length; i++) {
        this[i] = els[i]
      }
      this.length = els.length
    }
    css() {
      /** ... ... */
      return this
    }
  }

  /** 工厂调用 */
  const $ = (selector) => {
    return new Jquery(selector)
  }
  /** 
   *  前端常用的工厂模式有
   *  1、Jquery 库
   *  2、react 创建 vdom 的方法 react.crateElement()
   *  3、vue 创建 vdom 的方法 
   */
```
## 单例模式
- 单例模式是一种创建型设计模式，它的目的是确保一个类只能实例化一个对象，并提供一个访问该对象的全局访问点。
```
 class Store {
    static instance = null

    createStore() {
      if(!this.instance) {
        this.instance = new Store()
      }
      return this.instance
    }

  }

  Store.createStore()
```