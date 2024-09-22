# GPT BLOGGER

A simple command line AI tool which you can use to write blogs. 

## About the Project
I built this as my final coding project as part of the ```Codedex Python Certification```

## Technologies used

1. ```Python```
2. ```OpenAI module ```
3. ```Dotenv module```

This project requires paid openAI credits which is why I have not comitted my openAI key in the repository to protect te credits.

#### An overview of how the project works
The ```openai.api_key = config['API_KEY']``` calls for the hidden API key in the ```.env``` file, which I have added in the **gitignore** file


``` 
def generate_blog(paragraph_topic):
  response = openai.completions.create(
    model = 'gpt-3.5-turbo-instruct',
    prompt = 'Write a paragraph about the following topic. ' + paragraph_topic,
    max_tokens = 400,
    temperature = 0.3
  )
```
This thing above defines our chat gpt model, although I can change it if I want.
- The **prompt =** gives the predefined sentence prompt to our gpt, with us just needing the topic from the user.
- The max_tokens basically defines how big our answers can be, and 400 is very big. 400 is not the number of characters or words by the way.
> And there is a reason I am not defining the ```temperature``` here.



```
user_input = input("Give the topic you want to know about: ")
print(generate_blog(user_input))
```
The above code is pretty obvious I think

## But wait. The user wants to know more?

That's when our loop comes into play. We are obviously not gonna just only let the user ask us once.

> Not that I am in any shortage of openAI credits. And if I was, you wouldn't know about it anyway.   
   
```   
while keep_writing:
  answer = input('Write a paragraph? Y for yes, anything else for no. ')
  if (answer == 'Y'):
    paragraph_topic = input('What should this paragraph talk about? ')
    print(generate_blog(paragraph_topic))
  else:
    keep_writing = False
```

Actually, openAI API pricing is really genuine, unless you are planning to build an industry level application.


## What if you want to run the project using your own API key?   

Don't worry, I gotchu.

- create a ```.env``` file in the project folder
  and Add this simple line there

```
API_KEY=yourapikey
```

## LAST BUT NOT THE LEAST
If anybody wants to solve the problem of using your own API key, I will be happy to accept any PR which accomplishes the following:
- The project uses my API key rather than people having to provide their own
- My API keys stays safe and unexposed to the person such that anybody from anywhere can download this project and use it with my API key, provided that they are not able to see my API key.
- Also I want to be abe to convert the python file to ```.exe``` format so that any person can download the project and use it, not just people with python installed on their computers.
- There is also an open issue in the repo regarding this
