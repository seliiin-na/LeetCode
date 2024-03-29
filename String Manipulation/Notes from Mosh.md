## Common String Manipulation Techniques
1. reverse words in a string
```python
  # split a string into a list of words
  words = sentence.split(' ')

  # reverse the split string list and join using space
  rev_sentence = ' '.join(reversed(words))
```
2. check if `str2` is a rotation of `str1`
```python
  if str1 == None and str2 == None:
      return False

  # double str1, and check if str2 is part of that
  # bc rotations doesn't change order of letters
  return (len(str1) == len(str2) &&
          str2 in (str1 + str1))
```
3. if want to remove duplicates, use a *SET* to store keys/record seens <br>
   (dictionary _NOT_ needed bc no need to store value)

4. get the most repeated char from `str`
```python
    ASCII_SIZE = 256
    freq = [0] * ASCII_SIZE  # initialize list of specified size
    for i in str:
        freq[i] += 1
    # ...loop thru `freq` to find the max freq...
    # return the corresponding ASCII char of the index with max freq -> i.e. `chr(97)`
```



