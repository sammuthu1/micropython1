# Building a voice centric application with Amazon Alexa

**What are the benefits of voice?**

* 9.6 million adult Americans, age 65+, (~18.6%) reported having trouble seeing, even when wearing corrective lenses [2018 NHIS data](https://www.afb.org/research-and-initiatives/statistics/statistics-older-vision-loss/statistics-older-vision-loss-nhis).
* 24% of all adult Americans report doctor diagnosed arthritis [2021 CDC data](https://www.cdc.gov/chronicdisease/resources/publications/factsheets/arthritis.htm).
* Nearly 90 Million U.S. adults own a smart speaker [Apr 2020, Voicebot.ai](https://voicebot.ai/2020/04/28/nearly-90-million-u-s-adults-have-smart-speakers-adoption-now-exceeds-one-third-of-consumers/)
* Parity with UHG competitors: BCBS/Anthem, Cigna, & multiple independents

**How does the world view Alexa and our target demagraphic?**

* Saturday Night Live did a [faux commercial](http://www.nbc.com/saturday-night-live/video/amazon-echo/3518896?snl=1) for Alexa Silver, an Alexa designed for the greatest generation
* Amazon Alexa VP Toni Reid agreed that the [SNL spoof](https://www.geekwire.com/2017/amazon-alexa-chief-saturday-night-live-spoof-echo-speaker-actually-kind-spot/) is actually spot on
* Amazon recently released "Smart Properties" for [Senior Living Communities](https://www.youtube.com/watch?v=iUwEQnYr1wY) and [Healthcare Properties](https://www.youtube.com/watch?v=ZvEh_l2H64c)

**Let's define some terms**

Term | Definition
---------|----------
Wake Word | The word used to start an interaction with an Amazon device.  The current wake words are: Alexa, Echo, Amazon, and Computer
Invocation Name | The two or more word name that a user will use to start a dialog
Skill | An Alexa application that responds to and invocation
Intent | The action or request that a user can interact with
Utterance | The words that a user will use to invoke an intent
Slot | Custom values used in intents

**Voice Design**

* Design the skill to mimic human conversation: 	
    - Think through how  users will interact with  skill. 
    - Skipping this step will result in a skill that will not work well with  users.
* Do not use a flow chart to represent how a conversation may branch! 
    - Flow charts are not conversational. 
    - Instead of flow charts, use situational design.

**Situational Design**

* Situational Design is a voice-first method to design a voice user interface. 
    - Start with a simple dialog.
    - Each interaction between a user and the skill represents a turn. 
    - Each turn has a situation that represents the context. 
* If it's the user’s first time interacting with the skill, there is a set of data that is unknown. 
    - In this situation, the skill will ask basic questions, such as when were you born?
    - However, if this isn’t the first time, the skill should respond differently.
* Situational Design has four parts:
    - Utterance: What the user said
    - Situation: Context
    - Response: What Alexa says
    - Prompt: Question Alexa asks

**Date of birth / Birthday Counter Examples**

* Example 1:
    - Utterance: Open birthday counter
    - Situation: First time (unknown birthday)
    - Response: Hello.  Welcome to birthday counter
    - Prompt: When is your birthday?
* Example 2:
    - Utterance: Open birthday counter
    - Situation: Known birthday (today)
    - Response: Happy Birthday!
    - Prompt: N/A
* Example 3:
    - Utterance: Open birthday counter
    - Situation: Known birthday (not today)
    - Response: There are n days until your birthday
    - Prompt: N/A

**Some things to consider**

* When asking for a birthday, you want to be able to handle a full response (month, day, year) as well as a partial response (Under filling).  
    - [What happens if a user gives a partial answer?](https://www.youtube.com/watch?v=cn308bvNBq4&feature=youtu.be)
* Additionally, the user may give you too much information (Over filling).
    - [What happens if a user gives too much information?](
https://www.youtube.com/watch?v=Gr59BrDWnIE&feature=youtu.be)

**Tools to use**

* Birthday Counter Exercise:
    - [Cake Walk](https://developer.amazon.com/en-US/alexa/alexa-skills-kit/courses/cake-walk)
* Alexa Developer Console:
    - [Dev Console](https://developer.amazon.com/edw/home.html#/)
* Amazon Web Services:
    - [AWS](https://console.aws.amazon.com/console/home)
        - Lambda service – Hosts services
        - CloudWatch – Logs
* Blueprints:
    - [Blueprints](https://blueprints.amazon.com/)
* Skill Testing Tool:
    - [Echosim](https://echosim.io/welcome)

