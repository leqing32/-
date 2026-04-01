# -<img width="942" height="396" alt="image" src="https://github.com/user-attachments/assets/52a1d617-f1ce-4954-8416-60f77ad76ca1" />
##详细操作请看文档
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
