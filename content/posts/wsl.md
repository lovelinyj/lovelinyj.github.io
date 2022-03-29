---
title: "Windows 子系統 Linux 版 (WSL)"
date: 2022-03-28T15:20:05+08:00
type: post
---

# Windows subsystem Linux (WSL) 
 可讓開發人員直接在未修改的 Windows 上執行 GNU/Linux 環境（包括大部分的命令列工具、公用程式和應用程式），而不會產生傳統虛擬機器或雙重開機安裝的額外負荷。

適用於 Linux 的 Windows 子系統可讓開發人員執行 GNU/Linux 環境 (包括大部分的命令列工具、公用程式和應用程式)，直接在 Windows 上執行，不需進行修改，不會造成傳統虛擬機器或 dualboot 設定的額外負荷。

[Windows Docs](https://docs.microsoft.com/zh-tw/windows/wsl/)

# WSL vs WSL2  
> 從WSL更新到WSL2的主要原因：  
>> 1. 增加檔案系統效能  
>> 2. 支援完整系統呼叫相容性

## 比較功能
|功能|WSL 1|WSL 2
| -- | -- | --
Windows 和 Linux 之間的整合|	✅|	✅
快速開機時間	|✅|	✅
相較于傳統虛擬機器的小型 resource 墊腳列印|	✅|	✅
以最新版的 VMware 和 VirtualBox 執行	|✅	|✅
受控 VM|	❌	|✅
完整的 Linux 核心	|❌	|✅
完整的系統呼叫相容性	|❌	|✅
OS 檔案系統之間的效能	|✅	|❌


# 安裝WSL  
## 必要條件  
必須執行 Windows 10 2004 版和更高版本 (組建19041和更新版本的) 或 Windows 11。  
> 查詢windows版本和組建編號：  
> 1. 請選取Windows 標誌鍵 + R
> 2. 輸入`winver`，然後選取[確定]。  
>  
>  
> 您可以選取 [開始設定 ]Windows Update檢查更新，以更新至最新的 Windows 版本。

## 安裝
您現在可以在系統管理員 PowerShell 或 Windows 命令提示字元中輸入此命令，然後重新開機電腦，安裝執行 Windows 子系統 Linux 版 (WSL) 所需的所有專案。
> `wsl --install`

## 變更已安裝的預設 Linux 發行版本
根據預設，已安裝的 Linux 散發套件會是 Ubuntu。 這可以使用 `-d`旗標來變更。

> 若要變更已安裝的散發套件，請輸入： `wsl --install -d <Distribution Name>` 。   
> 以您要安裝的散發名稱取代 <Distribution Name> 。  
> 若要查看可透過線上商店下載的可用 Linux 發行版本清單，請輸入： `wsl --list --online` 或 `wsl -l -o` 。  
> 若要在初始安裝之後安裝額外的 Linux 發行版本，您也可以使用命令： wsl --install -d <Distribution Name> 。

# WSL的基本命令  
下列 WSL 命令會以 PowerShell 或 Windows 命令提示字元所支援的格式列出。 若要從 Bash/Linux 散發命令列執行這些命令，您必須將取代 wsl 為 wsl.exe 。
## 安裝
> `wsl --install`
## 安裝特定的 Linux 發行版本  
> `wsl --install --distribution <Distribution Name>`  
指定要安裝的 Linux 發行版本，除了預設 (Ubuntu) ，取代 < Distribution Name > 為散發的名稱。  
> 此命令也可以輸入為： wsl -d < Distribution Name > 。  

## 列出可用的 Linux 發行版本
> `wsl --list --online`  
查看可透過線上商店取得的 Linux 發行版本清單。 此命令也可以輸入為： wsl -l -o 

## 列出已安裝的 Linux 發行版本
> `wsl --list --verbose`  
查看 Windows 電腦上所安裝的 Linux 發行版本清單，包括 (是否正在執行或) 停止散發的狀態，以及執行散發的 WSL 版本 (WSL 1 或 WSL 2) 。  
 比較 WSL 1 和 WSL 2。 此命令也可以輸入為： `wsl -l -v` 。  
 可與 list 命令搭配使用的其他選項包括： --all 要列出所有散發套件、 --running 只列出目前執行中的發行版本，或 --quiet 只列出發佈名稱。

## 將 WSL 版本設定為1或2
> `wsl --set-default-version <Version>`  
若要設定 WSL 1 或 WSL 2 的預設版本，請以數位1或2取代 <Version> ，以代表您想要在新的 Linux 發行版本安裝上安裝的預設 WSL 版本。 例如： wsl --set-default-version 2 。 比較 WSL 1 和 WSL 2。

## 設定預設的 Linux 散發套件
> `wsl --set-default <Distribution Name>`  
若要設定 WSL 命令將用來執行的預設 Linux 發行版本，請將取代 <Distribution Name> 為您慣用的 linux 發行版本的名稱。

## 將目錄變更為首頁
> `wsl ~`  
`~`可以與 `wsl` 搭配使用，以從使用者的主目錄啟動。  
 若要在 WSL 命令提示字元中，從任何目錄回復至首頁，您可以使用命令： `cd ~` 。
 
## 更新 WSL
> `wsl --update`  
手動更新 WSL Linux 核心的版本。  
您也可以使用命令： `wsl --update rollback` 復原至舊版的 WSL Linux 核心。

## 檢查 WSL 狀態
> `wsl --status`  
查看 WSL 設定的一般資訊，例如預設的散發類型、預設散發和核心版本。

## 關機
> `wsl --shutdown`  
立即終止所有執行中的發行版本和 WSL 2 輕量公用程式虛擬機器。 需要您重新開機 WSL 2 虛擬機器環境的實例（例如 變更記憶體使用量限制 或對 wslconfig檔案進行變更）時，可能需要執行此命令。

## 取消註冊或卸載 Linux 發行版本  
> `wsl --unregister <DistributionName>`  
以目標 Linux 發行版本的名稱取代 < DistributionName > ，將會從 WSL 取消註冊該散發套件，以便重新安裝或清除該散發套件。  
謹慎：  
一旦取消註冊之後，與該散發相關聯的所有資料、設定和軟體將會永久遺失。 從 Microsoft Store 重新安裝將會安裝一份全新的散發套件。  
例如， wsl --unregister Ubuntu 會從 WSL 中可用的發行版本移除 Ubuntu。 wsl --list執行會顯示它已不再列出。  
您也可以在 Windows 電腦上卸載 Linux 發佈應用程式，就像任何其他存放區應用程式一樣。 若要重新安裝，請在 Microsoft Store 中尋找散發，然後選取 [啟動]。