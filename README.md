---
title: 'Multipass - Ubuntu 虛擬機部署管理工具'
disqus: hackmd
---

Multipass 使用 - Ubuntu 虛擬機部署管理工具
===
## Table of Contents

[TOC]

## 安裝

```gherkin=
# Ubuntu
sudo snap install multipass

# Mac
brew install --cask multipass

# Windows
## 須先安裝 Hyper-V 或是 VirtualBox
## 再下載安裝檔 https://multipass.run/docs/install-multipass
```

## 基礎操作
```gherkin=
multipass find

multipass launch --name <vm-name> 22.04 --cpus 2 --memory 2G --disk 20G

# 啟動一個 minikube 
multipass launch minikube --memory 4G --disk 40G --cpus 2


multipass shell <vm-name>

multipass stop <vm-name>

multipass delete <vm-name>

multipass purge

multipass exec <vm-name> -- <command>

```
## 設定
### 查看設定
```gherkin=
multipass get local.<vm-name>.cpus
multipass get local.<vm-name>.disk
multipass get local.<vm-name>.memory
```
### 修改設定
```gherkin=
multipass stop <vm-name>
multipass set local.<vm-name>.cpus=4
multipass set local.<vm-name>.disk=60G
multipass set local.<vm-name>.memory=7G
```

### 檔案搬移
```gherkin=
multipass transfer <local-path> <vm-name>:.
multipass transfer <vm-name>:<vm-path> .
```

### 掛載與卸載資料夾
```gherkin=
multipass mount <local-path> <vm-name>:<vm-path>

multipass umount <vm-name>:<vm-path>
```

## 可用命令
> delete 刪除機器
> exec 在機器中執行命令
> find 列出可以安裝 ubuntu 版本 image
> get 獲取配置資訊
> help 查看幫助
> info 查看機器信息
> launch 創建並啟動機器
> list 列出所有機器
> mount 掛載文件夾到機器
> purge 清除已刪除的機器
> recover 恢復已刪除的機器
> restart 重啟機器
> set 設置某個配置
> shell 通過 shell 連接機器
> start 啟動機器
> stop 停止機器
> suspend 暫停機器
> transfer 在本機和機器之間傳輸檔案或文件
> umount 移除機器中掛載的文件夾
> version 查看版本

## Appendix and FAQ

:::info
**Find this document incomplete?** Leave a comment!
:::

###### tags: `Templates` `Documentation`
