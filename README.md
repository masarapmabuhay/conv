# Browser-based Units Converter App

Can you make use of your knowledge of HTML5 and Javascript to create a simple units converter app that runs on web browers?

# Development Logs

1. 20260525; Create the appearance first. Without yet interactivity.<br/>

<img src="https://github.com/masarapmabuhay/conv/blob/main/screenshots/convScreenshotV20260525T1522.png" width="60%">

2. 20260527; http://store.usbong.ph/server/conv/conv20260527.html<br/>
+added: basic conversion from kg to pound or vice-versa; using constant `1 kg` is to `2.20462262 pounds`;<br/> 
+noted: conversion quickly done and without having to refresh the browser due to using Javascript;<br/>
+added: `toFixed(4)` to reduce not have too many numbers after the decimal point;<br/>
TODO: -verify parameter put in `toFixed(...)`;

3. 20260528 (CURRENT); http://store.usbong.ph/server/conv/conv.html<br/>
+added: `select` function that auto-updates the labels and the multiplier based on the chosen option; `Mass` or `Length`<br/>
+added: `Length` coversion; `foot` to `centimeter`; in addition to `Mass`<br/>
+updated: position of cursor in input boxes to `center` instead of `right`<br/>
+fixed: `NaN` is displayed in the input box when the other input box has received a letter in the alphabet or some other non-number character<br/>
+fixed: letters in the alphabet can still be inserted between the numbers in the input box<br/>
+fixed: decimal point cannot be added if the input box is blank<br/>
TODO: -verify parameter put in `toFixed(...)`;<br/>

# Get PhilNITS Certified!

https://philnits.org/

# Open Source Software License

Copyright 2026 SYSON, MICHAEL B.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0
  
Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

@company: USBONG<br/>
@author: SYSON, MICHAEL B.<br/>
@website address: http://www.usbong.ph<br/>
