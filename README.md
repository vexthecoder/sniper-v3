all information on the sniper will be fully added on first release. but for now, here is how to get your discord token and roblox cookie.

## Important Security Warning

**These scripts extract sensitive authentication information. Use with caution:**

- Never share extracted tokens with anyone
- Tokens can provide full account access
- Use only for the sniper

## Discord Token Extractor Script

### How to Use
1. Navigate to [Discord Web](https://discord.com/app)
2. Login to your account
3. Open Browser Developer Tools (F12)
4. Click on the Mobile Device Icon to enable mobile mode
5. Go to Console tab
6. Paste the following script (click "Show Script" to expand):
7. Click Enter to run

<details>
<summary>Show Script</summary>

```javascript
const iframe = document.createElement('iframe');
document.body.appendChild(iframe);

try {
    const token = iframe.contentWindow.localStorage.token;
    
    if (token) {
        let tokenValue;
        try {
            tokenValue = JSON.parse(token);
        } catch (e) {
            tokenValue = token;
        }
        
        const copyToClipboard = async (text) => {
            try {
                await navigator.clipboard.writeText(text);
                return true;
            } catch (err) {
                const textArea = document.createElement('textarea');
                textArea.value = text;
                document.body.appendChild(textArea);
                textArea.select();
                const success = document.execCommand('copy');
                document.body.removeChild(textArea);
                return success;
            }
        };
        
        copyToClipboard(tokenValue).then(success => {
            if (success) {
                console.log('✅ Token copied to clipboard: %c%s', 'font-size:16px; color: green;', tokenValue);
                console.log('📋 Token has been automatically copied to your clipboard!');
            } else {
                console.log('✅ Token: %c%s', 'font-size:16px; color: green;', tokenValue);
                console.log('❌ Could not copy to clipboard. Manually copy the token above.');
            }
        });
        
    } else {
        console.log('❌ No token found in localStorage');
        console.log('%c📱 Mobile Mode Required:', 'font-size:16px; color: orange; font-weight: bold;');
        console.log('1. Press F12 to open Developer Tools');
        console.log('2. Click the 📱 mobile device icon (Toggle Device Toolbar)');
        console.log('3. Refresh the page or re-authenticate');
        console.log('4. Run this script again');
    }
} catch (e) {
    console.log('❌ Error:', e.message);
    console.log('%c📱 Enable mobile mode and try again!', 'font-size:14px; color: orange;');
} finally {
    iframe.remove();
}
```
</details>

### Troubleshooting
- **Token not found?** Enable mobile mode in developer tools
- **Copy failed?** Manually copy from console output
- **Error?** Ensure you're logged in and on discord.com

</details>

## Roblox .ROBLOSECURITY Cookie

You can't use a script to extract the roblox cookie, so please watch this video tutorial for instructions:

[Roblox Cookie Tutorial](https://youtu.be/sz07F5inaFg?t=16)

## Support

For issues with the Discord token script:
1. Ensure you're logged into Discord
2. Try refreshing the page
3. Check browser console for errors
4. Verify you're on discord.com
5. Make sure you have the mobile mode enabled

For Roblox cookie extraction, refer to the video tutorial above.