# 1NCE Tools - README

## Usage

1. **Settings Tab**: Enter your API credentials and choose an output directory where CSV files will be saved.
2. **Get SIM List Tab**: Retrieve a list of SIMs and save it to a CSV file.
3. **Get SIM Quota Tab**: Load a CSV file with ICCID data and retrieve the quota details for each SIM.
4. **Update Label Tab**: Load a CSV or TSV file with ICCID and label data to update SIM labels.
5. **Software Update Tab**: Check for the latest version of the application and download updates when available.

## Supported CSV Formats for Update Label

The application supports CSV and TSV formats with the following structure:

- **ICCID and LABEL columns**:
   - For **Update Label** functionality, the CSV file should contain at least two columns:
     1. ICCID (required)
     2. LABEL (optional, can be left blank for no label)

Example CSV structure:
```csv
ICCID,LABEL
8988228066608751xxx,Test-Label0920
8988228066608751xxx,Another-Label
```

The application also supports CSV files exported from the 1NCE portal. These files contain a full set of SIM data including ICCID, IMSI, status, and other relevant fields. The tool can work with such files to retrieve and update SIM data seamlessly.

Example structure from 1NCE Portal:
```csv
ICCID,EID,STATUS,IMSI,MSISDN,IMEI,IP_ADDRESS,SIM_TYPE,LABEL
8988228066608751xxx,,active,901405108751345,882285108751xxx,,,,Test-Label0920
8988228066608751xxx,,active,901405108751347,882285108751xxx,,,,Another-Label
```

## Software Update

### macOS

1. **Downloading and Installing the Update (.dmg file)**
   - Use the Software Update tab to check for the latest version. When an update is available, download the .dmg file and install it by dragging `1NCE-Tools.app` to the Applications folder.
2. **Remove Quarantine Attribute**
   - After downloading the .dmg file, macOS might quarantine the app, which can prevent it from running properly. To remove the quarantine attribute, open Terminal and run the following command:
     ```bash
     xattr -r -d com.apple.quarantine /Applications/1NCE-Tools.app
     ```
3. **Grant Execute Permissions After Software Update**
   - If the application does not start after the update, you may need to ensure the executable files have the correct permissions. Run the following command in Terminal:
     ```bash
     chmod -R +x /Applications/1NCE-Tools.app
     ```

### Windows

1. **Security Warning**:
   - Windows Defender or SmartScreen may warn you about the application being unsigned. If this happens:
     1. Click “More info” on the warning.
     2. Select “Run anyway” to proceed.
2. **Unblocking the File**:
   - Windows may block files downloaded from the internet. To unblock:
     1. Right-click the .exe file, select “Properties.”
     2. Under the General tab, check “Unblock.”
     3. Click “Apply” and then “OK.”

## Requirements

- Active internet connection for API requests.
- 1NCE API credentials.

## Disclaimer

This tool is not affiliated with or endorsed by 1NCE GmbH or 1NCE KK. It is a personal project developed independently. The tool utilizes publicly available APIs provided by 1NCE but is in no way associated with the company.

Any use of this tool is at your own risk, and neither 1NCE GmbH nor 1NCE KK bears any responsibility for its functionality or use.

## FAQ

### Running the Application on macOS

On macOS, due to the app being unsigned, users may encounter a warning from Gatekeeper when trying to run the app for the first time:

**Error**: “'1NCE-Tools' can’t be opened because Apple cannot check it for malicious software.”

To resolve this, follow these steps:

1. Go to “System Preferences” → “Security & Privacy” → “General.”
2. You will see a message saying that the app was blocked from opening. Click the “Open Anyway” button.
3. When prompted again, click “Open” to run the app.

You only need to do this the first time you open the application.

### Permission Issues on macOS

In some cases, the application might fail to start due to permission issues. This can happen if the app’s executable files are missing the necessary permissions or the app is quarantined. To resolve this issue:

1. **Remove quarantine attribute**:
   - Open Terminal and navigate to the directory where the application is located, then run the following command:
     ```bash
     xattr -r -d com.apple.quarantine /Applications/1NCE-Tools.app
     ```
2. **Grant execute permissions**:
   - If the application still doesn’t open, ensure that it has the necessary execute permissions:
     ```bash
     chmod -R +x /Applications/1NCE-Tools.app
     ```
