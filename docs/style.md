# Grow a Garden Calculator - 设计系统规范

## 设计理念
结合Apple的简洁优雅、Google的Material Design和Roblox的游戏化风格，打造现代化、有趣且专业的用户体验。

## 色彩系统

### 主色调
- **主绿色**: `#10B981` (emerald-500) - 代表生长和活力
- **深绿色**: `#059669` (emerald-600) - 用于强调和悬停状态
- **浅绿色**: `#D1FAE5` (emerald-100) - 背景和卡片
- **极浅绿色**: `#ECFDF5` (emerald-50) - 大面积背景

### 辅助色彩
- **橙色**: `#F59E0B` (amber-500) - 用于重要按钮和强调
- **蓝色**: `#3B82F6` (blue-500) - 链接和信息提示
- **紫色**: `#8B5CF6` (violet-500) - 特殊功能和游戏元素
- **粉色**: `#EC4899` (pink-500) - Roblox风格的点缀色

### 中性色
- **深灰**: `#1F2937` (gray-800) - 主要文本
- **中灰**: `#6B7280` (gray-500) - 次要文本
- **浅灰**: `#F9FAFB` (gray-50) - 背景

## 排版系统

### 字体层级
- **超大标题**: `text-4xl md:text-5xl font-black` - 主标题
- **大标题**: `text-2xl md:text-3xl font-bold` - 章节标题
- **中标题**: `text-lg md:text-xl font-semibold` - 子标题
- **正文**: `text-sm md:text-base` - 正常文本
- **小字**: `text-xs md:text-sm` - 辅助信息

### 字重
- **Black (900)**: 主要标题和品牌名称
- **Bold (700)**: 重要标题和按钮
- **Semibold (600)**: 子标题
- **Medium (500)**: 强调文本
- **Regular (400)**: 正文

## 间距系统

### 垂直间距
- **超大间距**: `mt-32` (128px) - 主要章节间
- **大间距**: `mt-16` (64px) - 子章节间
- **中间距**: `mt-8` (32px) - 元素组间
- **小间距**: `mt-4` (16px) - 相关元素间
- **微间距**: `mt-2` (8px) - 紧密相关元素

### 内边距
- **大内边距**: `p-8` - 主要容器
- **中内边距**: `p-6` - 卡片和组件
- **小内边距**: `p-4` - 按钮和小组件

## 组件设计规范

### 按钮设计
```css
/* 主要按钮 */
.btn-primary {
  @apply bg-gradient-to-r from-emerald-500 to-emerald-600 hover:from-emerald-600 hover:to-emerald-700 
         text-white font-semibold py-3 px-6 rounded-xl shadow-lg hover:shadow-xl 
         transform hover:scale-105 transition-all duration-300;
}

/* 次要按钮 */
.btn-secondary {
  @apply bg-white border-2 border-emerald-500 text-emerald-600 hover:bg-emerald-50 
         font-semibold py-3 px-6 rounded-xl shadow-md hover:shadow-lg 
         transform hover:scale-105 transition-all duration-300;
}

/* 游戏风格按钮 */
.btn-game {
  @apply bg-gradient-to-r from-purple-500 to-pink-500 hover:from-purple-600 hover:to-pink-600 
         text-white font-bold py-4 px-8 rounded-2xl shadow-xl hover:shadow-2xl 
         transform hover:scale-110 transition-all duration-300 border-4 border-white;
}
```

### 卡片设计
```css
.card {
  @apply bg-white rounded-2xl shadow-lg hover:shadow-xl p-6 
         border border-gray-100 transform hover:scale-105 transition-all duration-300;
}

.card-game {
  @apply bg-gradient-to-br from-emerald-50 to-blue-50 rounded-3xl shadow-xl p-8 
         border-2 border-emerald-200 transform hover:scale-105 transition-all duration-300
         relative overflow-hidden;
}
```

### 输入框设计
```css
.input {
  @apply w-full px-4 py-3 bg-white border-2 border-gray-200 rounded-xl 
         focus:border-emerald-500 focus:ring-4 focus:ring-emerald-100 
         transition-all duration-300 text-gray-800;
}

.select {
  @apply w-full px-4 py-3 bg-white border-2 border-gray-200 rounded-xl 
         focus:border-emerald-500 focus:ring-4 focus:ring-emerald-100 
         transition-all duration-300 text-gray-800 cursor-pointer;
}
```

## 动画和交互

### 悬停效果
- **缩放**: `hover:scale-105` - 卡片和按钮
- **阴影**: `hover:shadow-xl` - 提升层次感
- **颜色过渡**: `transition-colors duration-300` - 平滑颜色变化

### 过渡动画
- **标准过渡**: `transition-all duration-300` - 大多数交互
- **快速过渡**: `transition-all duration-200` - 小元素
- **慢速过渡**: `transition-all duration-500` - 大型变化

### 游戏化元素
- **弹跳动画**: `animate-bounce` - 重要提示
- **脉冲动画**: `animate-pulse` - 加载状态
- **渐变动画**: `animate-gradient-x` - 背景效果

## 响应式设计

### 断点策略
- **移动端**: `< 768px` - 单列布局，大按钮
- **平板**: `768px - 1024px` - 两列布局
- **桌面**: `> 1024px` - 多列布局，更多细节

### 移动端优化
- 增大触摸目标 (最小44px)
- 简化导航
- 优化字体大小
- 减少动画复杂度

## Roblox游戏风格元素

### 视觉特征
- **圆角设计**: 大量使用 `rounded-xl`, `rounded-2xl`, `rounded-3xl`
- **渐变背景**: 多彩渐变营造游戏氛围
- **阴影层次**: 丰富的阴影效果增加立体感
- **鲜艳配色**: 使用明亮、饱和的颜色

### 游戏化UI元素
- **进度条**: 彩色渐变进度指示器
- **徽章**: 圆形或六边形的成就标识
- **按钮**: 3D效果的游戏按钮
- **图标**: 卡通风格的矢量图标

## 可访问性

### 颜色对比
- 确保文本与背景对比度至少4.5:1
- 重要信息不仅依赖颜色传达

### 键盘导航
- 所有交互元素支持键盘访问
- 清晰的焦点指示器

### 屏幕阅读器
- 语义化HTML结构
- 适当的ARIA标签

## 性能优化

### 图片优化
- 使用WebP格式
- 响应式图片
- 懒加载非关键图片

### CSS优化
- 使用Tailwind的purge功能
- 最小化自定义CSS
- 优化动画性能

## 品牌一致性

### Logo使用
- 保持足够的留白空间
- 不要拉伸或变形
- 在深色背景上使用白色版本

### 语调
- 友好、专业、有趣
- 使用游戏术语但保持清晰
- 避免过于技术性的语言 