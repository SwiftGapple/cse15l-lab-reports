The failure-inducing input (the code of the test)
The symptom (the failing test output)
The bug (the code fix needed)
Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?

# List Method (ArrayExamples)
* Failure inducing input: 'ArrayExamples.reversed([1,2,3])' or any non-empty array

![Image](lab3img/1.png)
* Symptom: the resulting array are all zeros '[0,0,0]'

* Explain: the reversed method has two bugs. The first one is that it creates a new empty array and assigns in indices from the blank arry to the input array. This is why the output array is all zeros. The new array is set by default to be all zeros. The part `array[i] = newArray[arr.length - i - 1]' is bug. Secondly, the method modifys and outputs the original array instead of outputs the new array.

![Image](lab3img/2.png)
* ^ Fixed code

# ListExamples (filter)
* Failure inducing input: an list of String with length longer than 1




