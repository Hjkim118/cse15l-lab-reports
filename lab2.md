Part 1

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class Handler implements URLHandler {
    List<String> messages = new ArrayList<>();
    int num = 1;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.join("N/A", messages);
        } else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("s=");

            if (parameters.length == 2) {
                String message = parameters[1];
                String fMessage = num + ". " + message;
                messages.add(fMessage);
                num++;
                return String.join("\n", messages);
            }
        }
        return "404 Not Found";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

![Image](lab2_1.png)
1. Methods Called: A GET request is made to /add-message?s=Hello. In handleRequest, a used query that splits into two by the '=' sign and assigns it to each parameter. Saved the 2nd parameter into messages. Also if /add-messages is contained continue the process.
   
2. Relevant Arguments: The request URL contains the query parameter s=Hello. 
   
3. Values of Relevant Fields:
array messages is initially an empty array.
num is initially 1. This is changed by num++ in the file.
Change in Relevant Fields: After this specific request, messages contain the string "1. Hello\n" and the num is incremented to 2.

![Image](lab2_2.png)
Screenshot 2: Adding "How are you"

Methods Called: A GET request is made to /add-message?s=Hi. In handleRequest, the used query splits into two by the '=' sign and assigns it to each parameter. Saved the 2nd parameter into messages. Also if /add-messages is contained continue the process.

Relevant Arguments: The request URL contains the query parameter s=Hi. 

Values of Relevant Fields:

messages contain "1. Hello\n".
num is 2.
Change in Relevant Fields: After this specific request, messages contain "1. Hello\n 2. Hi\n" and num is incremented to 3.

Part2

The path to the private key for your SSH key for logging into ieng6 (on your computer or on the home directory of the lab computer)
![Image](lab2_ch1.png)

The path to the public key for your SSH key for logging into ieng6 (within your account on ieng6)
![Image](lab2_ch2.png)

A terminal interaction where you log into ieng6 with your course-specific account without being asked for a password.
![Image](lab2_2_3.png)

Part3

In lab week2,3, I learned more deeply about connecting to a remote computer from my local computer. Also, I did not know how a query was used before these two weeks and now I have an idea about how these are used in practical coding.
Another thing that is related to remote computers is having and saving authorized keys in my computer and remote computer and using them to save passwords to shorten the time to log into remote computers. 
Also, I learned other different commands such as mkdir for more purpose of making directories, copying files, and more skills related to terminal commands.
