Chart.js + Vue.js + BoxPlot Plot


main configuration needed for the `.mjs` files


```
vue.config.js
```

```js
// vue.config.js

module.exports = {
    configureWebpack: {
        module: {
            rules: [ // proper handle of .mjs files
                {
                    type: 'javascript/auto',
                    test: /\.mjs$/,
                    loader: 'babel-loader'
                }
            ]
        }
    }
};    

```