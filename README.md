# cll Library

This library provides functionality for implementing circular linked lists in JavaScript.
This is a circular-linked list library that provides various operations on the circular-linked lists library to visualize and interact with a circular-linked list using animations.
Go to the link to experience the animation ->  https://chintu1308.github.io/cll-library/src

## Installation 1

You can install this library using npm:

```bash
npm install cll-library
```
## Usage

To use the CLL library in your project, include the cllpractice.min.js file in your HTML:

```HTML

<script src="https://cdn.jsdelivr.net/gh/Chintu1308/cll-library/dist/js/cllpractice.min.js"></script>
```
Then, you can use the cll functions in your JavaScript code. For example:

```javascript

const CircularLinkedList = require('./cll-library');

const cll = new CircularLinkedList();
cll.append(1);
cll.append(2);
cll.append(3);
cll.display();  // Output: 1 -> 2 -> 3 -> HEAD

cll.prepend(0);
cll.display();  // Output: 0 -> 1 -> 2 -> 3 -> HEAD

cll.remove(2);
cll.display();  // Output: 0 -> 1 -> 3 -> HEAD

console.log(cll.getSize());  // Output: 3

```

## Installation 2

You can use this library by including the following resources in your HTML file. No need to download any files, just link directly to the hosted files.

## Usage

**Method1: Add to HTML Structure**
Include the following HTML structure to your webpage where you want the linked list animation to appear:

```HTML
<iframe src="https://chintu1308.github.io/cll-library/dist" width="650" height="400" frameborder="0"  allowfullscreen></iframe>
```
**Method2: Add as a Button**
add a button as follows
```HTML
<button onclick="openAnimation()">Open Linked List Animation</button>
```
and add the following function to your javascript
```javascript
function openAnimation() {
            window.open('https://chintu1308.github.io/cll-library/dist', '_blank', 'noopener,noreferrer');
        }
```
## For mobile and web applications

**Embedding in a Web Application**

If you want to add animation to a web application, such as one built with React, Vue, or Angular, you can use a similar approach with the iframe. Here is an example for a React application:

```jsx

import React from 'react';

const LinkedListAnimation = () => {
    return (
        <div style={{ width: '100%', height: '400px', position: 'relative' }}>
            <iframe src="https://chintu1308.github.io/cll-library/dist/index.html" style={{ width: '100%', height: '100%', border: 'none' }}></iframe>
        </div>
    );
};

export default LinkedListAnimation;
```
**Embedding in a Mobile Application (WebView)**

For mobile applications, you can use a WebView component to load the animation. Below are examples for both Android and iOS:

Android (using WebView):
***1. Add WebView dependency to your build.gradle file:***

```gradle
dependencies {
    implementation 'androidx.webkit:webkit:1.4.0'
}
```
***2. Create a WebView in your layout XML file:***
```XML
<WebView
    android:id="@+id/webview"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

***3. Load the URL in your Activity:***

```java
import android.os.Bundle;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        WebView webView = findViewById(R.id.webview);
        webView.setWebViewClient(new WebViewClient());
        webView.loadUrl("https://chintu1308.github.io/cll-library/dist/index.html");
    }
}
```
### iOS (using WebView):
Create a WebView in your Storyboard or SwiftUI view:
```swift
import SwiftUI
import WebKit

struct ContentView: View {
    var body: some View {
        WebView(url: URL(string: "https://chintu1308.github.io/cll-library/dist/index.html")!)
    }
}

struct WebView: UIViewRepresentable {
    let url: URL

    func makeUIView(context: Context) -> WKWebView {
        return WKWebView()
    }

    func updateUIView(_ uiView: WKWebView, context: Context) {
        let request = URLRequest(url: url)
        uiView.load(request)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```
