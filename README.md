# Browser-based Calculator App

Can you make use of your knowledge of HTML5 and Javascript to create a simple calculator app that runs on web browers?

This is what I've been able to accomplish in four weeks using my available free time.<br/>
<br/>
http://store.usbong.ph/server/calc/calc.html

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

7. 20260504; http://store.usbong.ph/server/calc/index20260504.html<br/>
+fixed: `3*-B` becomes `3`, instead of `3*`<br/>
+fixed: `-*B` now removes both `-*`; `-*` already results to `<blank>`<br/>
+fixed: `-*` should result to `<blank>`<br/>
+fixed: backspace in `3x-` incorrectly results to `3` instead of `3x`<br/>
TODO: -add: PEMDAS

<img src="https://github.com/usbong/calc/blob/main/plan/pemdasPlan20260504.jpg" width="60%">

8. 20260505; http://store.usbong.ph/server/calc/index20260505.html<br/>
+added: PEMDAS without yet the parenthesis<br/>
+tested: to output the correct answer with the following:<br/>
`6*2+1=13`<br/>
`1+2*6=13`<br/>
`3-1*6+2=-1`<br/>
`1-3+2=0`<br/>
`1*3/6=0.5`<br/>
`2*5/3=3.333333333`<br/>

9. 20260506; BUGGY<br/>
+added: work-in-progress function to process the parentheses with code for debugging purposes

<img src="https://github.com/usbong/calc/blob/main/plan/pemdasPlanParenthesis20260506.jpg" width="60%">

10. 20260507; BUGGY<br/>
+updated: work-in-progress function to process the parentheses with code for debugging purposes; can now prepare the input to be processed<br/> 
**Example:**<br/> 
**input:** `2*(1-(1+2*6))`<br/>
**output:** `1+2*6`

11. 20260508; BUGGY<br/>
+updated: function to process the parentheses; can now output correctly given the input; though not yet integrated with the rest of the code<br/> 
**Example:**<br/> 
**input:** `2×(1-(1+2×6))`<br/> 
**process:** `2×(1-A)`<br/>
**output:** `2×(1-13)`<br/>

12. 20260509; BUGGY<br/>
+updated: function to process the parentheses; gradually getting integrated with the rest of the code;<br/>
+noted: opted to add code that reads the input as a string of characters, which is auto-processed, identifying which are operands and which are operators, while storing them in the correct sequence;<br/>
+noted: right now, the first set inside the parentheses from the right has to be manually identified and then put into `arrayOperator` and `arrayOperand`<br/>
**Example:**<br/> 
**input:** `3×(1-2)`<br/> 
**process:** `3×-1`<br/> 
**output (CORRECT):** `-3`<br/> 
TODO: -reverify: with other example cases, e.g. `2×(1-(1+2×6))`<br/>
TODO: -add: `3(5)` which is equal to `3×5`<br/>  
				
13. 20260510; http://store.usbong.ph/server/calc/index20260510.html<br/>
+reverted: to version 20260505 with updates such as:<br>
+updated: to allow only one operator; due to `9/3*2`; error where `9/(3*2)` is done instead of `(9/3)*2`<br/>
+fixed: `3*3-B3=` results to error; by changing `B` to `C` ("Clear") to prevent the user from pressing backspace; other cases such as `3*3-=` are already giving the correct outputs;<br>

<table border="1">
  <tr>
    <td>
		<h3>
		Thanks for checking out my development logs.<br/>
		<br/>
		This is what I've been able to accomplish in two weeks using my available free time.<br/>
		<br/>
		http://store.usbong.ph/server/calc/index20260510.html
		</h3>
	</td>
  </tr>
</table>

# NEW CALC PLUS

14. 20260512; BUGGY<br/>
+added: auto-scaled user-interface based on whether user's device is mobile or not;<br/>
TODO: -fix: display issues, e.g. equals button (absolute position), on iPad<br/>
TODO: -fix: `280/(1.12)` and `60*0.12` resulting to non-whole number due to approximated value caused by computer's basic characteristic of using binary representations; solution says Google AI Overview is: Integer "Cents" Trick; however, parameter `2` in `toFixed(2)` should be auto-adjusted based on the number of places after the decimal point<br/>
TODO: -fix: max digits reached resulting to an incorrect answer displayed<br/>
TODO: -add: processing of parentheses<br/>

<img src="https://github.com/usbong/calc/blob/main/screenshots/calcScreenshotV20260512T1426.png" width="60%">

<img src="https://github.com/usbong/calc/blob/main/screenshots/calcScreenshotMobileV20260512T1430.jpg" width="30%">

15. 20260513; http://store.usbong.ph/server/calc/calc20260513.html<br/>
+fixed: `280/(1.12)` and `60*0.12` resulting to non-whole number;<br/> 
+added: a function to auto-count how many places there are after the decimal point; the count is used as parameter to `toFixed(...)`<br/>

