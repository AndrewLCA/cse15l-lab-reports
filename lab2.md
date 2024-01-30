# Lab Report 2 - Servers and SSH Keys 

**Code for ChatServer** 

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.*;  
class Handler implements URLHandler {
ArrayList<String> chat = new ArrayList<String>();
    public String handleRequest(URI url) {   
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("[=&]");
                if (parameters[0].equals("s") && parameters[2].equals("user")) {
                    String a = (parameters[3]);
                    String b = (parameters[1]); 
                    String c = a + ":" + " " + b; 
                    chat.add(c); 
                    String d = "";
                    for(int i =0; i < chat.size(); i++)
                    {
                        d += chat.get(i) + "\n";   
                    }
                    d = d.replaceAll("\\+", " "); 
                    //System.out.println(d);
                    return d;
                }
            }
           return "404 Not Found!"; 
        }
    }
class NumberServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```
**Screenshots of /add-message**

![image](Lab 2 ss1.png)

The methods that are called in the first `/add-message` is an array of `parameters` which are separated by the symbols `=` and `&`. This would separate each of the strings we input as indexes of the array. The relevant argument for this method is `s` which signals the first index of the array `parameter[0]` separated by `=` which then indicates the second index of the array `parameter[1]`. `&` also separates the indexes of the array so `&user` would be considered the third index `parameter[2]` and after `&user=` would be considered the fourth index, `parameter[3]`. A new string variable `c` is then created which is the append of `parameter[0]` and `parameter[1]` in the format of `<user>: <message>`. We then create an ArrayList `chat` and using a for loop, push `c` into the `chat`. Since we inputted the argument `/add-message?s=Hello what did you do today&user=Andrew`, `parameter[0]` would be `s`, `parmeter[1]` would be `Hello what did you do today`, `user` would be `parameter[2]`, and `Andrew` would be `parameter[3]`. This would change the value of `String a` to `parameter[3]` and `String b` to `parameter[1]`. `String c` would append both `a` and `b` and get pushed to the first index of `chat`. 

![image](Lab 2 ss2.png)

The methods that are run in this screenshot would be the same as what was stated in the screenshot above. Same with the relevant arguments for those methods. `/add-message?s=I played tennis today!&user=Theo` would have `String a` as `I played tennis today!` and `String b` as `Theo`. `String c` would concatenate both `a` and `b`. `c` would then get pushed into ArrayList `chat`. One difference here is that the message from the first screenshot is the first element of `chat` so this new message would be the second element of `chat`. Using a for loop we  move both elements into `String d` and separate each element with a new line `\n`. 

