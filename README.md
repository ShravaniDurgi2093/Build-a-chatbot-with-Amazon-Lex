# Build-a-chatbot-with-Amazon-Lex
This is project 1 of AI and AWS five series projects

Amazon Lex:
✔ Easily add AI that understands intent, maintains context, and automates simple tasks across many languages.
✔ Design and deploy omnichannel conversational AI in one click, without worrying about hardware or infrastructure.
✔ Connect seamlessly with other AWS services to query data, execute business logic, monitor performance, and more.
✔ Pay only for speech and text requests with no upfront costs or minimum fees.
In short: It is a tool that helps in creating programs that can talk or chat with people like Siri or Alexa. It understands what people say or type and helps the bot respond in a useful way.
Project Summary: Let's create our very own banking chatbot using Amazon Lex and Amazon Lambda, to build something interactive.
Note: Delete all the resources at the end of the day.
AWS Service: Amazon Lex
Project Steps:
1.	Login into your AWS account
2.	Search for Amazon Lex
3.	My region was Ohio, so an alert box popped up saying in United States its available only in two regions.
 
4.	Click Create Bot. Then we are going to create a traditional bot.
5.	Then, choose Create a blank bot.
6.	For Bot name, enter the name you want to  and enter the description of the bot.
 
7.	Under IAM permissions, select Create a role with basic Amazon Lex permissions.
Why do we need Amazon Lex permissions?
Amazon Lex needs the permission to call other AWS services on your behalf, later in this project series you'll be integrating Lex with another service called Lambda!
 
8.	Under Children’s Online Privacy Protection Act (COPPA), select No.
9.	Under Idle session timeout, keep the default of 5 minutes.
What does Idle session timeout mean?
Amazon Lex will only maintain a session for a set length of time. If the user is idle and doesn't add any input for 5 minutes, their session will end.
10.	Select Next.
11.	Now we're going to play around with your bot's voice.
12.	Keep the language as English so you can explore Lex's full set of features in this project.
13.	Under Voice interaction, click on the dropdown that says Danielle. Click around different voice options to choose your favorite one!
 
These voices are borrowed from Amazon Polly, which is another AWS service all about turning your text into speech!
14.	For Intent classification confidence score threshold, keep the default value of 0.40.
What is intent classification confidence score threshold?
When you're using Amazon Lex to build a chatbot, this threshold is like a minimum score for your chatbot to confidently understand what the user is trying to say.
Setting this to 0.4 means that your chatbot needs to be at least 40% confident that it understands what the user is asking to be able to give a response.
So if a user's input is ambiguous and your chatbot's confidence score is below 0.4, it'll throw an error message.
15.	Click Done.
16.	Then, an Intent page is automatically seen.
 


What are intents?
An intent is what the user is trying to achieve in their conversation with the chatbot. For example, checking a bank account balance; booking a flight; ordering food.
In Amazon Lex, you build your chatbot by defining and categorising different intents. If you set up different intents, one single chatbot can manage a bunch of requests that are usually related to each other.

 
17.	Under Intent details, enter WelcomeIntent for the Intent name.
18.	Add the description Welcoming a user when they say hello.
19.	Under Intent details, enter WelcomeIntent for the Intent name.
20.	Add the description Welcoming a user when they say hello.
21.	Copy the text below, which represent the user inputs (called utterances) that will trigger this intent, and paste it into the text window:
Hi
Hello
I need help
Can you help me?
22.	Click back to the Preview button to see these utterances in chat form.
23.	Scroll down to Closing response, and expand the arrow for Response sent to the user after the intent is fulfilled.
24.	In the Message field, enter the following message:
Hi! I'm BB, the Banking Bot. How can I help you today?
25.	Choose Save intent.
26.	Choose Build, which is close to the top of the screen.
 

27.	Choose Test.
28.	The following dialog will pop up, and you can interact with the bot by entering your opening message.
 
29.	We can try different utterances.
How does my chatbot respond to these user inputs?
The first three are successfully recognized - Amazon Lex is able to use its ML techniques to match what you have said against your utterances.
But the last two fail, resulting in an Intent FallbackIntent is fulfilled response - meaning Amazon Lex doesn't quite recognize your utterance. We'll learn what FallbackIntent means in the next step.
 
30.	Lets manage the FallbackIntent
31.	Customise FallbackIntent to send user-friendly messages.
32.	In your left hand navigation panel, choose FallbackIntent.
 
What is FallbackIntent?
Remember the intent classification confidence score threshold, and how it's been set to 0.4?
If your chatbot has a confidence score below 40% for all the intents you've defined (in our case, it's just the WelcomeIntent for now), the FallbackIntent is triggered.
Think of it as a custom error message that your chatbot will use to tell the user it doesn't understand their input.
33.	The default FallbackIntent message you saw just now ("Intent FallbackIntent is fulfilled") can be a little confusing.
34.	Let's re-phrase that message so it's clearer to the user that your chatbot doesn't understand the user's request.
35.	Scroll down to Closing responses.
36.	Expand the arrow for Response sent to the user after the intent is fulfilled.
37.	In the Message field, add the following text:
38.	Sorry I am having trouble understanding. Can you describe what you'd like to do in a few words? I can help you find your account balance, transfer funds and make a payment.
39.	You can add different variations.
 
What are variations?
Variations are literally variations of the same Message in the main Message box. When Amazon Lex needs to return a Fallback response, it will randomly choose a message from the group and return that.
Variations will give your users a dynamic range of responses, making them sound more conversational!
40.	Choose Save intent.
41.	Choose Build
 
42.	Let's test 2-3 message that failed in your last try.

 

