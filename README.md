# UpVoteBaby-
Radiator Bot For Running a BOT that votes after SBD Transfers with URL's In the Memo


_________________________________________________________________________________________________________________________________________

Bot can now accept bids from one account and vote from another. This is handy if delegation is not available for your particular configuration (e.g. Golos). Note, if you can use delegation, you should because voting/commenting is done in the same transaction, which is less prone to complications.




There's now better support for urls in memos that end with things like #comments and/or /. Some people paste urls without looking for extras or they get urls from other platforms running Apache, which automatically adds trailing slashes

.

You can now configure BOT to accept both core (STEEM) and debt (SBD) currencies. They are not accepted 1:1. BOT checks the internal market to find the correct ratio to process bids.







The default is that Bot will only vote in 10 batches a day. Multiple users can bid in a voting batch. 
If only one person bids, they get the entire upvote. 
If two people bid an equal amount, they share the vote 50/50. 
The higher the bid, the higher percentage for the upcoming vote batch.

The bot operator can set any vote weight for the batch, which will affect the number of daily votes to bid on. Therefore, each day per batch has:

Votes	Percentage	       Timeframe	              Blocks
10	100 %	           every 2.4 hours	        2,880
20	50 %	           every 1.2 hours	        1,440
40	25 %	           every 36 minutes	        720
80	12.5 %	     every 18 minutes	        360
160	6.25 %	     every 9 minutes	        180
320	3.13 %	     every 270 seconds	        90



Example A

If you set the bot to vote at 100.00%, bids open every 2.4 hours. Alice and Bob both bid for in the same voting batch. If Alice bids 4 SBD and Bob bids 2 SBD, Alice will get a 66.66% upvote and Bob will get a 33.33% upvote.

Example B

If you set the bot to vote at 3.13%, bids open every 270 seconds. Alice and Bob both bid for in the same voting batch. If Alice bids 4 SBD and Bob bids 2 SBD, Alice will get a 2.09% upvote and Bob will get a 1.04% upvote.


Usage Rules:

If there are multiple bids with the same post, only one vote will be cast and the remaining bids will not be returned.
If the bot has already voted for a post, additional bids will not be returned.
The URL must be correctly expressed in the memo alone. Malformed memos will not be returned.
Install
To use this Radiator bot:
1) Install RVM(Ruby Version Manager)
2) Install Bundler with gem

I've tested it on various versions of ruby. The oldest one I got it to work was: ruby 2.0 



      #First, clone this git and install the dependencies:



$ git clone  

$ cd UpVoteBaby

$ bundle install




                             #Configure




       ##Edit the config.yml file.
       
:upvotebaby:

  :block_mode: irreversible
  
  :account_name: <voting account name here>
      
  :posting_wif: <posting wif here>
      
  :active_wif: <active wif here>
      
  :max_age: 7200
  
  :batch_vote_weight: 100.00 %
  
  :min_effective_weight: 0.25 %
  
  :reserve_vote_weight: 0.00 %
  
  :minimum_bid: 2.000 SBD
  
  :blacklist: mikethemug
  
  :no_bounce: bittrex poloniex openledger
  
  :no_comment: bittrex poloniex openledger
  
  :no_comment_fee: 0.00 %
  
  :auto_bounce_on_lockout: false
  
  
:chain_options:

  :chain: steem
  
  :url: https://steemd.steemit.com
  
  
      
     
     
     
Edit the support/confirm.md template, used to reply to the post when voting.

This ${content_type} has received a ${vote_weight_percent} % ${vote_type} from @${account_name} thanks to @${from}.
Run Mode
Then run it:

$ rake run
Bot will now do it's thing. 



If you face any problems while installing  ping me @upvote on DISCORD   



Thank you 

IF you want to Donate   send SBD or STEEM to @upvotebaby 
IF you want to Support only  Delegate STEEM POWER to @upvote baby 

If i am unavilable in Discord   you can also send SBD to upvote Baby and write your email in the memo   

if you want more explanations  my email is pranish.jee@outlook.com


THANK YOU

