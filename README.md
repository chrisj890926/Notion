# GitHub 操作指南

## 1️⃣ 初始化 Git 儲存庫
### **本地初始化**
```bash
git init
```

### **添加遠端儲存庫**
```bash
git remote add origin <遠端儲存庫網址>
```

### **拉取遠端內容**
```bash
git pull origin main  # 或其他分支名稱
```

---

## 2️⃣ 日常開發工作
### **拉取最新變更**
```bash
git pull origin <your_branch_name>
```

### **添加與提交變更**
```bash
git add .
git commit -m "描述你的更改"
git push origin <your_branch_name>
```

### **解決合併衝突**
```bash
git pull
# 解決衝突後
git commit -m "解決衝突"
git push origin <your_branch_name>
```

---

## 3️⃣ 在隊友的分支上工作
### **克隆隊友的儲存庫**
```bash
git clone <隊友的儲存庫網址>
cd <專案名稱>
```

### **切換至隊友的分支**
```bash
git checkout <隊友的分支名稱>
```

---

## 4️⃣ 刪除檔案
### **從 Git 刪除檔案**
```bash
git status  # 檢查變更

git add -A
git commit -m "刪除檔案"
git push origin <your_branch_name>
```

---

## 5️⃣ 更改遠端儲存庫 URL
```bash
git remote -v  # 查看目前設定的 URL
git remote set-url origin <新的儲存庫網址>
git pull origin <your_branch_name>
git push origin <your_branch_name>
```

---

## 6️⃣ 覆蓋當前資料夾
```bash
git remote remove origin

git clone <新的儲存庫網址>
cd <專案名稱>

git checkout <branch_name>
git rm -r *
git add .
git commit -m "清除當前內容"
git push origin <branch_name> --force
```

---

## 7️⃣ 更改分支名稱
```bash
git branch -d <舊分支名稱>
git branch -m <新分支名稱>
```

---

## 8️⃣ 拉取隊友的資料
```bash
git checkout main
git pull origin main
git merge origin/main  # 若遇到歷史衝突

git merge origin/main --allow-unrelated-histories
```

---

# **📌 VSCode 終端機安裝指南**

## **建立與啟動環境**
```bash
conda create -n yolov8_env python=3.9
conda activate yolov8_env
```

## **安裝所需套件**
```bash
pip install ultralytics opencv-python
pip install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/mps
```

## **添加 Jupyter Kernel**
```bash
conda install -n yolov8_env ipykernel
```

---

# **📌 GitHub 大檔案處理**

## **使用 `.gitignore` 排除大檔案**
在專案根目錄建立 `.gitignore`，加入以下內容來排除特定大檔案：
```bash
# 排除模型檔案
A4/checkpoints/*.pth
```

## **檢查專案中大於 50MB 的檔案**
### **Windows PowerShell**
```powershell
Get-ChildItem -Path . -Recurse | Where-Object { $_.Length -gt 50MB }
```

### **Bash（Linux/macOS）**
```bash
find . -type f -size +50M
```

## **設定 Git 以避免自動轉換換行字元**
```bash
git config --global core.autocrlf false
```

---

這份 README 文件包含 GitHub 操作的核心內容、VSCode 環境設置，以及大檔案管理技巧，確保你在開發時能夠高效運行！🚀
