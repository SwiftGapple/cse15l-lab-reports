The failure-inducing input (the code of the test)
The symptom (the failing test output)
The bug (the code fix needed)
Then, explain the connection between the symptom and the bug. Why does the bug cause that particular symptom for that particular input?

# List Method (ArrayExamples)
* Failure inducing input:
'''
  @Test
  public void testReversed02(){
    int[] input2 = {1, 2, 3};
    int[] input2Reversed = {3, 2, 1};

    assertArrayEquals(input2Reversed, ArrayExamples.reversed(input2));
    assertArrayEquals(new int[]{1, 2, 3}, input2);
  }
  '''


![Image](lab3img/1.png)
* Symptom: the resulting array are all zeros '[0,0,0]'

* Explaination: the reversed method has two bugs. The first one is that it creates a new empty array and assigns in indices from the blank arry to the input array. This is why the output array is all zeros. The new array is set by default to be all zeros. The part `array[i] = newArray[arr.length - i - 1]' is bug. Secondly, the method modifys and outputs the original array instead of outputs the new array. It should return 'newArray' instead of returning 'arr'.

![Image](lab3img/2.png)
* ^ Fixed code

# ListExamples (filter)
* Failure inducing input: an list of String with length longer than 1
* For example: '["fun", "cse", "yes", "ok"]' with StringChecker having strings  '["fun", "cse", "yes"] '

![Image](lab3img/3.png)
* Symptom: the resulting array does not match the expected outcome. The order is backward.

* Explaination: the bug is that 'result.add(0, s)', where the code adds the string to the 0 index of the list. Due to the property of list, every time a new string is added, the existing strings will be pushed back. Thus, the resulting list is backward and does not match the expected result.

![Image](lab3img/4.png)
* ^ Fixed code









