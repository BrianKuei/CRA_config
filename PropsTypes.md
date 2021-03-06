```jsx
React.PropTypes.array           // 陣列

React.PropTypes.bool.isRequired // Boolean 且必要。

React.PropTypes.func            // 函式

React.PropTypes.number          // 數字

React.PropTypes.object          // 物件

React.PropTypes.string          // 字串

React.PropTypes.node            // 任何類型的: numbers, strings, elements 或者任何這種類型的陣列

React.PropTypes.element         // React 元素

React.PropTypes.instanceOf(XXX) // 某種XXX類別的實體

React.PropTypes.oneOf(['foo', 'bar']) // 其中一個字串

React.PropTypes.oneOfType([React.PropTypes.string, React.PropTypes.array]) // 其中一種格式類型

React.PropTypes.arrayOf(React.PropTypes.string)  // 某種類型的陣列(字串類型)

React.PropTypes.objectOf(React.PropTypes.string) // 具有某種屬性類型的物件(字串類型)

React.PropTypes.shape({                          // 是否符合指定格式的物件

  color: React.PropTypes.string,
  fontSize: React.PropTypes.number
});
React.PropTypes.any.isRequired  // 可以是任何格式，且必要。


// 自定義格式(當不符合的時候，會顯示Error) 

// 不要用`console.warn` 或者 throw, 因為他在`oneOfType` 的情况下無效。


customPropType: function(props, propName, componentName) {
  if (!/^[0-9]/.test(props[propName])) {
    return new Error('Validation failed!');
  }
}

// 當父元件沒有提供props的屬性時，可以採用getDefaultProps，預設props屬性的方式，讓元件使用預設的設定值，確保有props帶入。

var ComponentWithDefaultProps = React.createClass({ 
    getDefaultProps : function () { 
        return {
                value : 'default value' 
              }; 
    }, 
    /* ... */ 
});
```
