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
