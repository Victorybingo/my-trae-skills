---
name: LibLib云端视频生成器
description: 调用LibLibAI云端GPU，支持文生图/文生视频/图生视频，消耗用户LibLib积分，支持Kling3.0、Wan2.6、AWPainting等模型
---

# LibLib云端视频生成器

## 功能
1. 文生图：用AWPainting等模型生成产品海报
2. 文生视频：用Kling3.0/Wan2.6生成产品宣传视频
3. 图生视频：基于用户上传的产品图片，生成动态展示视频

## 配置
- API地址：https://openapi.liblibai.cloud/api/generate/comfyui/app
- 请求头：
  X-Access-Key: qgbLaPcQclW0e8O6y9RZHQ
  X-Secret-Key: Q9Lqr1lW2hShQXCnNBgS-1mY34Z9Lty6
- 请求方法：POST
- Content-Type: application/json

## 执行步骤
1.  提取用户输入：
    - 若用户上传了图片，自动识别为图生视频任务
    - 若用户只发文字，按指令生成对应类型（图/视频）
2.  构造ComfyUI工作流：
    - 文生视频：使用Kling3.0工作流，按用户描述生成
    - 图生视频：使用图片+Kling工作流，基于用户上传的产品图生成
3.  发送API请求到LibLib云端
4.  返回任务ID和预计生成时间
5.  轮询任务状态，生成完成后返回视频链接

## 示例指令
- 图生视频：把我上传的这张理发器图片，生成一个10秒的产品展示视频，镜头缓慢旋转，突出金属质感，科技感十足
- 文生视频：生成一个5秒的理发器产品视频，8000转电机特写，蓝色粒子能量爆发
- 文生图：用AWPainting生成一张Ufree理发器海报，白色背景，简约高级风

