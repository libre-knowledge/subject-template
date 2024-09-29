# 《自由知識協作平台》主題範本

快速創建風格一致的《自由知識協作平台》主題

<https://gitlab.com/libre-knowledge/gitlab-organization-templates/subject-template>  
[![GitLab CI 持續整合流程狀態標章](https://gitlab.com/libre-knowledge/gitlab-organization-templates/subject-template/badges/main/pipeline.svg?ignore_skipped=true "點擊查看 GitLab CI 持續整合流程的運行狀態")](https://gitlab.com/libre-knowledge/gitlab-organization-templates/subject-template/-/commits/main) [![「檢查專案中的潛在問題」GitHub Actions 作業流程狀態標章](https://github.com/libre-knowledge/subject-template/actions/workflows/check-potential-problems.yml/badge.svg "本專案使用 GitHub Actions 自動化檢查專案中的潛在問題")](https://github.com/libre-knowledge/subject-template/actions/workflows/check-potential-problems.yml) [![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white "本專案使用 pre-commit 檢查專案中的潛在問題")](https://github.com/pre-commit/pre-commit) [![REUSE 規範遵從狀態標章](https://api.reuse.software/badge/gitlab.com/libre-knowledge/gitlab-organization-templates/subject-template "本專案遵從 REUSE 規範降低軟體授權合規成本")](https://api.reuse.software/info/gitlab.com/libre-knowledge/gitlab-organization-templates/subject-template)

## 使用說明

本章節說明如何使用這個主題範本創建新的《自由知識協作平台》主題：

1. 確保已將要新增子主題之自由知識協作平台根/子主題專案的 Git 版控庫拓製至本地，且已拉取當前最新的修訂版
1. 開啟[自由知識協作平台 Libre Knowledge Collaboration Platform · GitLab](https://gitlab.com/libre-knowledge) 頁面
1. 點擊上側的「New project」藍色按鈕建立新的專案（目前本專案不支持使用 GitLab 的子群組架構，請一律將專案創建在最上層群組中）
    + 「Project name」欄位填入適當的主題標題（中文 + 英文）
    + 「Project slug」欄位填入適當的主題識別名稱（可以採用比較常見的英文縮寫）
    + 「Project deployment target (optional)」欄位下拉式選單選擇「Registry (package or container)」
    + 「Visibility Level」選擇「Public」
    + 「Project Configuration」區塊勾選「Initialize repository with a README」
1. 點擊新專案頁面左側欄的 Settings > General 選項開啟 General Settings 設定頁面，進行下列設定：
    + Topics
        - `自由知識協作平台 Libre Knowledge Collaboration Platform`
        - `自由知識協作平台主題 L.K.C.P. Topics`
    + Project description 欄位輸入主題適當的文字描述
1. 如果您有 GitHub 組織權限：
    1. 開啟[自由知識協作平台（鏡像用） Libre Knowledge Collaboration Platform(Mirrored)](https://github.com/libre-knowledge) 頁面
    1. 點擊中間右側的「New」綠色按鈕建立新的專案
    1. 「Repository name」欄位填入先前使用的主題識別名稱
    1. 「Description」欄位填入先前使用的主題文字描述
    1. 訪問權限單一選項提問選擇「Public」
    1. 點擊右下角的綠色「Create repository」按鈕創建專案
    1. 複製中間 Quick setup 區域的 HTTPS 協議的版控庫<ruby>拓製<rp>(</rp><rt>clone</rt><rp>)</rp></ruby>地址
    1. 於 GitLab 專案「Settings > Repository」頁面中的「Mirroring repositories」區塊中點擊右側的「Add new」按鈕新增新的鏡像版控庫
    1. 於「Git repository URL」欄位貼入剛剛複製的鏡像版控庫地址
    1. 於「Username」欄位貼入您的 GitHub 使用者名稱
    1. 於「Password」欄位貼入您的鏡像版控庫推送用 GitHub 個人存取用象徵物(Personal Access Token)
    1. 點擊下方的藍色「Mirror repository」按鈕保存鏡像版控庫設定
    1. 點擊新建立的鏡像版控庫設定右側的重新整理按鈕手動觸發鏡像程序
    1. 確認 GitHub 鏡像版控庫有被成功推送
    1. 於 GitHub 專案 > Settings > General > Features 面板移除下列預設啟用之專案功能：
        - Wikis
        - Issues
        - Projects
    1. 於 GitHub 專案 > About 面板進行下列設定：
        - 於 Website 欄位填入 GitLab 專案的網址
        - 於 Topics 欄位新增下列主題標籤：
            * `lkcp`
            * `lkcp-topics`
        - 於 Include in the home page 欄位將下列項目取消勾選
            * Packages
            * Deployments
1. 回到新建立之 GitLab 專案的主頁面，點擊頁面右側的藍色「Code」按鈕以獲取 Git 版控庫的拓製(clone)地址
1. 切換作業目錄至要新增該主題之「自由知識協作平台」根/子主題目錄
1. 執行下列命令將主題專案的 Git 版控庫以 Git 子模組的形式新增至本地先前已拓製到本地的「自由知識協作平台」：

    ```bash
    git submodule add \
        --name '_主題中文名稱_ _主題英文名稱_' \
        https://gitlab.com/libre-knowledge/_主題識別名稱_.git \
        '/path/to/自由知識協作平台 Libre Knowledge Collaboration Platform/_親主題路徑（如果有）_/_主題中文名稱_ _主題英文名稱_'
    ```

1. 編輯「自由知識協作平台 Libre Knowledge Collaboration Platform」主版控庫的 [.gitmodules 文件](https://gitlab.com/libre-knowledge/libre-knowledge/-/blob/main/.gitmodules)，合併新主題子模組下列 Git 子模組配置：

    ```ini
    [submodule "_主題中文名稱_ _主題英文名稱_"]
        ignore = dirty
    ```

1. 編輯託管版控庫的 README 文件，加入本主題的參照連結（GitLab 專案連結）與文字描述
1. 將本專案除下列以外專案文件複製到新的主題專案中：
    + README.md
    + .git
    + .gitattributes
    + .markdownlint.yml
1. （選用）於文字終端中切換作業目錄至新主題中後執行下列命令安裝 pre-commit 框架的配套 Git 提交前掛勾程序：

    ```bash
    pre-commit install
    ```

1. 編輯子模組專案 [real.README.md 主題說明文件模板](real.README.md)，將 `_佔位字_` 替換為適當之內容（別忘了替換 `libre-knowledge/_專案ID_`），並移除未使用之（待補）章節
1. 將 [real.markdownlint.yml Markdownlint 配置文件](real.markdownlint.yml)更名為「.markdownlint.yml」
1. 將 [real.gitattributes Git 路徑屬性配置文件](real.gitattributes)更名為「.gitattributes」
1. 將原始的 README.md 檔案使用 [real.README.md 主題說明文件模板](real.README.md) 替換
1. 執行下列命令（或等效操作）將範本用自定義授權條款移除：

    ```bash
    find_opts=(
        -type f
        -exec
            sed
                --in-place
                --regexp-extended
                --expression='s@ OR LicenseRef-Apache-2.0-If-Not-Used-In-Template-Projects@@g'
                {}
                ';'
    )
    find . "${find_opts[@]}"
    ```

1. 將變更提交為新修訂版（參考提交標題： `docs: 撰寫主題說明文件雛型`）
1. 將本地變更推送到遠端版控庫
1. 以下列修訂版提交訊息將自由知識協作平台根/子主題版控庫的變更提交為一新修訂版：

    ```git-commit-msg
    chore: 新增「_主題中文名稱_ _主題英文名稱_」主題
    ```

1. 切換作業目錄至「自由知識協作平台」主目錄
1. 執行下列命令將變更推送到遠端版控庫：

    ```bash
    git push
    ```

## 參考資料

本章節列舉開發本專案期間所參考的第三方資料：

* [Machine-readable debian/copyright file](https://www.debian.org/doc/packaging-manuals/copyright-format/1.0/)  
  說明 REUSE DEP5 檔案的撰寫格式
* [Tutorial: How to become REUSE-compliant \| REUSE](https://reuse.software/tutorial/)  
  說明如何使專案遵從 REUSE 規範
* [‎How to test whether a Debian package is installed in a shell script? | Google Bard](https://bard.google.com/share/21fb868d9e6f)  
  說明如何在 Shell 腳本中檢查特定 Debian 軟體包是否已安裝
* [‎How to verify whether the APT repository cache has been refreshed recently? | Google Bard](https://bard.google.com/share/8bb0ad0135b1)  
  說明如何檢查 APT 軟體庫本地快取是否近期有被刷新
* [Predefined variables reference | GitLab](https://docs.gitlab.com/ee/ci/variables/predefined_variables.html)  
  說明 GitLab CI 環境會設定的環境變數
* [gitlab CI example - Contributing - pre-commit documentation](https://pre-commit.com/#gitlab-ci-example)  
  說明如何於 GitLab CI 中配置 pre-commit 資源的快取以減少後續流水線所需的運行時間
* [Share caches between jobs in the same branch | Caching in GitLab CI/CD | GitLab](https://docs.gitlab.com/ee/ci/caching/index.html#share-caches-between-jobs-in-the-same-branch)  
  說明 GitLab CI 如何在同分支的同 CI 工作(job)間共享快取資料
* debconf(7) 的 manpage 使用手冊頁面  
  說明不同類型 debconf 前端界面的用途

---

本主題為[自由知識協作平台](https://gitlab.com/libre-knowledge/libre-knowledge)的一部分，除部份特別標註之經合理使用(fair use)原則使用的內容外允許公眾於授權範圍內自由使用

如有任何問題，歡迎於本主題的[議題追蹤系統](https://gitlab.com/libre-knowledge/gitlab-organization-templates/subject-template/-/issues)創建新議題反饋
