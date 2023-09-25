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
	docker run -p 8080:8080 ghcr.io/iplass/iplass-standalone

## How to use
Once the container was initiated, please access the following URL at your web browser.  
<a href="http://localhost:8080/iplass" target="_blank">http://localhost:8080/iplass</a>

For the guide after accessing the URL, please refer to iPLAss document site: <a href="https://iplass.org/en/docs/gettingstarted/gettingstarted/index.html#_installing_iplass" target="_blank">Install and Run</a>「4.iPLAss Installation」－「6.Access Tenant」and so on.  
Ahead of the link is in Japanese, the English version is under construction.

The following Tenant will be created in default.
- Tenant Name:'myTenant'
- Manager's user ID:'admin'
- Manager's password:'password'

To change the settings, please specify the following environment variables.

## Environment Variables
Please specify the environment variables in needs.

- IPLASS_MYSQL_ROOT_PASSWORD  
Change MySQL's root user's password.  
Default:'root'

- IPLASS_DB_USER  
Specify the username of the database user for iPLAss.  
Default:'mtpusr'

- IPLASS_DB_PASSWORD  
Specify the password of the database user for iPLAss.  
Default:'mtpusr'

- IPLASS_TENANT_NAME  
Specify the tenant name for the initial tenant.  
Default:'myTenant'

- IPLASS_TENANT_ADMIN_ID  
Specify the initial tenant manager's user ID.  
Default:'admin'

  user ID have to be more than 4 characters, and only contains English characters, numbers, and special character [-](minus)[@] [_] [.](period).

- IPLASS_TENANT_ADMIN_PASSWORD  
Specify the initial tenant manager's password.  
Default:'password'

  password have to be more than 6 characters and only contains English characters and numbers.

- IPLASS_BINARY_STORE_DIR  
Specify the directory to store the binary data files.  
Default:'file_lob_store'

  the root directory is IPLASS_HOME.

- TZ  
Specify the timezone for the system.  
Default:'Asia/Tokyo'

  for 3.0.9 or older versions, the timezone specified should be similar to the timezone by 「default-time-zone」 from $IPLASS_HOME/mysql.cnf

### 3.1.36 or later, 3.2.11 or later versions
If you are using 3.1.36 or later or 3.2.11 or later versions, the following environment variables are available.

- `TOMCAT_CONNECTOR_HTTP_PORT`  
  default value: `8080`  
  Set the `port` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.
- `TOMCAT_CONNECTOR_HTTP_CONNECTION_TIMEOUT`  
  default value: `20000`  
  Set the `connectionTimeout` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.
- `TOMCAT_CONNECTOR_HTTP_REDIRECT_PORT`  
  default value: `8443`  
  Set the `redirectPort` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.
- `TOMCAT_CONNECTOR_HTTP_MAX_PARAMETER_COUNT`  
  default value: `1000`  
  Set the `maxParameterCount` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.
- `TOMCAT_CONNECTOR_HTTP_PROXY_NAME`  
  default value: none  
  Set the `proxyName` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.
- `TOMCAT_CONNECTOR_HTTP_PROXY_PORT`  
  default value: none  
  Set the `proxyPort` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.
- `TOMCAT_CONNECTOR_HTTP_SCHEME`  
  default value: `http`  
  Set the `scheme` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.
- `TOMCAT_CONNECTOR_HTTP_SECURE`  
  default value: `false`  
  Set the `secure` attribute of the http connector element in ${CATALINA_HOME}/conf/server.xml.

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
	docker run -p 8080:8080 ghcr.io/iplass/iplass-standalone

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

### 3.1.36 以降、3.2.11 以降 のバージョン
3.1.36 以降、3.2.11 以降のバージョンを利用している場合は、以下の環境変数を利用することが可能です。

- `TOMCAT_CONNECTOR_HTTP_PORT`  
  デフォルト値: `8080`  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `port` 属性を設定します。
- `TOMCAT_CONNECTOR_HTTP_CONNECTION_TIMEOUT`  
  デフォルト値: `20000`  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `connectionTimeout` 属性を設定します。
- `TOMCAT_CONNECTOR_HTTP_REDIRECT_PORT`  
  デフォルト値: `8443`  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `redirectPort` 属性を設定します。
- `TOMCAT_CONNECTOR_HTTP_MAX_PARAMETER_COUNT`  
  デフォルト値: `1000`  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `maxParameterCount` 属性を設定します。
- `TOMCAT_CONNECTOR_HTTP_PROXY_NAME`  
  デフォルト値: 無し  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `proxyName` 属性を設定します。
- `TOMCAT_CONNECTOR_HTTP_PROXY_PORT`  
  デフォルト値: 無し  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `proxyPort` 属性を設定します。
- `TOMCAT_CONNECTOR_HTTP_SCHEME`  
  デフォルト値: `http`  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `scheme` 属性を設定します。
- `TOMCAT_CONNECTOR_HTTP_SECURE`  
  デフォルト値: `false`  
  ${CATALINA_HOME}/conf/server.xml の http connector 要素の `secure` 属性を設定します。
