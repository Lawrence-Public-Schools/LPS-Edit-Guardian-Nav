# Parent Portal Customization

## Table of Contents
1. [Overview](#overview)
2. [Parent Portal Before and After](#parent-portal-before-and-after)
3. [Code to Disable Items](#code-to-disable-items)

---

## Overview
The following items have been disabled for the parent portal:
- Standards Based Report Card *`//wildcards/guardian_header.report_cardsrwrc.leftnav.footer.txt`*  
- Course Based Report Card *`//wildcards/guardian_header.report_cardsrwrc.leftnav.footer.txt`*  
- Student Transcript *`//wildcards/guardian_header.report_cardsrwrc.leftnav.footer.txt`*  
- Email Notification *`//wildcards/guardian_header.txt`*  
- Document Library *`//wildcards/guardian_header.DD_insert.leftnav.footer.txt`*  
- Lunch Menu *`//wildcards/guardian_header.lunchmenu.context.footer.txt`*  

---

## Parent Portal Before and After
Below is a comparison of the parent portal with the items enabled and disabled:

<div align="center">
<table>
    <tr>
        <th>Before (Items Enabled)</th>
        <th>After (Items Disabled)</th>
    </tr>
    <tr>
        <td align="center" valign="top">
            <img src="images/itemsEnabled.png" alt="Parent Portal with Items Enabled" width="150" height="600">
        </td>
        <td align="center" valign="top">
            <img src="images/itemsDisabled.png" alt="Parent Portal with Items Disabled" width="150" height="600">
        </td>
    </tr>
</table>
</div>

---

## Code to Disable Items
I was not having much success with manipulating the *`guardian_header.txt`* files, so I decided to see what the elements were named in the DOM. I used the browser's developer tools to inspect the elements and found that they had IDs. I then used jQuery to hide them.

The following code snippet disables specific buttons by hiding them using jQuery:

```javascript
<script>
    // Disable specific buttons by hiding them
    $j(document).ready(function () {
        $j("#insertLink3").hide(); // Hides the #insertLink3 section
        $j("#btn-emailNotification").hide(); // Hides the Email Notification button
        $j("#btn-docMgmt").hide(); // Hides the Document Library button
        $j("#btn-lunchmenu").hide(); // Hides the Lunch Menu button
    });
</script>
```

### Explanation
- The `$j` function is a shorthand for jQuery.
- The `hide()` method hides the selected elements, making them invisible to the user while still present in the DOM.