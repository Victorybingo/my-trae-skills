---
name: LibLib云端视频生成器
description: 调用LibLibAI云端GPU生成绘画和视频，支持Kling3.0、Wan2.6、AWPainting等所有模型，消耗用户LibLib积分
---

# LibLib云端视频生成器

## 功能
调用LibLibAI开放API，在云端GPU上生成高质量图片和视频，不消耗本地任何资源。

## 配置
- API地址：https://openapi.liblibai.cloud/api/generate/comfyui/app
- 请求头：
  X-Access-Key: qgbLaPcQclW0e8O6y9RZHQ
  X-Secret-Key: Q9Lqr1lW2hShQXCnNBgS-1mY34Z9Lty6
- 请求方法：POST
- Content-Type: application/json

## 执行步骤
1. 提取用户需求：类型(图/视频)、描述、时长(视频默认5秒)、分辨率(默认1080p)、模型(默认kling-3.0)
2. 构造标准ComfyUI工作流JSON
3. 发送POST请求提交任务
4. 返回任务ID和预计生成时间
5. 每30秒轮询一次任务状态
6. 生成完成后返回最终的图片/视频链接

## 示例指令
- 生成5秒产品视频：8000转高速电机特写，蓝色粒子能量爆发，机械线框
- 用AWPainting生成黑色理发器产品海报，白色背景
- 把这张图变成10秒视频，镜头缓慢旋转
