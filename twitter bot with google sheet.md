# Introduction: Creating a twitter bot using a Google sheet

## **What is a Twitter Bot:** 
A Twitter bot is a type of bot software that controls a Twitter account via the Twitter API. The bot software may autonomously perform actions such as tweeting, re-tweeting, liking, following, unfollowing, or direct messaging other accounts. Wikipedia Bots date back to the 1980s, when programmers using a service called Internet Relay Chat began making user profiles to serve narrowly-defined, pre-programmed functions. The human user could ask the bot for date and time, for example, and the bot could provide. Soon, they were serving essential internet functions, like providing backup to Wikipedia’s human editors (bots can flag possible copyright violations, or add links to stories) and trawling sites to for Google and its search engine.

As the bot’s domain has expanded, so have the tool for its creation. Many bots are still built with basic programming languages, like this DIY bot made with NodeJS that will respond to text messages. But the most sophisticated bots are actually artificial intelligence, cannibalizing existing information, running it through a neural network, and spitting out novel ideas or images based on what it’s learned. A recent example includes this bot that turns words into strange, grainy, and theoretically-related images.
## **Five things to know about twitter bots:** 
It’s no secret that there are bots on Twitter. But how do bot accounts – which automatically create tweets without direct human oversight – actually affect the mix of content on Twitter?

A new Pew Research Center study, conducted over a six-week period in the summer of 2017, examined 1.2 million tweets with URL links to determine what share of links were posted by bots on Twitter. The study identified bots using Botometer, which learns patterns from hand-classified account data produced by trained experts.

To count how many times human and bot accounts shared links to particular websites, we wrote a computer program to follow each shared link to its destination. Then we isolated the 2,315 most commonly shared sites with meaningful content and classified the kinds of content that appear on those sites.

Here is a link to five key takeaways from [Pew Research](https://www.pewresearch.org/fact-tank/2018/04/09/5-things-to-know-about-bots-on-twitter/).
## References
[Zach Whalen spreedsheet](http://www.zachwhalen.net/posts/how-to-make-a-twitter-bot-with-google-spreadsheets-version-04/)

[How to Write your own Twitter Bots without Code - Digital Inspiration](https://www.labnol.org/internet/write-twitter-bot/27902/)

[Pew Research](https://www.pewresearch.org/fact-tank/2018/04/09/5-things-to-know-about-bots-on-twitter/).

##**General Setup Instructions**
The following steps are general for any type of bot you want to create. To get started, make a copy of this [Zach's spreadsheet](https://docs.google.com/spreadsheets/d/1Cbg_6pYN04XtDHpDLtxAP3ExQEBL8PYBXBQ1E5_Sq30/copy), then proceed through the steps below.
## Tutorial
 >**I recommend that you create a separate [Gmail](Gmail.com) account for your bot so you can have everything apart from your personal account.**

**1. Create a Twitter account for your Bot**

Go to [Twitter](https://twitter.com/) and sign up for a new account. You can always change the name later, but to make the next steps go smoother, go ahead and confirm the account with an email address and do some of the basic profile setup.

You’ll need to verify your email address and a mobile phone number. This is a pain, but it’s what Twitter requires now. If you already have a mobile number associated with a different Twitter account, you’ll have to disconnect that one first. You can always re-arrange those associations later, but the bot account does need to have a mobile number while you’re setting it up. Enter your account name in your Spreadsheet under Step 1.

***insert Join twitter PIC***

**2. Create a Twitter App for your Bot**

This application (“app”) is the method that your spreadsheet will use to talk to Twitter. It’s possible to use Apps for multiple bots or accounts — in fact, this is how they’re designed — but I like to make one for each bot account so that if one gets suspended the others aren’t necessarily in jeopardy at the same time.

Go to [Twitter Apps](apps.twitter.com) and hit the “Create New App” button there. Fill out the form to give your app a name, description, and website. These can be quite simple and can always be changed later. The app’s name needs to be unique, so you can name it the same it based on your bot. Leave the “Callback” field blank for now. If you get an Error message saying that you must first add a mobile phone number to your profile, then you should do that now.

***insert create application pic*** 

**3. Complete App Setup and Enter Keys into the Spreadsheet**

You App has four tabs: Details, Settings, Keys and Access Tokens, and Permissions. Under Details, make sure that the app’s access level is set to “Read and Write”, and if not, change that under the Permissions tab.

Under the Keys and Access Tokens tab, use the button to “Create my access token.” This will authorize your app to interface with your account. (I know, it seems redundant.)

Then, copy and paste the Consumer Key (API Key) and Consumer Secret (API Secret) from that tab into the green cells under Step 3 in your spreadsheet. (Note: The Consumer Key and Secret are not the same thing as the Access Token and Access Secret.)

***insert another bot and customer key pic***

**4. Locate your Google Spreadsheet’s “Project Key”**

This is your spreadsheet’s unique ID within Google. To find yours, first open “Tools -> Script Editor…” to bring up the Script Editor. In the Script Editor, open “File -> Project Properties”, and locate your “Project key” in the table that you’ll see there. Copy and paste that Project key into the green cell under Step 4.

***insert callback url pic***

**5. Add “Callback” Value to Twitter App**

After completing Step 4, the red cell under Step 5 should automatically change to include your Project key as part of a URL. If not, or if you accidentally delete it, the URL follows a simple formula:

	https://script.google.com/macros/d/<YOUR PROJECT KEY>/usercallback

Go back to your Twitter app’s Settings tab and paste that URL into “Callback URL” field.

**6. Select a Data Sheet and Generate a Preview of its Output**

Select a data sheet from the drop down under Step 6, and from the “Bot” menu in your Spreadsheet, select “Generate Preview”. (Each of the four options has specific setup instructions below, but they’re all pre-populated with sample content for this setup step.)

Switch to the “Preview Output” sheet to see 15 sample tweets generated from the selected data sheet. You can edit these data sheets to your own content now, or you can wait until the rest of the setup is complete.Generating this preview will require you to authorize the scripts in this spreadsheet, so you should agree to grant it permission if prompted.

***insert preview output***

**7. Test Twitter Authorization**

You’re almost done! From the “Bot” menu above, select “Send a Test Tweet”. If everything has been set up correctly, you should see a pop up inviting you to authenticate your app with your Twitter account. It’s pretty easy. Follow the link, click authorize, then close the new tab when it says. “Success!”

Re-run Send a Test Tweet, and check your time line. Hopefully it worked!

Step 8: Set Post Timing

Decide how often you want your bot posting, and select an option from the drop down under Step 8. Unfortunately, these are the only options, and the actually timing is to some extent subject to Google’s whims. You won’t, for example, be able to specify your bot to post at exactly 10:34 every day.
8
Step 9: Start it up!

If everything has gone well so far and your data sheet is populated with your content, then you’re ready to start sending out tweets. Select “Start Posting Tweets” from the Bot menu in your spreadsheet. If ever you decide to stop your bot, then use the “Stop Posting Tweets” option under the Bot menu.

You can change the data sheet selection and edit the data sheet contents without stopping the tweeting. It will simply use the updated setting whenever it next attempts to send a tweet. You will, however, have to stop and restart the posting if you want to change the timing.
