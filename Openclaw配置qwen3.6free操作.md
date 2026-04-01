![image-20260401224755022](C:\Users\le\AppData\Roaming\Typora\typora-user-images\image-20260401224755022.png)

![image-20260401231220013](C:\Users\le\AppData\Roaming\Typora\typora-user-images\image-20260401231220013.png)



###阿里在openrouter限时免费使用qwen/qwen3.6-plus-preview:free最新模型。以下是在Openclaw配置的操作步骤：

打开openrouter官网创建账户后点击API Keys

![image-20260401225257804](C:\Users\le\AppData\Roaming\Typora\typora-user-images\image-20260401225257804.png)

点击Create按钮进行创建key,Name随便起，Credit limit不能为0随便一个大于0的数就行。创建完后及时复制key

如下图：

![image-20260401225507112](C:\Users\le\AppData\Roaming\Typora\typora-user-images\image-20260401225507112.png)

把key复制到openclaw.json配置中如果你已经有了一个openrouter的模型再在"env"里面添加key。

![image-20260401225905459](C:\Users\le\AppData\Roaming\Typora\typora-user-images\image-20260401225905459.png)

## **`models.providers.openrouter.models`**（添加 1 个新模型）

在原配置的 `models` 数组中添加了 Qwen 模型配置：

"openrouter": {
        "baseUrl": "https://openrouter.ai/api/v1",
        "api": "openai-completions",
        "models": [
          {
            "id": "xiaomi/mimo-v2-pro",
            "name": "Xiaomi MiMo V2 Pro (via OpenRouter)",
            "reasoning": true,
            "input": [
              "text"
            ],
            "cost": {
              "input": 0,
              "output": 0
            },
            "contextWindow": 1048576,
            "maxTokens": 32000
          },
          {
            "id": "qwen/qwen3.6-plus-preview:free",
            "name": "Qwen 3.6 Plus Preview (Free)",
            "reasoning": false,
            "input": [
              "text"
            ],
            "cost": {
              "input": 0,
              "output": 0
            },
            "contextWindow": 262144,
            "maxTokens": 65536
          }
        ]
      }
    }
  },







## **`agents.defaults.models`**（添加 1 个别名配置）

在原配置的 `models` 对象中添加了 Qwen 模型的别名：

"openrouter/qwen/qwen3.6-plus-preview:free": {
    "alias": "Qwen-Free"
}

-----------------------------------------

以下是我的配置仅供参考：  "agents": {
    "defaults": {
      "model": {
        "primary": "openrouter/qwen/qwen3.6-plus-preview:free"//我把qwen设置成默认模型
      },
      "models": {
        "deepseek/deepseek-chat": {
          "alias": "DeepSeek"
        },
        "xiaomi/mimo-v2-pro": {},
        "modelstudio/qwen3.5-plus": {
          "alias": "Qwen"
        },
        "openrouter/xiaomi/mimo-v2-pro": {
          "alias": "OpenRouter-MiMo"
        },
        "openrouter/qwen/qwen3.6-plus-preview:free": {
          "alias": "Qwen-Free"
        }
      },

