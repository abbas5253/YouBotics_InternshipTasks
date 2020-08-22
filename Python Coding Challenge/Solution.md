<b>Problem Statement:</b>

Write a function that divides a sentence into word container with each
container containing "n" or fewer characters. Only include "full words"
inside each container.

<b>Code:</b>

```python
def split_into_container(input_string: str, n: int,) -> list:
    """
    Args:
        input_string: string to be parsed 
        n: max length of each word container
        
    Return:
        word_container: list of strings
    """
    
    #convert the string into list of words
    wordList = input_string.strip().split()
    
    #initialize list to be returned
    word_container = []
    
    #initialize current word container 
    cur_word = wordList[0]
    cur_len = len(wordList[0])
    
    #check length
    if(cur_len > n):
        return []

    #initialize pointer
    idx = 1
    
    #iterate over each word
    while(idx < len(wordList)):
        
        #check length
        if(len(wordList[idx]) > n):
            return []
        
        #new length if current word is added i.e, cur_word + space + new_word
        new_len = cur_len + 1 + len(wordList[idx])
        
        #check length
        if(new_len > n):
            word_container.append(cur_word) #add to container list
            
            #initialize new element
            cur_word = wordList[idx]
            cur_len = len(wordList[idx])
        else:
            cur_word += ' ' + wordList[idx] #add to current string
            cur_len  =  new_len #update length
            
        #increament pointer
        idx = idx+1
        
    #insert the last word
    word_container.append(cur_word)
            
    return word_container
```
<b>Tests:</b>
```python
>>> print(split_into_container("she sells sea shells by the sea", 10))
['she sells', 'sea shells', 'by the sea']
>>> print(split_into_container("the mouse jumped over the cheese", 7))
['the', 'mouse', 'jumped', 'over', 'the', 'cheese']
>>> print(split_into_container("ab ba ca", 1))
[]
```

