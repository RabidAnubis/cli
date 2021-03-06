---

copyright:

  years: 2015, 2018

lastupdated: "2018-08-31"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 開始使用 {{site.data.keyword.Bluemix_notm}} CLI
{: #overview}

在本指導教學中，您將安裝一組 {{site.data.keyword.Bluemix}} Developer Tools、驗證安裝，並配置您的環境。{{site.data.keyword.Bluemix}} Developer Tools 提供指令行方法，以建立、開發及部署端對端的 Web、行動及微服務應用程式。
{:shortdesc}

安裝之後，您會得到獨立式 {{site.data.keyword.Bluemix_notm}} CLI，以及下列工具：

* `Homebrew`（僅限 Mac）
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} 外掛程式
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} 外掛程式
* {{site.data.keyword.registrylong_notm}} 外掛程式
* {{site.data.keyword.containerlong_notm}} 外掛程式
* `sdk-gen` 外掛程式

## 開始之前
{: #prereq}

您需要 [{{site.data.keyword.Bluemix_notm}} 帳戶](https://console.bluemix.net/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 及下列系統需求：

* 如果您執行 Windows，則在您不是執行 Windows 10 Pro 的情況下，可能不支援部分功能。
* 您必須使用適用於 Docker 的穩定通道，而最低版本為 1.13.1。

## 步驟 1. 執行 install 指令
{: #step1}

* 若為 Mac 和 Linux，請執行下列指令：

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* 若為 Windows 10 Pro，請以管理者身分執行下列指令：

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

    在 Windows PowerShell 圖示上按一下滑鼠右鍵，然後選取**以系統管理員身分執行**。
  {: tip}

  您也可以從 [GitHub 儲存庫](https://github.com/IBM-Cloud/ibm-cloud-developer-tools)下載安裝程式 Script。

  如需手動安裝這些工具的步驟，請參閱[重新安裝工具](/docs/cli/ts_createapps.html#appendix)。

## 步驟 2. 驗證安裝
{: #step2}

若要驗證是否已順利安裝 CLI 及開發人員工具，請執行 `help` 指令：

```
ibmcloud dev help
```
{: codeblock}
<br>
輸出會列出用法指示、現行版本及支援的指令。

## 步驟 3. 配置環境
{: #step3}

1. 連接至 {{site.data.keyword.Bluemix_notm}} 地區中的 API 端點。例如，輸入下列指令以連接至 {{site.data.keyword.Bluemix_notm}} 美國南部地區：

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. 使用 IBM ID 登入 {{site.data.keyword.Bluemix_notm}}。

	```
	ibmcloud login
	```
	{: codeblock}
    <br>

	如果您的認證遭到拒絕，您可能是使用聯合 ID。如需詳細資料，請參閱[使用聯合 ID 進行登入](/docs/iam/login_fedid.html#federated_id)。
	{: tip}

3. 設定您的組織及空間。

	```
	ibmcloud target --cf
	```
	{: codeblock}

	您可以選擇性地使用來自上述指令的輸出，以下列指令手動設定您的組織及空間：

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## 後續步驟
{: #next-steps}

您現在已準備好開始開發及部署您的第一個應用程式！
