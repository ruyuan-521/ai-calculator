# 人工"智能"计算器

一个搞笑的网页计算器，模拟 AI 计算过程，实际上用手指数数来完成运算。

## 在线体验

👉 [calculator.yuanru.fun](http://calculator.yuanru.fun/ai-calculator.html)

## 功能特性

- **四则运算**：支持加（+）、减（-）、乘（×）、除（÷）
- **三阶段数数动画**：
  1. 🔴 红橙色数第一个数字
  2. 🟣 蓝紫色数第二个数字（不重叠）
  3. 🟡 金黄色数最终结果（覆盖前两轮颜色）
- **手脚可视化**：用 SVG 绘制的双手双脚，共 20 个手指/脚趾
- **进度条动画**：模拟"AI 计算链路展开"的搞笑过程
- **手机适配**：支持 480px 和 360px 两档响应式布局

## 使用方法

1. 在输入框中输入算式，例如 `5+8=`
2. 点击"开始计算"或按回车键
3. 观看 AI 用手指/脚趾逐个数数的全过程

## 技术栈

- 纯 HTML + CSS + JavaScript，无任何依赖
- SVG 绘制手脚图形
- CSS 动画实现脉冲呼吸效果
- async/await 控制动画时序

## 部署

### Nginx 部署

```bash
# 克隆仓库
git clone https://github.com/ruyuan-521/ai-calculator.git /var/www/calculator

# 配置 Nginx
cat > /etc/nginx/sites-available/calculator.yourdomain.com << 'EOF'
server {
    listen 80;
    server_name calculator.yourdomain.com;
    root /var/www/calculator;
    index ai-calculator.html;
    location / {
        try_files $uri $uri/ /ai-calculator.html;
    }
}
EOF

ln -s /etc/nginx/sites-available/calculator.yourdomain.com /etc/nginx/sites-enabled/
nginx -t && systemctl reload nginx
```

### 更新代码

```bash
cd /var/www/calculator && git pull origin main
```

## 作者

渊
