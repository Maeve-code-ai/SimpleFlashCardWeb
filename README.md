# Simple FlashCard Web

Simple FlashCard Web 是一个基于 React 和 TypeScript 的轻量级网页闪卡应用，帮助用户创建学习牌组、编写正反面卡片，并通过翻看卡片进行复习。应用目前以浏览器本地存储数据，无需注册账户或配置后端。

## 功能

- 创建牌组，并编辑牌组名称和描述。
- 在牌组中创建和查看正反面闪卡。
- 开始学习时查看卡片正面，点击后显示答案，再进入下一张。
- 根据卡片的下次复习时间筛选当前到期的卡片。
- 将牌组、卡片和复习记录保存在浏览器的 `localStorage` 中。
- 删除牌组时同时删除该牌组中的卡片及相关复习记录。

当前的复习间隔采用简单策略：完成复习后将卡片安排在约 24 小时后再次复习。应用尚未提供云端同步、用户账户、卡片编辑/删除、复杂间隔算法或学习统计功能。

## 技术栈

- React 18
- TypeScript
- Vite 5
- 浏览器 `localStorage`

## 本地运行

需要安装 Node.js 和 npm。

```bash
npm install
npm run dev
```

启动后，使用终端显示的本地地址在浏览器中打开应用。

## 其他命令

```bash
npm run build    # 构建生产版本
npm run preview  # 本地预览生产构建
```

## 项目结构

```text
src/
  components/
    CardEditor.tsx  # 闪卡创建表单
  lib/
    scheduler.ts    # 简单的复习时间安排
    storage.ts      # 牌组、卡片和复习记录的本地存储
  pages/
    Home.tsx        # 牌组列表和创建入口
    Deck.tsx        # 牌组详情、编辑和卡片创建
    Study.tsx       # 闪卡学习流程
  App.tsx           # 应用和哈希路由
  main.tsx          # React 应用入口
  styles.css        # 全局样式
```

## 数据与隐私

应用使用浏览器本地存储保存数据，不会通过本项目代码同步至云端。清除浏览器站点数据会移除保存在该浏览器中的牌组、卡片和复习记录。
