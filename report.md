## Part 1
I wrote the StringServer implementation under the class "SearchEngine" as it was mentioned in lab 2, since I had already made some progress on the concept of the assignment through SearchEngine. Here is the code for the server:

import java.io.IOException;
import java.net.URI;
import java.util.*;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> wordList=new ArrayList<String>();
    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    wordList.add(parameters[1]);
                    return "String "+parameters[1]+" added!";
                }
                else{
                    return "No argument given";
                }
            }
        else{
            String res="";
            for(String word:wordList){
                res=res+word+"\n";
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

