# wide-chatgpt
Tampermonkey script from reddit to give chatgpt a wide user interface

From reddit user: 

https://www.reddit.com/user/__nickerbocker__/

Link to post: 

https://www.reddit.com/r/OpenAI/comments/19ffvs9/tutorial_how_to_make_chatgpt_full_width_using_a/

----

Tutorial: How to Make ChatGPT Full Width Using a Custom Tampermonkey Script
Tutorial

Tutorial: How to Make ChatGPT Full Width Using a Custom Tampermonkey Script

This tutorial will guide you through the process of making the ChatGPT interface on https://chat.openai.com/ use the full width of your browser window, or any width of your choosing, using a Tampermonkey script.

What You’ll Need:

    A modern web browser (e.g., Chrome, Firefox, Edge).

    Tampermonkey extension installed in your browser.

Step-by-Step Guide:

    Install Tampermonkey:

    Create a New Script:

    Click the Tampermonkey icon in your browser toolbar and select “Create a new script…”

    Script Setup:

    A new tab will open with a script editor. You’ll see some default text.

    Replace that text with the following script:

```
// ==UserScript==
// @name         OpenAI Chat Full Width Adjustment for All Messages
// @namespace    http://tampermonkey.net/
// @version      1.1
// @description  Adjust the max-width of all message elements on OpenAI Chat website, for both user and ChatGPT messages
// @author       __nickerbocker__
// @match        https://chat.openai.com/*
// @grant        none
// ==/UserScript==

(function() {
    'use strict';

    function adjustWidth() {
        // Select all message elements using a more inclusive selector
        var elements = document.querySelectorAll('.flex.flex-1.text-base.mx-auto.gap-3.md\\:px-5.lg\\:px-1.xl\\:px-5');

        elements.forEach(function(element) {
            // Adjust the max-width property with !important to override media queries
            element.style.cssText = 'max-width: 100% !important;';
        });

        console.log(elements.length + " chat elements adjusted.");
    }

    // Adjust the width of all messages on page load
    window.addEventListener('load', adjustWidth);

    // Continuously adjust the width of new messages
    setInterval(adjustWidth, 500);
})();
```

4. Save the Script:

    Click “File” then “Save” in the Tampermonkey editor tab.

    Visit ChatGPT:

    Go to https://chat.openai.com/ in your browser. The script should automatically run and adjust the chat interface to full width.

Modifying the Script for Different Widths:

If you prefer a specific width rather than full width, you can modify the script:

    Locate the line in the script that says element.style.cssText = 'max-width: 100% !important;';.

    Change 100% to any other value, like 80% for 80% width, or 1200px for a fixed width of 1200 pixels.

    Example: element.style.cssText = 'max-width: 80% !important;'; for 80% width.

Troubleshooting:

    If the script doesn’t seem to work, ensure that Tampermonkey is enabled and the script is active.

    Check for typos in the script, especially in the document.querySelector line.

    The website's layout may change over time, requiring updates to the script.

Conclusion:

You now have a customized browsing experience on ChatGPT with control over the chat interface width. Enjoy your tailored browsing experience!