3. **Try opening the app again**.

These steps should resolve any permission-related issues on macOS.

### Running the Application on Windows

On Windows, similar to macOS, you might encounter a security warning due to the app being unsigned. Windows Defender or SmartScreen may prevent the app from running.

1. **Windows Defender SmartScreen Warning**:
   - If you see a message saying, “This app may harm your device” or “This app has been blocked for your protection,” follow these steps:
     1. Click “More info” on the warning message.
     2. Then, click the “Run anyway” button to allow the app to run.
2. **How to Disable SmartScreen Temporarily (not recommended)**:
   1. Open the Start Menu and search for “Windows Security.”
   2. Go to “App & browser control.”
   3. In the “Check apps and files” section, select “Warn” or “Off.”
   - **Note**: Disabling SmartScreen is not recommended as it provides protection from potentially harmful applications.
3. **Unblocking the File**:
   - Sometimes, Windows blocks files downloaded from the internet. To unblock:
     1. Right-click the .exe file of the app and select “Properties.”
     2. Under the General tab, if you see a message saying, “This file came from another computer and might be blocked,” check the box “Unblock.”
     3. Click “Apply” and then “OK.”

## Support

Please note that this software is provided as-is without any official support. If you encounter issues, refer to the FAQ section for troubleshooting steps. While we strive to make the software as stable as possible, we are unable to offer dedicated support for individual inquiries.


# 1NCEツール - README

## 使用方法

1. **設定タブ**: APIの認証情報を入力し、CSVファイルを保存する出力ディレクトリを選択します。
2. **SIMリスト取得タブ**: SIMのリストを取得し、CSVファイルに保存します。
3. **SIMクオータ取得タブ**: ICCIDデータを含むCSVファイルを読み込み、各SIMのクオータ詳細を取得します。
4. **ラベル更新タブ**: ICCIDおよびラベルデータを含むCSVまたはTSVファイルを読み込み、SIMラベルを更新します。
5. **ソフトウェア更新タブ**: アプリケーションの最新バージョンを確認し、利用可能な場合は更新をダウンロードします。

## ラベル更新用のサポートされるCSV形式

アプリケーションは以下の構造のCSVおよびTSV形式をサポートしています。

- **ICCIDおよびLABELの列**:
   - **ラベル更新**機能の場合、CSVファイルには少なくとも以下の2つの列が必要です:
     1. ICCID（必須）
     2. LABEL（任意、ラベルがない場合は空白にできます）

CSVのサンプル構造:
```csv
ICCID,LABEL
8988228066608751xxx,Test-Label0920
8988228066608751xxx,Another-Label
```

1NCEポータルからエクスポートされたCSVファイルにも対応しています。これらのファイルにはICCID、IMSI、ステータスなど、SIMデータの完全なセットが含まれており、このツールはそれらのファイルを使ってSIMデータの取得および更新をシームレスに行えます。

1NCEポータルからのサンプル構造:
```csv
ICCID,EID,STATUS,IMSI,MSISDN,IMEI,IP_ADDRESS,SIM_TYPE,LABEL
8988228066608751xxx,,active,901405108751345,882285108751xxx,,,,Test-Label0920
8988228066608751xxx,,active,901405108751347,882285108751xxx,,,,Another-Label
```

## ソフトウェア更新

### macOS

1. **更新のダウンロードとインストール (.dmgファイル)**
   - ソフトウェア更新タブを使用して最新バージョンを確認します。更新が利用可能な場合は、.dmgファイルをダウンロードし、`1NCE-Tools.app`をアプリケーションフォルダにドラッグしてインストールします。
2. **隔離属性の削除**
   - .dmgファイルをダウンロードした後、macOSはアプリを隔離することがあり、正常に動作しない可能性があります。隔離属性を削除するには、ターミナルを開き、以下のコマンドを実行します。
     ```bash
     xattr -r -d com.apple.quarantine /Applications/1NCE-Tools.app
     ```
3. **ソフトウェア更新後の実行権限の付与**
   - 更新後にアプリケーションが起動しない場合、実行ファイルに正しい権限が必要になることがあります。ターミナルで以下のコマンドを実行します。
     ```bash
     chmod -R +x /Applications/1NCE-Tools.app
     ```

### Windows

