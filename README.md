# react-douban
react／react-router／redux／axios／ material-ui

#### css 模块化

```
```

#### less的添加

```
```

#### react-router 异步加载组件

```
import React, { Component } from 'react'

function AsyncComponent (importComponent) {
    return class AsyncRouterComponent extends Component {
        constructor (props) {
            super(props)
            this.state = {
                component: null
            }
        }

        async componentDidMount () {
            const { default: component } = await importComponent()
            this.setState({
                component: component
            })
        }

        render () {
            const component = { this.state }

            return (
                component ? <component {...this.props}/> : null
            )
        }
    }
}

export default AsyncComponent
```
