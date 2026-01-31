# MTC Online 師資班 - GitHub Pages 部署指南

## 📋 部署前檢查清單

### ✅ 已完成的準備工作
- [x] 主導航頁面 (`index.html`)
- [x] 6個獨立的lesson頁面（`pages/lesson1-6.html`）
- [x] 所有React組件使用CDN版本（無需編譯）
- [x] 移除Firebase依賴（改用純前端實現）
- [x] 所有頁面都有「返回主頁」按鈕

### 📦 需要上傳的文件
```
VOC teaching/
├── index.html
└── pages/
    ├── lesson1.html
    ├── lesson2.html
    ├── lesson3.html
    ├── lesson4.html
    ├── lesson5.html
    └── lesson6.html
```

---

## 🚀 部署步驟

### 步驟1：初始化Git倉庫

在項目文件夾中打開 PowerShell，執行以下命令：

```powershell
# 切換到項目目錄
cd "d:\Users\user\Desktop\Vibe coding camp\VOC teaching"

# 初始化 Git 倉庫
git init

# 添加所有需要的文件
git add index.html
git add pages/

# 提交到本地倉庫
git commit -m "Initial commit: MTC Online 師資班教學網站"
```

---

### 步驟2：在GitHub創建新倉庫

1. **登入 GitHub**
   - 前往 https://github.com
   - 使用 **newwineteach** 帳號登入

2. **創建新倉庫**
   - 點擊右上角的 `+` → `New repository`
   - Repository name: `mtc-vocabulary-teaching`（或您喜歡的名稱）
   - Description: `MTC Online 第47期師資班 - 詞彙教學互動課程`
   - 選擇 `Public`（公開）
   - **不要**勾選 "Add a README file"
   - 點擊 `Create repository`

---

### 步驟3：連接本地倉庫到GitHub

複製GitHub提供的命令，並在PowerShell中執行：

```powershell
# 設置遠程倉庫（替換為您的實際倉庫URL）
git remote add origin https://github.com/newwineteach/mtc-vocabulary-teaching.git

# 推送到GitHub
git branch -M main
git push -u origin main
```

> **⚠️ 注意**：如果這是第一次從這台電腦推送到GitHub，可能需要輸入GitHub的用戶名和密碼（或Personal Access Token）。

---

### 步驟4：啟用GitHub Pages

1. 在GitHub倉庫頁面，點擊 `Settings`（設置）
2. 在左側菜單中找到 `Pages`
3. 在 **Source** 區域：
   - Branch: 選擇 `main`
   - Folder: 選擇 `/ (root)`
4. 點擊 `Save`（保存）
5. 等待幾分鐘，頁面會顯示網站的URL

---

### 步驟5：訪問網站

您的網站將會發布在：
```
https://newwineteach.github.io/mtc-vocabulary-teaching/
```

🎉 **完成！** 您的互動教學網站現在已經上線！

---

## 🔧 後續更新方法

如果您需要修改網站內容，使用以下命令：

```powershell
# 1. 修改文件後，添加更改
git add .

# 2. 提交更改
git commit -m "描述您做的修改"

# 3. 推送到GitHub
git push
```

等待幾分鐘，GitHub Pages會自動更新網站。

---

## 📱 測試所有功能

部署成功後，請測試以下內容：

- [ ] 主頁面正常顯示所有6個單元卡片
- [ ] 每個卡片的連結都能正確跳轉
- [ ] Lesson 1: VARK測試可以正常運行
- [ ] Lesson 2: 卡牌遊戲可以拖曳（單機版）
- [ ] Lesson 3: Flashcards可以翻卡和切換
- [ ] Lesson 4: 分類遊戲可以拖曳卡片
- [ ] Lesson 5: 近義詞測驗可以答題
- [ ] Lesson 6: Matrix測驗可以完成
- [ ] 所有頁面的「返回主頁」按鈕都能正常工作
- [ ] 手機瀏覽器也能正常使用

---

## 🎨 自定義網站

### 修改網站標題
編輯 `index.html` 第44-47行：
```html
<h1 class="font-bangers text-4xl md:text-6xl...">
    MTC ONLINE  <!-- 可修改此處 -->
</h1>
<h2 class="text-2xl md:text-3xl font-bold...">
    第47期師資班 - 詞彙教學  <!-- 可修改此處 -->
</h2>
```

### 修改主題顏色
主頁面使用的漸層背景在 `<body>` 標籤：
```html
<body class="pop-dots">
    <!-- background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); -->
```

---

## ❓ 常見問題

### Q1: 為什麼Lesson 2和Lesson 4沒有多人協作功能？
**A:** 為了簡化部署，我移除了Firebase依賴。這些頁面現在是純前端版本，適合單人使用或課堂演示。

### Q2: 我可以添加多人協作功能嗎？
**A:** 可以！需要：
1. 註冊Firebase帳號
2. 創建Firebase項目
3. 獲取配置信息
4. 修改對應的lesson頁面代碼

### Q3: 手機上顯示不正常怎麼辦？
**A:** 所有頁面都使用了響應式設計（Tailwind CSS），但部分複雜互動（如拖曳）在手機上體驗可能不同。建議在平板或電腦上使用。

### Q4: 可以自定義域名嗎？
**A:** 可以！在GitHub Pages設置中添加自定義域名（Custom domain）。

---

## 📧 技術支持

如果遇到問題，請檢查：
1. GitHub倉庫是否設置為Public
2. GitHub Pages是否已啟用
3. 瀏覽器控制台是否有錯誤訊息
4. 文件路徑是否正確（所有lesson頁面都在pages文件夾中）

---

## 🎓 使用建議

### 課堂使用
1. **投影展示**：使用主頁面作為課程導航
2. **學生練習**：分享網站鏈接給學生課後練習
3. **翻轉教學**：讓學生先完成測驗，課堂討論結果

### 教學順序建議
1. Lesson 1: 了解學生學習風格
2. Lesson 3: 複習基礎概念
3. Lesson 4: 區分各級詞彙特徵
4. Lesson 5: 練習近義詞辨析
5. Lesson 2: 互動遊戲鞏固
6. Lesson 6: 總結測驗評估

---

**祝您教學順利！** 🚀

最後更新：2026-01-31
版本：v1.0
