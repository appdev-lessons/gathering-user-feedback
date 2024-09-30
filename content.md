# User Feedback: Techniques for Effective User Conversations

In this lesson, we'll explore techniques for engaging with users to gather meaningful feedback, ensuring your product meets their needs. The goal is to **make something people actually want**. People *will* lie to you. (They don't want to hurt your feelings) It is your job to make sure you get useful information to make informed product decisions.

## Objectives

- Understand the importance of user feedback in product development.
- Learn effective methods for conducting user interviews.
- Develop skills to interpret user feedback.

## Introduction

> "If I had asked people what they wanted, they would have said faster horses." — Henry Ford  
> "A lot of times, people don’t know what they want until you show it to them." — Steve Jobs

It's important to talk to users, even if their desires might not be immediately clear. Actions also speak louder than words. So listen to what users say, but, more importantly, notice what they do.

## The Importance of User Feedback

Best developers maintain a direct connection to users. A lack of user feedback can signal a problem in the development process. At larger companies, it is common to have many layers in between the user and the developer: customer service, sales, automated support, designers, researchers, etc. Have you ever called tech support and talked to the actual person who makes the product? 

There is a direct connection between exposure to users and building better products. Jared Spool talks about this in [Fast Path to a Great UX: Increased Exposure Hours](https://www.linkedin.com/pulse/fast-path-great-ux-increased-exposure-hours-jared-spool/). Each team member has to be exposed directly to the users themselves. Teams that have dedicated user research professionals, who watch the users, then in turn, report the results through documents or videos, don't deliver the same benefits. It's from the direct exposure to the users that we see the improvements in the design.

## The mistake you will make

> You will make up some idea in your head that you will call your *vision*. And then you will spend a lot of time thinking about your vision in a cafe by yourself and build some elaborate thing without going and talking to users because that’s doing sales, which is as pain and they might say no. You will not ship fast enough because you’re embarrassed to ship something unfinished and you don’t want to face the likely feedback you will get, so you will shrink from contact with your users. When in reality, you’d be better off finding someone with a problem they will pay you to fix and then seeing if you can find more people like that. The best case scenario is that it’s a problem you yourself have.
> 
> [Paul Graham](https://x.com/StartupArchive_/status/1779842017818038308)

## The Product Development Lifecycle

A typical product development lifecycle looks something like this:

1. Idea 💡
2. Launch something 🚀
3. Talk to users to see if it serves their needs 🗣️
4. Repeat 🔁

You want to optimize for speed of delivery, iterating your product towards something people actually want.

## Listening to Users

- Listen for user problems (You can usually ignore their proposed solutions). Your user owns their problem, you own the solution.
- **Focus on actions over words**: Understand what users do, not just what they say.
- If users are "hacking" your product, pay attention to that behavior.

## The Mom Test

![](assets/mom-test.webp)

[The Mom Test](https://www.momtestbook.com/) is a guide on how to conduct user interviews effectively and interpret the feedback (even when everyone is lying to you). It's very common to have a conversation that goes something like this:

- **you**: Hey, my new app idea is ...
- **friend**: Wow, that's super cool!
- **you**: bla bla bla bla
- **friend**: Amazing,... billion dollar idea
- (months later)
- **you**: We just launched, will you buy?
- **friend**: (...crickets...)

This is a totally useless conversation. Your friend is trying to be supportive and doesn't want to hurt your feelings. You didn't ask any questions to validate that you're building something useful or that your friend wants it. If you formulate good questions, you should be able to ask even your Mom and get useful data points. You don't want to spend your time working on something that nobody actually wants.


### Guidelines for User Conversations

- Discuss their lives, not your product.
- Ask about real experiences, not hypotheticals. (avoid "would")
- Listen more than you speak.


#### DOs
- Plan the 3 most important questions you want to investigate. The answers to these questions should terrify you and potentially disprove your idea. Try to form the rest questions around these questions. These questions may be different for each type of person you’re talking to.
- Start from broad questions and then zoom in until you’ve found a strong signal. Mix generic and specific questions during your conversation. These conversations can be really casual. The interviewee may not even know you are working on a project or that you are "interviewing" them.
- Ask about lived experience, daily habits and frequent actions instead of abstract ideas and possible solutions.
- Ask about specific actions in the past, about the positive and negative experience of using similar products. If you consider your idea unique than refer to indirect competitors or the main issues a person witnesses.
- Ask your potential user to describe all the steps in detail of using a similar product. Listen and make notes carefully. Don’t miss the emotional questions (like "What did you feel...?").
- Try to ask for a commitment at the end of your conversation (it can be an intro to the colleagues or boss or a person who might be also interested in; pre-payment; one more meeting and etc.)

#### DON'Ts
- Don’t look for approval or support. Look for the truth. It’s pleasant to receive positive feedback and compliments, but they are dangerous. They might be misleading.
- Don’t try to convince your potential user that your idea is awesome. Listen to what people say and what kind of questions they ask.

### Crafting Questions

| Bad Question | Good Question |
| --- | --- |
| Do you think it’s a good idea? | Why do you bother? |
| Would you buy a product which did X? | What are the implications of that? Talk me through your workflow. |
| How much would you pay for X?	| What else have you tried? |
| What would your dream product do?	| How are you dealing with it now? |
| Would you pay X for a product that did Y?	| Who else should I talk to? |
| Do you think your husband would use this?	| Is there anything else I should have asked? |

#### Great Interview Questions

1. What is the hardest part about [doing this thing]?
2. When is the last time you encountered this problem?
3. Why was this hard?
4. What, if anything, have you done to solve this problem?
5. What don’t you love about the solution you already tried?

### Bad Data

Avoid:
- Compliments
- Fluff (generics, hypotheticals)
- Ideas

## Eat Your Own Dog Food

![](assets/man-eat-dog-food.jpeg)

Experience your product as your users do. If it’s good enough for you, it’s likely good enough for your users. This is called "dog fooding".

## Make It Easy For Users to Contact You

Maintain a direct connection to your users. Add a contact link on your website for user inquiries. 

### Contact Links

Add contact email and phone links to your site.

```html
<a href="mailto:ian@dpi.dev">Email Me</a>
```

You can even add a `body` and `subject` as query string params. This works for SMS too.

```html
<a href="sms:+15555555555">Text Me</a>
```

### Send user registration email follow up

Make sure you have a way to contact users. You can confirm email and/or phone number when users sign up. Send users a "welcome" email when they sign up.

```ruby
class User < ApplicationRecord
  after_create :send_welcome_email

  private

  def send_welcome_email
    UserMailer.welcome_email(self).deliver_now
  end
end
```

Here's a good example:

![](./assets/smart-bear-welcome.png)

![](./assets/smart-bear-question.png)

### Stay In Touch

Follow up with users after registration to build a rapport. You can even send it from your personal email to maintain a direct connection. Here's a good example:

![](./assets/rails-devs-update.png)

### TLDR;

Don’t ask anyone whether your app is a good idea!

## Quiz

- What is one major consequence of not gathering user feedback during product development?
- Increased development speed.
  - Not quite. (Copy this when selected)
- Increased likelihood of building a product nobody wants.
  - Correct! 
- Improved team morale.
  - Not quite. 
{: .choose_best #quiz_question_1 title="Importance of User Feedback" points="1" answer="2" }

- Which of the following is considered "bad data" during user feedback?
- Detailed user complaints.
  - Not quite.
- User compliments.
  - Correct! 
- Specific suggestions for improvements.
  - Not quite.
{: .choose_best #quiz_question_2 title="Identifying Bad Data" points="1" answer="2" }

- Which question is a good example of effective user interviewing?
- What would your dream product do?
  - Not quite. This is a "hypothetical" question.
- What are the implications of that? Talk me through your workflow.
  - Correct! 
- Would you buy a product that did X?
  - Not quite. This is a "hypothetical" question.
{: .choose_best #quiz_question_3 title="Crafting Effective Questions" points="1" answer="2" }

## Resources

- [Mom Test Summary](https://nucks.co/notes/the-mom-test-rob-fitzpatrick)
- [How To Talk To Users | Startup School](https://www.youtube.com/watch?v=z1iF1c8w5Lg)
- [Eric Migicovsky - How to Talk to Users](https://www.youtube.com/watch?v=MT4Ig2uqjTc)
- [How To Build Products Users Love](https://www.youtube.com/watch?v=12D8zEdOPYo)
- [Fast Path to a Great UX: Increased Exposure Hours](https://www.linkedin.com/pulse/fast-path-great-ux-increased-exposure-hours-jared-spool/)
