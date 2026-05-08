# Browser-based Calculator App

Can you make use of your knowledge of HTML5 and Javascript to create a simple calculator app that runs on web browers?

# Development Logs

1. Create the appearance first. Without yet interactivity.<br/>

<img src="https://github.com/usbong/calc/blob/main/screenshots/calcScreenshotV20260427T1507.png" width="60%">

2. 20260428; http://store.usbong.ph/server/calc/index20260428.html<br/>
Add basic arithmetic: Addition, Subtraction, Multiplication, Division

3. 20260429; http://store.usbong.ph/server/calc/index20260429.html<br/>
+added: backspace<br/>
+fixed: equals button not correctly displayed in newer browsers<br/>
+fixed: error when operator is added before adding any operand

4. 20260430; http://store.usbong.ph/server/calc/index20260430.html<br/>
+fixed: backspace error when there's only a digit left after doing an operation; "sCurrOperand" incorrectly set to Float, instead of String<br/>
+fixed: backspace error when the operator is backspaced, then a new operator cannot anymore be added<br/>
+added: decimal point<br/>
+added: max 11 digits for the resulting answer if it has a decimal point<br/>
+added: max 13 operands and operators including the decimal point<br/>
+added: "Clear" button which replaces the "Backspace" button after using the equals operator; then, again bring back the "Backspace" button upon entering an operand or an operator<br/>
+updated: multiply symbol to "×"<br/>
+updated: multiply symbol to "÷"<br/>
+updated: equals button position to "136px;" from "136.5px;"

<img src="https://github.com/usbong/calc/blob/main/screenshots/calcScreenshotV20260430T1447.png" width="60%">

5. 20260501; http://store.usbong.ph/server/calc/index20260501.html<br/>
+added: current operator can be changed at its position<br/>
+set: temporarily input box to read-only to prevent intentional or inadvertent entering of text via keyboard 

6. 20260502; http://store.usbong.ph/server/calc/index20260502.html<br/>
+fixed: pressing equals button multiple times causes next arithmetic operation to result to zero<br/>
+removed: reset function via pressing equals button; instead, use "Clear" button<br/>
+fixed: certain sequences that lead to incorrect output;<br/>
**Examples:** `3*/B*` error, `5*60=*B==/2` error<br/>
+added: changeable number signs<br/>
+fixed: `3/=5`; previously resulted to `05`; now results to `5`<br/>
TODO: -fix: `3*-B` becomes `3`, instead of `3*`<br/>
TODO: -fix: `-*B` now removes both `-*`

7. 20260504; http://store.usbong.ph/server/calc/index.html<br/>
+fixed: `3*-B` becomes `3`, instead of `3*`<br/>
+fixed: `-*B` now removes both `-*`; `-*` already results to `<blank>`<br/>
+fixed: `-*` should result to `<blank>`<br/>
+fixed: backspace in `3x-` incorrectly results to `3` instead of `3x`<br/>
TODO: -add: PEMDAS

<img src="https://github.com/usbong/calc/blob/main/plan/pemdasPlan20260504.jpg" width="60%">

8. 20260505; http://store.usbong.ph/server/calc/index.html<br/>
+added: PEMDAS without yet the parenthesis<br/>
+tested: to output the correct answer with the following:<br/>
`6*2+1=13`<br/>
`1+2*6=13`<br/>
`3-1*6+2=-1`<br/>
`1-3+2=0`<br/>
`1*3/6=0.5`<br/>
`2*5/3=3.333333333`<br/>

9. 20260506; http://store.usbong.ph/server/calc/index.html<br/>
+added: work-in-progress function to process the parentheses with code for debugging purposes

<img src="https://github.com/usbong/calc/blob/main/plan/pemdasPlanParenthesis20260506.jpg" width="60%">

10. 20260507; http://store.usbong.ph/server/calc/index.html<br/>
+updated: work-in-progress function to process the parentheses with code for debugging purposes; can now prepare the input to be processed<br/> 
**Example:**<br/> 
**input:** `2*(1-(1+2*6))`<br/>
**output:** `1+2*6`

11. 20260508 (CURRENT); http://store.usbong.ph/server/calc/index.html<br/>
+updated: function to process the parentheses; can now output correctly given the input; though not yet integrated with the rest of the code<br/> 
**Example:**<br/> 
**input:** 2×(1-(1+2×6))<br/> 
**process:** 2×(1-A)<br/>
**output:** 2×(1-13)<br/>

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
