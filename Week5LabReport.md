![image](https://github.com/Gabriel-Ren/cse15l-lab-reports/assets/156254424/ed921602-f787-4adb-8645-a66fb41ad115)# Week 5 Lab Report by Gabriel Renslow

# `Part 1 - Bugs`

# Failure Inducing Test
```int[] input1 = { 1, 2, 3 };```
```ArrayExamples.reverseInPlace(input1);```
```assertArrayEquals(new int[]{ 3, 2, 1 }, input1);```

# Non-Failure Inducing Test
```int[] input1 = { 3 };```
```ArrayExamples.reverseInPlace(input1);```
```assertArrayEquals(new int[]{ 3 }, input1);```

# Sympton

![Image](Week5_Part1.png)

# Bug/Solution

Before
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

After
```
static void reverseInPlace(int[] arr) {
    int[] temp = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      temp[i] = arr[arr.length - i - 1];
    }
    for(int i = 0; i < arr.length; i +=1) {
      arr[i] = temp[i];
    }
  }
```




This command allows me to login to my ieng6 environment so I can begin the lab report.

# `Part 2 - Researching Commands`

![Image](week7_Part5-Copy.png)

Keystrokes: ```git clone <ctrl>+v<enter>```

This command allows me to clone my github repo into the environment so I can begin work on it. Ctrl+V was used to copy paste my repo link.

