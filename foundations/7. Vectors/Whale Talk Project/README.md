# Whale Talk Project

1. Let’s create a skeleton for the program. Add:

```
#include <iostream>
#include <vector>
#include <string>

int main() {

  // Whale, whale, whale.
  // What have we got here?

}
```

2. First things first, you need an input string for the program to translate.

	Declare a ```std::string``` and initialize it with ```"turpentine and turtles"``` or anything you’d like.

3. Whales only speak in vowels so you need a vector of vowels to be extracted from the ```input``` variable.

	Create a ```char``` vector named ```vowels``` and give it values of:

	- ```a```
	- ```e```
	- ```i```
	- ```o```
	- ```u```

	**Note**: Whales don’t consider ‘y’ a vowel.

4. Create another vector named ```result```.

	This will serve as a place to store the vowels from the input string (the translated whale talk).

5. So now that we have:

	- The input string
	- The vowels
	As well as a place to store the resulting ```char```s.

	Let’s think about the logic for a minute.

	We want to loop through the input string and check if each of the characters is a vowel.

	Let’s first write a ```for``` loop that iterates through the input string.

6. But how to check if each of the characters is a vowel? Well, we have to compare *each* of the characters with *each* of the vowels.

	So we need another loop inside. One loop inside another loop is called a **nested loop**!

	Inside your current ```for``` loop, write another ```for``` loop inside that iterates through the ```vowel``` vector.

	**Note**: Use a different counter variable for the inner loop.

7. So now as you have a nested ```for``` loop, compare each of the characters with each vowels.

	Write an ```if``` statement that compares ```input[i]``` with ```vowels[j]```.

	If they are equal, add the character to the ```result``` vector using ```.push_back()```.

8. To check your work, write another ```for``` loop that goes through the ```result``` vector and outputs each of the elements.

	The output should look something like:

```
	ueieaue
```

	We now have all the vowels!

9. Whales double the ```e```s and the ```u```s in their language.

	Write an ```if``` statement that checks if each letter in the ```input``` string is equal to ```'e'```. If so, ```.push_back()``` ```input[i]``` to the ```result``` vector.

	**Note**: This statement belongs *after* the inner ```for``` loop block, but still *inside* the outer ```for``` loop. This is because you only want to perform this check once for every letter in the input.

10. Run the program and sing the output out loud — you officially speak whale!

	To confirm, if your ```input``` string is “turpentine and turtles”, the whale version would read: ```'uueeieeauuee'```.

	Try other tests like ```'hi, human'``` (to get ```iuua```) or ```'a whale of a deal!'``` (to get ```'aaeeoaeea'```).

Example code can be found in the [whale.cpp](https://github.com/keldavis/c-plus-plus-practice/blob/master/foundations/7.%20Vectors/Whale%20Talk%20Project/whale.cpp) file.