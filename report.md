# Part 1
I wrote the StringServer implementation under the class "SearchEngine" as it was mentioned in lab 2, since I had already made some progress on the concept of the assignment through SearchEngine. Here is the code for the server:

<img width="353" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/e453f521-9930-49b0-826d-7dc32598b4f9">

### Usages of "add-message":
### 1. "/add-message?s="hi"":
<img width="250" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/f2932b2a-149e-435e-a308-bd6c579677de">

In this instance, we use the add-message path to add the string "hi" (with String quotation marks included) to the wordList. In the Handler class, we called the handleRequest method which took the "add-message" path. The program used the ArrayList class to add the String "hi" to the ARrayList<String> object wordList.

### 2. "/add-message?s="""
<img width="300" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/571c4a1b-59b3-4379-8b23-996ddc9b0094">

In this example, we took the same path as the previous one, with the difference being that the String added to wordList is blank. As a result, wordList actually added the String consisting of two quotation marks instead of a blank String. Interesting!

<img width="426" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/57977f6d-5233-4e2f-803f-65d5bb4bf406">

# Part 2

<img width="374" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/5aee606c-8cc6-463a-9aad-fb285c08e6e1">

<img width="374" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/9619ed47-f719-4be1-95a6-4faf8895897c">

# Part 3

One thing I learned this week is that I can upload images directly to GitHub from my clipboard by using Ctrl C+V. Another thing I learned is how to use Java to handle url path queries. In the past, I've usually used HTML+Python to handle weppage logic.

