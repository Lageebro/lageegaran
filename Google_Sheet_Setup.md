**How to Connect Your Contact Form to a Google Sheet**

Follow these exact steps to start receiving messages on your Google Sheet:

1. Go to Google Drive (drive.google.com) and create a **New Google Sheets** file.
2. Name the file something like "Portfolio Messages".
3. In row 1 (the top header row), enter these EXACT 4 words in columns A, B, C, and D:
   - A1: **date**
   - B1: **name**
   - C1: **email**
   - D1: **message**
   (These must exactly match the lowercase words above).

4. Click on **Extensions** in the top menu, then click **Apps Script**.
5. Delete the empty `function myFunction() {}` code that is there, and paste this EXACT code instead:

```javascript
const sheetName = 'Sheet1';

function doPost(e) {
  const lock = LockService.getScriptLock();
  lock.tryLock(10000);

  try {
    const doc = SpreadsheetApp.getActiveSpreadsheet();
    const sheet = doc.getSheetByName(sheetName);
    
    const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getValues()[0];
    const nextRow = sheet.getLastRow() + 1;
    
    const newRow = headers.map(function(header) {
      return header === 'date' ? new Date() : e.parameter[header];
    });

    sheet.getRange(nextRow, 1, 1, newRow.length).setValues([newRow]);
    
    return ContentService
      .createTextOutput(JSON.stringify({ 'result': 'success', 'row': nextRow }))
      .setMimeType(ContentService.MimeType.JSON);
  }
  
  catch (e) {
    return ContentService
      .createTextOutput(JSON.stringify({ 'result': 'error', 'error': e }))
      .setMimeType(ContentService.MimeType.JSON);
  }
  
  finally {
    lock.releaseLock();
  }
}
```

6. Click the Save icon (💾) at the top.
7. Now look at the top right for a big blue button named **Deploy** and click it -> Choose **New deployment**.
8. Click the gear icon (⚙️) next to "Select type" and choose **Web app**.
9. Fill out the details exactly like this:
   - Description: "Contact Form endpoint"
   - Execute as: **Me (your email)**
   - Who has access: **Anyone**  <-- (CRITICAL STEP! Must be "Anyone" so the website can talk to it).
10. Click **Deploy**.
11. You will see a prompt saying "Authorization required". Click **Authorize access**, select your Google account, click "**Advanced**" (if shown), and then click "Go to Untitled project (unsafe)" and finally click "**Allow**".
12. Once deployed, you will get a **Web app URL**. Copy that long link!
13. Now, open your website's **index.html** file.
14. Scroll down to line **768** to this section:
    `const scriptURL = 'YOUR_GOOGLE_SCRIPT_WEB_APP_URL_HERE';`
15. Replace `'YOUR_GOOGLE_SCRIPT_WEB_APP_URL_HERE'` with the long URL you just copied (keep the quotes!).

Done! Now whenever someone types a message and hits send, it will show "Sending...", and the message will automatically appear in your Google Sheet!
