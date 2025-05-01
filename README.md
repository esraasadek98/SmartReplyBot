# SmartReplyBot
This UiPath project automates smart email replies by:

Receiving customer emails.

Analyzing the tone of the email using Google Gemini (GenAI).

Generating a context-based reply.

Sending the reply back via SMTP.

Logging the response status (SMTP 250 OK)

# Main Workflow – Main.xaml Summary
1. ReceiveMail.xaml
Fetches incoming emails (lIMAP).

Outputs:

emailBody

emailSender

emailSubject

2. AnalyzeTone.xaml
Sends the emailBody to Gemini AI.

Asks for the tone in one word ("happy", "angry").

Returns the tone via toneReply.

3. GenerateReply.xaml
Constructs a reply based on:

Email Body

Identified tone

Uses GenAI or templates to build the response.

4. SendReply.xaml
Uses SMTP to send the generated reply.

Inputs:

in_ReplyBody

in_EmailReciever

in_EmailSubject

If successful, returns status code 250 OK from the SMTP server.

Status is tracked via out_SendStatus.

How to Run
Open Main.xaml in UiPath Studio.

Ensure your email account and Gemini API settings are configured.

Run the workflow.


