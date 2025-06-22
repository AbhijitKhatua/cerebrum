![[Pasted image 20250621235852.png]]

![[Pasted image 20250621235911.png]]

![[Pasted image 20250621235942.png]]

![[Pasted image 20250621235957.png]]

For example, if I run the expect method and pass it an invocation of the concatStrings function with numbers 1 and 2 as arguments, my expectation of 12 being the results will fail. This is because when I use the plus operator with two values of the number type, it performs the mathematical operation of addition, instead of joining the two numbers together to form the number 12, like it would form abcdef. If I gave it the arguments of abc and def. When tests fail, you say that they are red, and when they pass, you say that they are green. If a test fails, then it's a sign that I need to write the code 
in such a way that it passes its test. Once my test passes, I need to improve both the app's code and the test code, but without changing the behavior of either.

![[Pasted image 20250622000158.png]]
![[Pasted image 20250622000212.png]]

### Types Of testing

for a UX designer. Testing might mean making sure that the website looks and behaves as expected. 

For project manager on a software project testing might mean that a specific piece 
of software works well with other parts of your system 

for a software engineer. Testing might mean writing code that doesn't break the existing 
functionality is bug free and satisfies the requirements as set out in a given task based on what your motivations are.

1.  End to End testing
2. Integration testing
3. Unit Testing

#### E2E
In testing tries to imitate how a user might interact with your app. This means that in Italy testing you need to open your web application in a browser and then test it by interacting with the page the same way a user might interact with it.

- WebdriverJs
- protractor
- cypress
#### Integration
How parts of system interact with other parts of the system
(how separate parts of apps works together)

- React testing library
- enzyme

#### Unit testing
Unit testing is the process of testing the smallest units of your source code in isolation.

Practically the smallest unit of testable code in Js is usually a function or a method. Unit tests are self contained. They're meant to test code in isolation, preferably separate from the rest of your app. This makes unit tests fast to run and easy to write. 

![[Pasted image 20250622001838.png]]
![[Pasted image 20250622002049.png]]
![[Pasted image 20250622002104.png]]

`npm install --save-dev jest`

![[Pasted image 20250622002923.png]]
![[Pasted image 20250622003114.png]]
![[Pasted image 20250622003127.png]]
![[Pasted image 20250622003247.png]]

Since your coding the TDD way you first write the test, even before you've written any actual implementation, for example, you test if a function named status of keys exists

![[Pasted image 20250622003344.png]]

Since you haven't written your source code implementation. The test fails. Next you run your test. The test fails because there's no status of keys. Function declared. The logic of your test code is expect that the function status of keys exists in your source code. You declare a function named status of keys. You run the test. Again, it checks if there is such a function and it confirms it exists. So the test passes, it's important to note that one of the rules of TDD is that you should write as little code as possible to make the test pass for this test to pass, it's enough to just declare a function with the name next you receive another requirement which is as follows except a keys variable, which should be set to true and console log the keys variable. So the requirement states the status of keys function should accept a previously declared keys variable, which should be set to true. The status of keys should then console log the value of the keys variable.

![[Pasted image 20250622003724.png]]

So you write another test which fails again since you have yet to write the implementation, you write it and your previously failing test now passes.

Finally, you examine your function code and realize that the indentation is all wrong. There are also too many unnecessary comments. So you clean up your code and run the test again to confirm that you haven't accidentally made any errors. The test still passes, so everything is okay. That is the TDD approach in a nutshell, let's go over it one more time.

![[Pasted image 20250622004106.png]]

![[Pasted image 20250622004045.png]]

