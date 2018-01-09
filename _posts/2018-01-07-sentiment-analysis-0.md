---
layout: post
title: Sentiment Analysis
---

Some time ago, a flatmate of mine was telling Luiza and I about a talking therapy where the therapist offers no analysis. Loosely, the therapist is just listening actively, with the occasional prompt to continue - such as 'Please, go on' or 'How did that make you feel?'. Now, we know nothing about talking therapy, but we laughed at this and decided to make a bot to administer our caricature of that.

We started simply, with a robot that responded randomly with 'How queer', 'Tell me more' or 'Keep going'. This produced:

BOT: Please begin...

PATIENT: It all began in my childhood

BOT: How queer

PATIENT: Exactly! A homoerotic experience

BOT: How queer

PATIENT: Indeed, so we sat there eating grapes and looked at each other

BOT: Tell me more

PATIENT: And we saw love

BOT: Keep going

PATIENT: And we knew it was true

BOT: How queer

PATIENT: Do you think so?

BOT: How queer

Which was funny, but we wanted more appropriate responses. Luckily, we are working in Python, so of course there's a library to help us. In this case it was textblob and nltk. One of the tools they came with is 'sentiment analysis'. It looks at words in a sentence and assigns them values - called polarity - between -1 (sad/bad) and 1 (happy). For example 'fun' has a value of 0.3, and 'awful' has a value of '-1.0'. I suspect the values are actually probabilities of the sentence containing the word being negative/sad or positive/good, but I am really ignorant of the theory behind it.

Our next leap was a two-statement bot: if the patient said something negative it would respond with 'How terrible' and 'Great!' otherwise. This was ok, but we were quickly distracted by what was considered positive or negative as you can see:

BOT: Please begin...

PATIENT: The fourth stabbing happened at 2.30am on 1 January, when a 20-year-old man was attacked in Old Street, east London. A second man, aged in his 20s, was taken to hospital with critical stab injuries. Police have arrested a 19-year-old man on suspicion of murder following the stabbing.

BOT: How terrible.

PATIENT: Puppies and rainbows.

BOT: Great!

PATIENT: Blood and toil.

BOT: Great!

PATIENT: Candle wax in the ear

BOT: Great!

PATIENT: Killing for fun

BOT: Great!

PATIENT: Child slaughter and plunder of old women

BOT: Great!

PATIENT: Sad killing for fun

BOT: How terrible.

PATIENT: Sad puppies and rainbows

BOT: How terrible.

PATIENT: Sad Good

BOT: Great!

PATIENT: Terrible good

BOT: How terrible.

The tool does consider many words such as 'toil', 'kill', and 'slaughter' neutral (value 0.0), and there doesn't seem to be much consideration of interaction between words apart from grammar ('terribly good' is good).

But perhaps the flaws could be smoothed over with enough words, we thought. We wondered whether the sentiment measured by this 'polarity' during a story would make sense, so we decided to apply the analysis to entire books and see whether the sentiment correlated with the plot. First, we just plotted the sentiment throughout the story for 'A Study in Scarlet' by Arthur Conan Doyle (which we got via project Gutenberg).

![alt text](http://127.0.0.1:4000/public/d180106_scarlet_sentiment.jpg)

There are many (39%) sentences which have polarity 0, and without knowing the plot that well, it's difficult to see whether the polarity graph makes sense. The large dip near index 1500 is the start of part II chapter III 'John Ferrier talks with the prophet'. The beginning of the chapter speaks of torture and injustice as part of religious oppression, so that makes sense, but overall we haven't had any major insights yet.

Another approach we tried was to compare the distribution of positive and negative sentences in three books: 'The Brothers Karamazov' by Dostoyevsky, 'Pride and Prejudice' by Austen, and 'A Study in Scarlet'. This is a little more interesting, but not revolutionary. I've removed the sentences with 0 polarity to make the trends visible. The other books also have large proportions of polarity-neutral sentences (30% for Pride, 45% for Karamazov).

![alt text](http://127.0.0.1:4000/public/d180106_histogram.jpg)

Some points of note: Dostoyevsky has twice the number of the strongest negative words, Austen is biased towards slightly happy and Doyle is biased towards slightly negative.

At this point, we have data, but little insight. Next steps will either be focused on improving the analysis, or expanding the body of books considered to look for patterns across books.
