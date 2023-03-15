<a id="english"></a>
#### English ( [日本語](#japanese) )

## About iPLAss
iPLAss is a java-based enterprise class low-code web development platform, which have been focused on boosting the productivity of system development.  
MVC based framework with non-programming development mechanism ensure both Productivity and Customizability.

**<a href="https://iplass.org/en/" target="_blank">iPLAss Official Site</a>**

## Image
iPLAss docker image which has the Web server bundled with Tomcat and database bundled with MySQL, along with all necessary libraries packaged.

## Volume
`/var/lib/iplass` (IPLASS_HOME)  
The home directory for iPLAss, where the definition file suppose to be placed at.

`/var/lib/mysql`  
The data directory for MySQL.

## Booting

### Command to Start
	docker run -p 8080:8080 iplass/iplass-standalone

## How to use
Once the container was initiated, please access the following URL at your web browser.  
<a href="http://localhost:8080/iplass" target="_blank">http://localhost:8080/iplass</a>

For the guide after accessing the URL, please refer to iPLAss document site: <a href="https://iplass.org/en/docs/gettingstarted/gettingstarted/index.html#_installing_iplass" target="_blank">Install and Run</a>「4.iPLAss Installation」－「6.Access Tenant」and so on.  
Ahead of the link is in Japanese, the English version is under construction.

The following Tenant will be created in default.
- Tenant Name:'myTenant'
- Manager's user ID:'admin'
- Manager's password:'password'

To change the settings, please specify the followng environment variables.

## Environment Variables
Please specify the environment virables in needs.

- IPLASS_MYSQL_ROOT_PASSWORD  
Change MySQL's root user's password.  
Defualt:'root'

- IPLASS_DB_USER  
Specify the username of the database user for iPLAss.  
Defualt:'mtpusr'

- IPLASS_DB_PASSWORD  
Specify the password of the database user for iPLAss.  
Default:'mtpusr'

- IPLASS_TENANT_NAME  
Specify the tenant name for the intial tenant.  
Default:'myTenant'

- IPLASS_TENANT_ADMIN_ID  
Specify the initial tenant manager's user ID.  
Default:'admin'

  user ID have to be more than 4 characters, and only contains Enligh chacaters, numbers, and special character [-](minus)[@] [_] [.](period).

- IPLASS_TENANT_ADMIN_PASSWORD  
Specify the initial tenant manager's password.  
Default:'password'

  password have to be more than 6 characters and only contains English chacaters and numbers.

- IPLASS_BINARY_STORE_DIR  
Specify the directory to store the binary data files.  
Default:'file_lob_store'

  the root directory is IPLASS_HOME.

- TZ  
Specify the timezone for the system.  
Default:'Asia/Tokyo'

  for 3.0.9 or older versions, the timezone specified should be similar to the timezone by 「default-time-zone」 from $IPLASS_HOME/mysql.cnf

<a id="japanese"></a>
#### 日本語 ( [English](#english) )

## iPLAssについて
iPLAssとは、エンタープライズクラスのシステム開発における生産性向上を主目的とした、javaベースの開発プラットフォームです。  
MVCパターンベースの開発フレームワーク上にノンプログラミングでの開発を可能とする機能を提供し、高い生産性とカスタマイズ性を両立させます。

**<a href="https://iplass.org/" target="_blank">iPLAssオフィシャルサイト</a>**

## イメージ
WebサーバにTomcat、DBサーバにMySQLをバンドルし、iPLAssの動作に必要なアプリケーション及びライブラリをパッケージングしたiPLAssのDockerイメージです。

## ボリューム
`/var/lib/iplass` (IPLASS_HOME)  
iPLAssのホームディレクトリです。定義ファイルなどを配置します。

`/var/lib/mysql`  
MySQLのデータディレクトリです。

## 起動

### 起動コマンド
	docker run -p 8080:8080 iplass/iplass-standalone

## 使用方法
コンテナ起動後、Webブラウザで次のURLにアクセスしてください。  
<a href="http://localhost:8080/iplass" target="_blank">http://localhost:8080/iplass</a>

アクセス後の使用方法についてはiPLAssドキュメントサイトの<a href="https://iplass.org/docs/gettingstarted/gettingstarted/index.html#_iplassのインストール" target="_blank">Install and Run</a>「4.iPLAssのインストール」－「6.テナントへのアクセス」以降を参照してください。

デフォルトでは次の設定で初期テナントが作成されます。
- テナント名：'myTenant'
- 管理者ユーザID：'admin'
- 管理者パスワード：'password'

これらの設定を変更する場合は次の環境変数を指定してください。

## 環境変数
必要に応じて起動コマンドに次の環境変数を指定してください。

- IPLASS_MYSQL_ROOT_PASSWORD  
MySQLのrootユーザのパスワードを指定します。  
既定値：'root'

- IPLASS_DB_USER  
iPLAssのデータベースユーザのユーザ名を指定します。  
既定値：'mtpusr'

- IPLASS_DB_PASSWORD  
iPLAssのデータベースユーザのパスワードを指定します。  
既定値：'mtpusr'

- IPLASS_TENANT_NAME  
初期テナントのテナント名を指定します。  
既定値：'myTenant'

- IPLASS_TENANT_ADMIN_ID  
初期テナントの管理者ユーザIDを指定します。  
既定値：'admin'

  ユーザIDには4文字以上の「英数字」および「-」(マイナス)「@」「_」「.」(ピリオド)のみ入力可能です。

- IPLASS_TENANT_ADMIN_PASSWORD  
初期テナントの管理者パスワードを指定します。  
既定値：'password'

  パスワードには6文字以上の英数字のみ入力可能です。

- IPLASS_BINARY_STORE_DIR  
バイナリデータファイルの保存先ディレクトリを指定します。  
既定値：'file_lob_store'

  ルートディレクトリはIPLASS_HOMEになります。

- TZ  
システムのタイムゾーンを指定します。  
既定値：'Asia/Tokyo'

  3.0.9以前を利用の場合は指定したタイムゾーンと$IPLASS_HOME/mysql.cnfの「default-time-zone」で指定するタイムゾーンを一致させてください。