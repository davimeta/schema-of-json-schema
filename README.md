# json-schema
JSON-schema,自带描述说明

## 使用说明

在vsCode环境下的示例

可参考本仓库的.vscode/settings.json 文件的项目配置, 指定解析json的schema映射

``` json
{
    "json.schemas": [
        {
            "fileMatch": [
                "/manifest.json"
            ],
            "url": "/manifest-schema.json"
        },
        {
            "fileMatch": [
                "/manifest-schema.json"
            ],
            "url": "/json-schema.json"
        }
    ]
}
```

本示例包含了三层映射

### json-schema.json采用官方约束

``` json
{
    "$schema": "http://json-schema.org/draft-07/schema#",
    ...
}
```

### manifest-schema.json的约束定义文档,采用json-schema约束,实现中文提示

``` json
{
    "json.schemas": [
        ...
        {
            "fileMatch": [
                "/manifest-schema.json"
            ],
            "url": "/json-schema.json"
        }
    ]
}
```

同时,注释掉了官方无注释说明的模式映射约束

``` json
{
    "//$schema": "https://json-schema.org/draft-07/schema#",
    ...
```

### manifest.json的约束定义文档,采用manifest-schema.json约束,并继续实现中文提示

``` json
{
    "json.schemas": [
        ...
        {
            "fileMatch": [
                "/manifest-schema.json"
            ],
            "url": "/json-schema.json"
        }
    ]
}
```
