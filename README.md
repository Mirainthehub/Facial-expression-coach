# 🎭 表情训练教练 - 专业版

> AI驱动的专业表演训练系统，基于MediaPipe面部识别技术，提供影视镜头与舞台表演两种模式的表情训练。

[![Demo](https://img.shields.io/badge/🚀-Live%20Demo-blue)](https://your-username.github.io/Facial-expression-coach/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Privacy](https://img.shields.io/badge/🔒-本地计算-brightgreen)](README.md#隐私保护)

## ✨ 特色功能

### 🎬 双表演模式
- **影视镜头模式**: 适合近距离拍摄，注重表情细腻度和真实感
- **舞台表演模式**: 适合舞台演出，需要清晰可见的表情幅度

### 📊 专业四维评分系统
- **清晰度 (Clarity)**: 表情是否清晰可读
- **一致性 (Consistency)**: 面部各部位表情协调性
- **强度 (Intensity)**: 表情幅度是否合适
- **真实性 (Truth)**: 表情是否自然真实

### 🎯 个人化训练
- **Quick Calibrate**: 建立个人面部基线
- **渐进式训练**: 从简单到复杂的表情序列
- **实时反馈**: AI教练级专业指导建议

### 🔒 隐私保护
- **本地计算**: 所有处理在浏览器端完成
- **零上传**: 不上传任何图像或视频数据
- **即时处理**: 实时分析，无需联网

## 🚀 快速开始

### 在线体验
访问 [Live Demo](https://your-username.github.io/Facial-expression-coach/) 立即开始训练

### 本地运行
1. 克隆项目
```bash
git clone https://github.com/your-username/Facial-expression-coach.git
cd Facial-expression-coach
```

2. 启动本地服务器 (摄像头需要HTTPS或localhost)
```bash
# Python 3
python -m http.server 8000

# 或 Python 2
python -m SimpleHTTPServer 8000

# 或使用Node.js
npx serve .
```

3. 打开浏览器访问 `http://localhost:8000`

## 🎮 使用指南

### 第一步：选择表演模式
- 根据你的训练目标选择影视镜头或舞台表演模式
- 不同模式采用不同的评分标准和训练重点

### 第二步：摄像头设置
- 允许浏览器访问摄像头权限
- 确保光线充足，面部清晰可见
- 保持正面朝向，头部占据画面约1/3

###第三步：个人化校准
- 保持中性表情2秒钟
- 系统建立你的个人面部基线
- 提高后续评分的准确性

### 第四步：表情训练
跟随AI教练完成5种核心表情训练：
- 😊 **自然微笑**: 嘴角自然上扬，眼神温和
- 😄 **带眼笑**: 眼角微眯，嘴角上扬，真诚快乐
- 😮 **惊讶**: 张口瞪眼，眉毛上扬
- 😢 **悲伤**: 眉心内收，嘴角下垂
- 😠 **愤怒**: 眉毛压低，目光集中

### 第五步：查看结果
- 获得详细的四维评分
- 接收专业的表演指导建议
- 了解你的表演风格特点

## 🛠️ 技术架构

### 核心技术栈
- **前端**: 原生HTML5 + CSS3 + JavaScript (ES6+)
- **AI引擎**: Google MediaPipe FaceMesh
- **视觉处理**: Canvas 2D API
- **语音合成**: Web Speech API
- **构建方式**: 单文件应用，无需构建工具

### 关键算法
- **面部关键点检测**: 468个3D关键点实时追踪
- **表情特征提取**: 嘴部比例、眼部EAR、眉部活动度等7个核心指标
- **评分算法**: 基于模式差异化的综合评分系统
- **个人化校准**: 相对基线的动态评分调整

### 性能优化
- **实时处理**: 60fps面部识别
- **内存管理**: 滑动窗口数据缓冲
- **渲染优化**: requestAnimationFrame动画循环
- **响应式设计**: 适配各种屏幕尺寸

## 🎨 界面设计

### 设计理念
- **引导性**: 5步式向导流程，降低学习门槛
- **专业性**: 影视级UI设计，毛玻璃效果
- **互动性**: 实时动画反馈，庆祝效果
- **可访问性**: 清晰的视觉层次，直观的操作逻辑

### 视觉特色
- 🌟 渐变背景与毛玻璃效果
- 🎯 进度指示器与状态反馈
- 🎉 成就庆祝动画
- 📊 彩色评分卡片系统

## 🧪 表情识别原理

### MediaPipe FaceMesh
本项目基于Google MediaPipe的FaceMesh模型，提供468个高精度3D面部关键点：

```javascript
// 核心特征提取
const metrics = {
    mouthRatio: mouthWidth / mouthHeight,    // 嘴部宽高比
    eyeEAR: eyeAspectRatio,                  // 眼部纵横比  
    browActivity: eyeHeight - browHeight,     // 眉部活动度
    symMouth: 1 - abs(leftCorner.y - rightCorner.y), // 嘴部对称性
    // ... 更多指标
};
```

### 评分系统
```javascript
// 影视 vs 舞台模式差异化评分
const finalScore = {
    clarity: match * 0.7 + aesthetics * 0.3,
    consistency: stability * 0.8 + eyeMouthConsistency * 0.2,  
    intensity: amplitude * (mode === 'stage' ? 1.2 : 0.9),
    truth: detectFakeExpression(metrics, target)
};
```

## 📱 兼容性

### 浏览器支持
- ✅ Chrome 88+
- ✅ Firefox 78+
- ✅ Safari 14+
- ✅ Edge 88+

### 设备要求
- 📷 前置摄像头
- 💾 2GB+ RAM
- 🌐 现代浏览器
- 💡 充足光线环境

## 🤝 贡献指南

我们欢迎各种形式的贡献！

### 如何贡献
1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

### 贡献方向
- 🎭 新的表情类型和训练模式
- 🌍 多语言支持 (i18n)
- 📊 更丰富的数据可视化
- 🎨 UI/UX 改进
- 🐛 Bug 修复和性能优化
- 📚 文档完善

## 📄 开源协议

本项目采用 [MIT License](LICENSE) 开源协议。

## 🙏 致谢

- **Google MediaPipe Team**: 提供强大的面部识别技术
- **表演艺术界**: 专业的表情训练理论指导
- **开源社区**: 无私的技术分享和支持

## 📞 联系我们

- 🐛 **Bug报告**: [GitHub Issues](https://github.com/your-username/Facial-expression-coach/issues)
- 💡 **功能建议**: [GitHub Discussions](https://github.com/your-username/Facial-expression-coach/discussions)
- 📧 **商务合作**: your-email@example.com

## 🗺️ 发展路线图

### v1.0 当前版本 ✅
- [x] 基础表情识别与评分
- [x] 影视/舞台双模式
- [x] 个人化校准系统
- [x] 专业UI界面

### v2.0 计划中 🚧
- [ ] 表情序列训练 (微表情、情绪转换)
- [ ] 多人协作训练模式
- [ ] 训练数据导出与分析
- [ ] 移动端适配优化

### v3.0 愿景 🌟
- [ ] VR/AR 沉浸式训练
- [ ] AI导演模式 (场景化训练)
- [ ] 专业演员认证系统
- [ ] 表演学校定制版

---

<div align="center">

**⭐ 如果这个项目对你有帮助，请给个Star支持一下！**

Made with ❤️ by [Your Name](https://github.com/your-username)

</div>