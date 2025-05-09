# 🤖 Amazon Lex Bot – Book an Appointment

This project demonstrates how to build an Amazon Lex chatbot with a single intent: **Book an Appointment**. The bot collects information such as date, time, and type of appointment using conversational AI. Once all required slots are filled, it confirms the booking or passes the data to a Lambda function for processing.

---

## Key Features

- **Bot Name:** AppointmentBot
- **Intent Name:** BookAppointment
- **Slots Used:**
  - `AppointmentType` (e.g., Doctor, Dentist, Interview)
  - `Date` (Amazon built-in slot type: `AMAZON.Date`)
  - `Time` (Amazon built-in slot type: `AMAZON.Time`)
- **Lambda Fulfillment (Optional):** Simulates booking logic and returns confirmation
- **Response Prompts:** Engaging, user-friendly prompts for slot elicitation

---

## 🛠️ Setup Steps

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

## 🧠 What I Learned

- Building conversational interfaces using Amazon Lex
- Slot management and custom slot types
- Designing user-friendly prompts and confirmations
- (Optional) Integrating Lex with AWS Lambda for dynamic fulfillment

---

## 📌 Status

   - Bot is fully functional and tested with Lex V2.  
⚙️ Optional: Can be enhanced with calendar integration or backend database (e.g., DynamoDB) for storing appointments.

---

## 📁 Files

