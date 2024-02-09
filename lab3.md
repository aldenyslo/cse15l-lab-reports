# Lab Report 3

## Part 1 - Bugs

The method I'm testing is the `ArrayList` `reversed()` method.

### Failure Input

```
@Test
  public void testReversed() {
    int[] input1 = {1,2,3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
  }
```

### No Failure Input

```
@Test
  public void testReversed() {
    int[] input2 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input2));
  }
```

### Symptom

![Image](screenshots/symptom.png)

### Bug

Before:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = newArray[arr.length - i - 1];
    }
    return newArray;
  }
```

After:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The fix addresses the issue as the old code overwrites the original array with the new array populated
with only 0s. THe fix switches that around so that it is the new array that is being edited, not the original one.

## Part 2 - Researching Commands