16. 20260514; http://store.usbong.ph/server/calc/calc20260514.html<br/>
+fixed: incorrect output when doing division; `280/(1.12)` now outputs the correct answer;<br/>
+noted: without using scientific notations like exponents, there's no way to get a result greater than `999,999,999,999` (12 digits) using at most 12 digits summing the number of digits that the two operands have;<br/>
+fixed: display issues, e.g. equals button (absolute position), on iPad<br/>
+noted: padding-right and padding-left have to be set to `0` to fix display issues on iPad; also used "em" instead of "px" for certain button fields;<br/>
+updated: "BackSpace" to "BACKSPACE";<br/>
+updated: "Clear" to "CLEAR";<br/>
+added: browser tab icon<br/>

<img src="https://github.com/usbong/calc/blob/main/screenshots/calcScreenshotIpadMobileLandscapeResizedV20260514T1333.png" width="50%">

<img src="https://github.com/usbong/calc/blob/main/screenshots/calcScreenshotIpadMobilePortraitResizedV20260514T1333.png" width="30%">

17. 20260515; http://store.usbong.ph/server/calc/calc20260515.html<br/>
+updated: to use max available browser width and height if the user is using non-mobile or desktop;<br/>
+updated: to identify if user is using an iPad or MacBook, and adjust the browser width or height available for use accordingly; <br/>
+added: keyboard inputs (keys near numlock or top of keyboard)<br/>
+added: when "=" is pressed, and "CLEAR" button is activated, perform reset();<br/>
+updated: calc fav icon to use the transparent/alpha color;<br/>
TODO: -add: processing of parentheses<br/>

18. 20260516; http://store.usbong.ph/server/calc/calc20260516.html<br/>
+added: auto-focus on the `AnswerInput` so that when `/` is pressed on the keyboard, "Quick find" on Firefox browser isn't opened<br/>
+added: relevant keys other than those near the numlock could be pressed, including those combined with SHIFT down<br/>
+noted: display error when the following is used:<br/>
`<link rel="icon" type="image/x-icon" href="./assets/images/calcfavicon.png?lastmod=20260516T0953">`<br/>
instead of:<br/> 
`<link rel="icon" type="image/x-icon" href="./assets/images/calcfavicon.png">`<br/>
+noted: focusing on creating a "solid" app rather than a buggy one by adding more extra features, e.g. processing of parentheses;<br/>
+added: ESCAPE key to do a `reset()`;<br/>
+updated: max digits to be `14` instead of `12`; though equals sign is allowed to be pressed as the 15th input<br/>
+increased: length of `AnswerInput`'s display to show no partly drawn characters<br/>
+fixed: width too long for standard Android via changing it from `260px` to `240px`<br/>
+updated: equals sign function to continue to process operation even when the BACKSPACE button displays "CLEAR" when there's an operator in `answerInput`<br/>
+fixed: focused `AnswerInput` not displayed uniformly with Firefox, Chrome, Safari on Edge<br/>

19. 20260518; http://store.usbong.ph/server/calc/calc20260518.html<br/> 
+added: when a new operator is entered, calc performs the operation if an existing operator is already present and then adds the new operator;<br/> 
+updated: increased width of buttons, and their positions accordingly;<br/> 
+updated: ESCAPE key to `reset()` and then execute`inputOperator("=")`<br/>

20. 20260519; http://store.usbong.ph/server/calc/calc20260519.html<br/> 
+removed: debug-related comments, thereby reducing the file size from 55KB to 30KB;<br/>
+removed: blinking border effect in `AnswerInput` whenever a button is mouse-clicked;<br/>
+tested: calc functionality; now as usable as how I use the calculator in my day-to-day working life;<br/> 

21. 20260520; http://store.usbong.ph/server/calc/calc20260520.html<br/> 
+updated: output to make sure that all the digits to the left of the decimal point are present;<br/>
+opted: to keep the decimal point even if the numbers to its right aren't anymore displayed due to max length reached;

<img src="https://github.com/usbong/calc/blob/main/screenshots/calcScreenshotV20260520T1514.png" width="50%">

22. 20260522 (CURRENT); http://store.usbong.ph/server/calc/calc.html<br/>
+fixed: `.-6` incorrectly results to `0` instead of `-6`, because `.` (not a number) is now set to `0`;<br/>
+fixed: `.6*6` incorrectly results to `3.599...` instead of `3.6`;<br/>
+fixed: `1.12*100` incorrectly results to `112.00000000000001`, instead of `112` by using `Math.round` after multiplying by the power of `10` raised to a specified number based on the input operands; didn't anymore use `Number.EPSILON` due to incorrect result if operand is `0`;<br/>
+fixed: `0/0=5` incorrectly results to `Err5`, instead of `5`;<br/>
+updated: font size to `1.7rem` for Android, while the default is `1.9rem`; adjusted button font size and position accordingly;<br/>
+increased: `AnswerInput` width on iPad due to additional one digit accepted;<br/>
+updated: when `AnswerInput` is `Err` as a result of `0/0`, for example, pressing any of the operators (except `-`) results to `0`; meanwhile, when `-` is pressed, `-` is immediately put instead of `0`;<br/>
+updated: `0` cannot be added to the left unless there's a `.`<br/>

<table border="1">
  <tr>
    <td>
		<h3>
		Thanks for checking out my development logs.<br/>
		<br/>
		This is what I've been able to accomplish in four weeks using my available free time.<br/>
		<br/>
		http://store.usbong.ph/server/calc/calc.html
		</h3>
	</td>
  </tr>
</table>

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