1. **セキュリティ警告**:
   - Windows DefenderやSmartScreenがアプリケーションを未署名として警告することがあります。その場合は次の手順を行ってください:
     1. 警告に「詳細情報」をクリックします。
     2. 「実行」を選択して続行します。
2. **ファイルのブロック解除**:
   - インターネットからダウンロードしたファイルをWindowsがブロックすることがあります。ブロックを解除するには:
     1. .exeファイルを右クリックして「プロパティ」を選択します。
     2. 「全般」タブで「ブロック解除」にチェックを入れます。
     3. 「適用」をクリックし、その後「OK」をクリックします。

## 必要条件

- APIリクエストのためのインターネット接続が必要です。
- 1NCE APIの認証情報。

## 免責事項

このツールは1NCE GmbHまたは1NCE KKによって承認または提携されたものではありません。本ツールは独自に開発された個人的なプロジェクトです。ツールは1NCEが提供する公開APIを利用していますが、同社とは一切関係がありません。

本ツールの使用は自己責任で行ってください。1NCE GmbHおよび1NCE KKは、本ツールの機能や使用について一切の責任を負いません。

## FAQ

### macOSでアプリケーションを実行する

macOSでは、アプリが未署名であるため、初回実行時にGatekeeperから警告を受けることがあります。

**エラー**: 「'1NCE-Tools'は悪意のあるソフトウェアかどうかをAppleが確認できないため、開くことができません。」

これを解決するには、次の手順を実行してください:

1. 「システム環境設定」→「セキュリティとプライバシー」→「一般」を開きます。
2. アプリがブロックされたというメッセージが表示されるので、「このまま開く」ボタンをクリックします。
3. 再度プロンプトが表示されたら、「開く」をクリックしてアプリを実行します。

これはアプリを初めて開く際にのみ必要です。

### macOSでの権限の問題

場合によっては、アプリケーションが実行に必要な権限が不足しているため、起動に失敗することがあります。これを解決するには:

1. **隔離属性の削除**:
   - ターミナルを開き、アプリケーションが存在するディレクトリに移動してから、以下のコマンドを実行します。
     ```bash
     xattr -r -d com.apple.quarantine /Applications/1NCE-Tools.app
     ```
2. **実行権限の付与**:
   - アプリケーションがまだ開かない場合は、必要な実行権限を付与してください。
     ```bash
     chmod -R +x /Applications/1NCE-Tools.app
     ```
3. **アプリを再度開いてみてください**。

これらの手順でmacOSでの権限に関連する問題を解決できるはずです。

### Windowsでのアプリケーション実行

Windowsでも、macOSと同様にアプリが未署名であるため、セキュリティ警告が表示されることがあります。Windows DefenderまたはSmartScreenがアプリの実行を阻止する場合があります。

1. **Windows Defender SmartScreenの警告**:
   - 「このアプリはお使いのデバイスに危害を与える可能性があります」または「このアプリは保護のためにブロックされました」と表示された場合:
     1. 警告メッセージで「詳細情報」をクリックします。
     2. 次に「実行」ボタンをクリックし、アプリの実行を許可します。
2. **SmartScreenを一時的に無効にする方法（推奨されません）**:
   1. スタートメニューを開き、「Windowsセキュリティ」を検索します。
   2. 「アプリとブラウザーコントロール」に移動します。
   3. 「アプリとファイルの確認」セクションで「警告」または「オフ」を選択します。
   - **注意**: SmartScreenを無効にすることは推奨されません。これは潜在的に有害なアプリケーションから保護する機能を提供しているためです。
3. **ファイルのブロック解除**:
   - Windowsがインターネットからダウンロードしたファイルをブロックすることがあります。ブロックを解除するには:
     1. アプリの.exeファイルを右クリックして「プロパティ」を選択します。
     2. 「全般」タブで「このファイルは他のコンピュータから取得したもので、ブロックされている可能性があります」と表示されている場合、「ブロック解除」にチェックを入れます。
     3. 「適用」をクリックし、その後「OK」をクリックします。

## サポート

このソフトウェアは現状のまま提供され、公式なサポートはありません。問題が発生した場合は、FAQセクションを参照してトラブルシューティングを行ってください。できる限り安定したソフトウェアを提供するよう努めていますが、個別の問い合わせに対して専用のサポートを提供することはできません。

