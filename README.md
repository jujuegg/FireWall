# RJ FireWall

這是一個基於 Netfilter、Netlink 的 Linux L7 防火牆。

功能：
- [x] 按照來源 IP、目的 IP、埠號 (Port Number)，以及協定來過濾封包
- [x] 使用者可以新增、刪除、查看所有規則
- [x] 記錄封包過濾的日誌 (Log)，並可查看其內容
- [x] 連接狀態檢測
- [x] NAT

## 安裝

### 環境

環境為 Ubuntu 24.04，Linux Kernel 版本 6.8.0。

### 編譯與安裝

首先，下載程式碼並解壓縮：
```bash
unzip RJFireWall.zip

cd RJFireWall
```

**編譯**：
```bash
sudo make
```

**安装至 Linux 核心中**：
```bash
sudo make install
```

## 使用

在安裝的步驟中，已經將 module 載入至 Linux 核心，此时，只需使用應用程式 uapp 來對防火牆下命令即可控制其運作。

### 新增過濾規則：
```bash
./uapp rule add
```

### 刪除過濾規則：
```bash
./uapp rule del 要刪除的規則名稱
```

### 顯示已有規則：
```bash
./uapp ls rule
```

### 顯示所有過濾日誌：
```bash
./uapp ls log
```

### 顯示目前已有連接：
```bash
./uapp ls connect
```
