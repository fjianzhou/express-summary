# express使用
- #### express项目生成工具  express-generator
    - express-generator 安装
        ```
            npm install -g  express-geneartor
        ```
    - express-generato 常用命令
        - --version 查看express-generate版本号
        ```
            express -version
        ```
        - -v,--view 设置生成的express项目使用什么模板引擎 (默认jade)
        ```
            express -v ejs | express --view=ejs
        ```
        - -c,--css 设置cssd预编译器 (less sass stylus) (默认css)
        ```
            express -c less | express --css=less
        ```


# express常用的三方插件
- lessMiddleware （编译less文件=> css文件）
- path-to-regexp  (path转换成regexp)

# express 错误处理
- 定义错误处理中间件和定义其他中间件一样
    ```
    app.use(function(err, req, res, next) {
        console.error(err.stack);
        res.status(500).send('Something broke!');
    });
    ```
# exprss 404页面处理
- 在其所有他中间件的后面添加一个处理 404 的中间件
    ```
        app.use(function(req, res, next) {
            res.status(404).send('Sorry cant find that!');
        });
    ```

# 路由
- 路由是指如何定义应用的端点（URIs）以及如何响应客户端的请求。      


