# Part 1
I wrote the StringServer implementation under the class "SearchEngine" as it was mentioned in lab 2, since I had already made some progress on the concept of the assignment through SearchEngine. Here is the code for the server:

	import java.io.IOException;
	import java.net.URI;
	import java.util.*;
	class Handler implements URLHandler {
	    // The one bit of state on the server: a number that will be manipulated by
	    // various requests
	    ArrayList<String> wordList=new ArrayList<String>();
	    public String handleRequest(URI url) {
	        if (url.getPath().contains("/add-message")) {
	            String[] parameters = url.getQuery().split("=");
	                if (parameters[0].equals("s")) {
	                    wordList.add(parameters[1]);
	                    String res="";
	                    for(int i=0;i<wordList.size();i++){
	                        res=res+(i+1)+". "+wordList.get(i)+"\n";
	                        }
	                    return res;
	                }
	                else{
	                    return "No argument given";
	                }
	            }
	        else{
	            String res="";
	            for(int i=0;i<wordList.size();i++){
	                res=res+(i+1)+". "+wordList.get(i)+"\n";
	            }
	            return res;
	
	        }
	        }
	    }
		
	 class SearchEngine {
	    public static void main(String[] args) throws IOException {
	        if(args.length == 0){
	            System.out.println("Missing port number! Try any number between 1024 to 49151");
	            return;
	        }
	
	        int port = Integer.parseInt(args[0]);
	
	        Server.start(port, new Handler());
	    }
	}

### Usages of "add-message":
### 1. "/add-message?s="hi"":
![image](https://github.com/wangharold001/cse15-report2/assets/60553459/3819823a-0d17-43ee-af36-726be75c7976)

In this instance, we inputted to the handleRequest method the path "add-message/s=hi". The method takes us to the add-message condition path, where we passed the parameter[0], which was "s", and then added parameter[1], the string "hi", to the wordList.  The program used the ArrayList class to add the String "hi" to the ArrayList <String> object wordList.

### 2. "/add-message?s="""
![image](https://github.com/wangharold001/cse15-report2/assets/60553459/812e24c2-6878-4c6c-8d4d-5437ab9100d9)

We inputted to the handleRequest method the path "add-message/s=""\\". The method takes us to the add-message condition path, where we passed the parameter[0], which was "s", and then added parameter[1], the string """\\", to the wordList.  The program used the ArrayList class to add the String """\\" to the ArrayList <String> object wordList.
In this example, we took the same path as the previous one, with the difference being that the String added to wordList is a collection of special characters. However, wordList as an ArrayList<String> accepts it as input regardless.

# Part 2

<img width="374" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/5aee606c-8cc6-463a-9aad-fb285c08e6e1">

<img width="374" alt="image" src="https://github.com/wangharold001/cse15-report2/assets/60553459/9619ed47-f719-4be1-95a6-4faf8895897c">


Here is the path to the public and private keys on my computer:
![image](https://github.com/wangharold001/cse15-report2/assets/60553459/964c6404-21bf-4313-857f-7f35827fa4f4)

# Part 3

One thing I learned this week is that I can upload images directly to GitHub from my clipboard by using Ctrl C+V. Another thing I learned is how to use Java to handle URL path queries. In the past, I've usually used HTML+Python to handle webpage logic.

