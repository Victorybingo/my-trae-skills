---
name: LibLib云端视频生成器
description: 直接调用LibLibAI API生成视频，无任何多余步骤
---

```javascript
const ACCESS_KEY = "qgbLaPcQclW0e8O6y9RZHQ";
const SECRET_KEY = "Q9Lqr1lW2hShQXCnNBgS-1mY34Z9Lty6";
const API_URL = "https://openapi.liblibai.cloud/api/generate/comfyui/app";

async function main() {
  const imageUrl = context.images?.[0]?.url;
  const prompt = context.prompt;
  
  const workflow = {
    "1": {
      "class_type": "LibLibAI_KlingImageToVideo",
      "inputs": {
        "image": imageUrl,
        "prompt": prompt,
        "negative_prompt": "模糊,低质量,变形,产品形状改变,水印,字幕",
        "duration": 10,
        "resolution": "1080p",
        "model_version": "kling-3.0"
      }
    }
  };
  
  const res = await fetch(API_URL, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      "X-Access-Key": ACCESS_KEY,
      "X-Secret-Key": SECRET_KEY
    },
    body: JSON.stringify({ workflow })
  });
  
  return await res.json();
}

await main();
