# 🤖 Amazon Lex Bot – Book an Appointment
![AWS](https://img.shields.io/badge/Built%20with-AWS-orange?style=flat&logo=amazonaws)![Project Status](https://img.shields.io/badge/status-finished-green)

This project demonstrates how to build an Amazon Lex chatbot with a single intent: **Book an Appointment**. The bot collects information such as date, time, and type of appointment using conversational AI. Once all required slots are filled, it confirms the booking or passes the data to a Lambda function for processing.

---

## Key Features

- **Bot Name:** AppointmentBot
- **Intent Name:** BookAppointment
- **Slots Used:**
  - `AppointmentType` (Doctor, Dentist, Interview)
  - `Date` (Amazon built-in slot type: `AMAZON.Date`)
  - `Time` (Amazon built-in slot type: `AMAZON.Time`)
- **Lambda Fulfillment (Optional):** Simulates booking logic and returns confirmation
- **Response Prompts:** Engaging, user-friendly prompts for slot elicitation

---

##  Setup Steps

<img align="right" alt="Coding" width="600" src="https://github.com/Juniorklb/Amazon-Lex-bot/blob/7d7d7fb4702eb117b1b75bc88b641ba4f10fb763/Images/LEXBOX.PNG">

1. **Create a new bot** in Amazon Lex V2 
2. **Create an intent** named `BookAppointment`
3. Add sample utterances:
   - “I need to book an appointment”
   - “Schedule an appointment for tomorrow at 3 PM”
4. **Define slots:**
   - AppointmentType – Custom slot type (Doctor, Dentist, etc.)
   - Date – `AMAZON.Date`
   - Time – `AMAZON.Time`
5. **Set up responses:**
   - Prompt user to provide missing slot values
   - Confirmation message after all values are gathered
6. **(Optional)** Attach a Lambda function for fulfillment
7. **Build and test the bot** in Lex test window
8. **Create version & alias** to publish your bot
9. **Integrate** with Amazon Connect, website chat widget, or Slack

---
## Step 1: Create the Lex Bot & Define Intent

**A. Go to Amazon Lex Console (V2)**
- Link: [https://console.aws.amazon.com/lexv2/](https://ca-central-1.console.aws.amazon.com/lexv2/home?region=ca-central-1#bots)

- Click **“Create bot”**
**B. Configure Bot Settings**
- Bot name: AppointmentBot
  
![image alt](https://github.com/Juniorklb/Amazon-Lex-bot/blob/397f2078ed328a89c5bab22dc291cfe69a9b41dd/Images/lexxyboy.PNG)

- IAM Role: Create a new role with basic Lex permissions
  
![image alt](https://github.com/Juniorklb/Amazon-Lex-bot/blob/a8312789a2ee12bf800391fc2376fff3ccb0a2f9/Images/prettyboylex.PNG)
- Language: English (US)

- Children-directed: No

- Sentiment analysis: Off (you can enable it later if needed)

- Idle session timeout: 5 minutes (default is fine)

- Click Next

**C. Add an Intent**
- Click **“Add intent”** → choose **“Create intent”**

- **Intent name**: ``BookAppointment``

- Save it for now — we’ll define slots and utterances in the next step.

## Step 2: Define Slots and Sample Utterances
#### 🗣️ A. Sample Utterances
- In the BookAppointment intent, add a few training phrases (utterances) to teach Lex what users might say:
  
``I want to book an appointment``

``Schedule an appointment for {Date} at {Time}``

`` Book a {AppointmentType} appointment on {Date}``

``I need to see a {AppointmentType} at {Time}``

``Can I get a {AppointmentType} appointment tomorrow?``

**B. Define Slots**
You'll add three slots: ``AppointmentType, Date, and Time.``

1. ``AppointmentType``
   
- Slot name: ``AppointmentType``

- Slot type: Custom (create a slot type)

   - Click "Add slot type"

   - Name: ``AppointmentTypeValues``

   - Values: Doctor, Dentist, Therapist, Interview, Haircut

- Prompt: “What type of appointment would you like to book?”

2. ``Date``
  - Slot name: ``Date``

  - Slot type: ``AMAZON.Date``

  - Prompt: “On what date do you want the appointment?”

 3. ``Time``
   - Slot name: ``Time``

   - Slot type: ``AMAZON.Time``

   - Prompt: “What time works best for your appointment?”

###  Confirmation Prompt (Optional) 
- You can enable confirmation before fulfillment:

   - Prompt:
     “Just to confirm, you want to book a {AppointmentType} appointment on {Date} at {Time}, right?”

- Decline response:
   “Okay, I’ve canceled the appointment request.”

## Step 4: Test Your AppointmentBot
**A. Build the Bot**
- In the Lex V2 console, click your bot: AppointmentBot

- Go to the "Build" tab at the top right.

- Click “Build” to compile your bot and intents.

   - This may take a minute or two.
     
**B. Test in the Console**

- Once the build is complete, go to the “Test” window (on the right side)

- Try typing phrases like:

   - “I need to book an appointment”

   - “Book a dentist appointment for Friday at 2 PM”

**The bot should:**

- Prompt for any missing slots ( time or type)

- Confirm the details

- (If configured) simulate fulfillment

## What we Learned
- Building conversational interfaces using Amazon Lex
- Slot management and custom slot types
- Designing user-friendly prompts and confirmations
- (Optional) Integrating Lex with AWS Lambda for dynamic fulfillment

---

##  Status

   - Bot is fully functional and tested with Lex V2.  
⚙️ Optional: Can be enhanced with calendar integration or backend database (e.g., DynamoDB) for storing appointments.

---

## Conclusion
This project showcases a simple appointment booking chatbot using Amazon Lex V2 with Lambda fulfillment. It collects appointment details like type, date, and time, then confirms the booking using a Lambda function — demonstrating how to build smart, conversational interfaces on AWS.

