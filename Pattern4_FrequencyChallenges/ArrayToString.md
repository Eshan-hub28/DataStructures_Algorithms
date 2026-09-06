Method 1: Using StringBuilder

Syntax:

StringBuilder sb = new StringBuilder();
for(String word : words){
    sb.append(word);
}
String result = sb.toString();

code:

String[] words = {"bella", "label", "roller"};
StringBuilder sb = new StringBuilder();
for(String word : words){
    sb.append(word);
}
String result = sb.toString();
System.out.println(result);

Method 2: Using String.join()

Syntax:

for space:

String result = String.join(" ", words);

without space:

String result = String.join("", words);
System.out.println(result);