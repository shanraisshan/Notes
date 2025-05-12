# Webview
everything related

# PASS DATA TO WEBVIEW
| Method|Summary|Pros|Cons|Best Use Case|
|-|-|-|-|-|
| **HTTP Headers**      | Pass values via custom HTTP headers during the initial WebView request.     | Simple, secure for one-time data, no client-side storage.           | Limited to initial request, not persisted, size limits.             | One-time data (e.g., auth tokens) read server-side.                        |
| **Cookies**           | Set cookies in WebView to send values with every HTTP request to the domain.| Persists across requests, client/server access, standard mechanism. | Security risks (XSS), management overhead, size limits (4KB per cookie). | Persistent data (e.g., session tokens) accessible client- or server-side.  |
| **JavaScript Interface** | Inject data directly into the web page via JavaScript or native interface. | Flexible, no size limits, direct client-side access.                | Security risks, complex setup, client-side only unless sent to server. | Complex/dynamic data (e.g., JSON) for client-side use with trusted web pages. |

# CALL JAVASCRIPT INTERFACE 

```
//window.AndroidBridge.openAppScreen("{\"type\":\"brand\",\"redirected_from\":\"webview\"}")
@JavascriptInterface
fun openAppScreen(json: String?) {
    json?.let { activity.serverOpenAppScreen(it) }
}
```

Call from android
```
window.AndroidBridge.openAppScreen("{\"type\":\"brand\",\"redirected_from\":\"webview\"}")
```

Call from iOS
```
window.webkit.messageHandlers.iOSBridge.postMessage('{"type":"brand","redirected_from":"webview"}');
```

# CENTRAL NAVIGATION FROM 5 PLATFORMS
1. Push
2. In-App Notification
3. Deeplink
4. Webview
5. App Shortcuts
