---
layout: post
title: "AIternate endings: Lyrics completion using GPT-2"
date: 2019-03-31
---

GPT-2, a language model recently [published](https://d4mucfpksywv.cloudfront.net/better-language-models/language_models_are_unsupervised_multitask_learners.pdf){:target="_new"} by OpenAI researchers has attracted a lot of attention for
a number of reasons. The model has been trained on a giant, somewhat
curated and minimally processed text scraped off the Internet.
It is based on the [Transformer](https://papers.nips.cc/paper/7181-attention-is-all-you-need.pdf){:target="_new"} architecture that has been
highly successful on a variety of NLP tasks such as machine translation,
text comprehension, question answering and many more.

The model indeed demonstrates some impressive abilities, especially when 
considering that it has not been trained on any specific NLP task. Instead, it
only learned to predict the next word given a sequence of words,
a task known as *language modelling*. For example, the model will complete the
sentence "Thank you for the meal, it was absolutely" with the word "delicious".

Its ability to complete sentences, or invent paragraphs of text is particularly
interesting (or funny/creepy, depending on whom you ask).
For example, given the following text excerpt:
```
Context (human-written): In a shocking finding, scientist discovered a herd of unicorns living in a remote, previously unexplored valley, in the Andes Mountains. Even more surprising to the researchers was the fact that the unicorns spoke perfect English
```
The model continues:
```
The scientist named the population, after their distinctive horn, Ovid’s Unicorn. These four-horned, silver-white unicorns were previously unknown to science. Now, after almost two centuries, the mystery of what sparked this odd phenomenon is finally solved. Dr. Jorge Pérez, an evolutionary biologist from the University of La Paz, and several companions, were exploring the Andes Mountains when they found a small valley, with no other animals or humans. Pérez noticed that the valley had what appeared to be a natural fountain, surrounded by two peaks of rock and silver snow.
```

The fully completed text is available in the [manuscript](https://d4mucfpksywv.cloudfront.net/better-language-models/language_models_are_unsupervised_multitask_learners.pdf){:target="_new"} (more
nice examples are at pages 19 and 20).
The text is very convincing at the first reading, the model comes
up with reasonable names given the location in South America (Dr. Jorge Pérez,
University of La Paz), and it also gets some important details right
(evolutionary scientists, prepends the "Dr" title). It might take some time to
notice inconsistencies, such as a unicorn having four horns or two centuries
timeline. 

The authors imply that texts generated by the model are of such quality that
they can be perceived as written by a human, and thus misused, which is the reason
why they decided not to make the model available to the public 
([yet](https://github.com/openai/gpt-2/issues/16){:target="_new"}).
Instead, they released a smaller version of the model, which is not as
powerful, but still does a decent job on many language problems.

I was wondering how "good" would the small model be at coming up with alternate lyrics
for some famous songs. So I selected a few well-known songs, based on my
personal preferences, as well as the popularity (the number of YouTube views). In some cases, the model was able to complete
the original lyrics correctly, but I was more interested in less conventional options. There were many possible completions, and I selected ones which
I thought were particularly... refreshing :). Some of the results are quite
entertaining. The last verse is the produced by the model.

### Metallica - Nothing Else Matters
Revealing the dark side of AI...
```
So close, no matter how far
Couldn't be much more from the heart
Forever trust in who we are
And nothing else matters

Never opened myself this way
Life is ours, we live it our way
All these words, I don't just say
And nothing else matters

Trust I seek and I find in you
Every day for us something new
Open mind for a different view
And nothing else matters

Not long ago I've been telling you 
That if you don't believe in God's Will 
I will kill you, but if I tell you so much 
It will be true  
Do it as you've done, if you're a liar
```

### Police - Every Breath You Take
Appropriately creepy.

```
Every breath you take and every move you make
Every bond you break, every step you take, I'll be watching you
Every single day, every word you say
Every game you play, every night you stay, I'll be watching you

Oh can't you see, you belong to me
How my poor heart aches with every step you take

Every move you make and every vow you break
Every smile you fake, every claim you stake, I'll be watching you

Oh and the world moves with me every tiny moment I hear, you belong to me
How my heart aches with every bite you make, every kiss you make, I'll be watching you
No matter what you say - I'll be watching you
```

### Led Zeppelin - Stairway to Heaven
Deep.

```
There's a lady who's sure all that glitters is gold
And she's buying a stairway to heaven.
When she gets there she knows, if the stores are all closed
With a word she can get what she came for.
Ooh, ooh, and she's buying a stairway to heaven.

There's a sign on the wall but she wants to be sure
'Cause you know sometimes words have two meanings.
In a tree by the brook, there's a songbird who sings,
Sometimes all of our thoughts are misgiven.

But all of our thoughts are just misunderstood. 
So you don't know which words are true! 
So she thinks she's heard all the things her father taught her. 
And then she tries to tell her she could read those things for herself. 
```

### Rihanna - Umbrella
An unexpected, but consistent, plot twist.

```
You had my heart, and we'll never be worlds apart
Maybe in magazines, but you'll still be my star
Baby 'cause in the dark, you can't see shiny cars
And that's when you need me there
With you, I'll always share
Because when the sun shines, we'll shine together
Told you I'll be here forever

Said I'll always be your friend
Took an oath, I'ma stick it out to the end
Now that it's raining more than ever
Know that we'll still have each other
You can stand under my umbrella

And call me 'Lil Mama' 
'Cause Mama's right here
And I'm always here to help you break your fast, Because Mama's right there
And I'm always here to help you be safe 'Cause Mama's right there
'Cause there's my baby  And Mama's right there
And we'll be your friends
And we'll always be there.
```

### Ed Sheeran - Shape of You
This one has a rather unexpected ending... But it has good intentions.
```
The club isn't the best place to find a lover
So the bar is where I go
Me and my friends at the table doing shots
Drinking fast, and then we talk slow

And you come over and start up a conversation with just me
And trust me, I'll give it a chance now
Take my hand, stop
Put "Van the Man" on the jukebox
And then we start to dance
And now I'm singing like

You know what I mean
That's the way it is
So please, I know it's weird
But I know it's right
Because I just tell it
And I say "Hi, nice to meet you 
You better get dressed"
```

### Justin Bieber - Sorry
It flows nicely... until it doesn't.

```
You gotta go and get angry at all of my honesty
You know I try but I don't do too well with apologies
I hope I don't run out of time, could someone call a referee?
Cause I just need one more shot at forgiveness
I know you know that I made those mistakes maybe once or twice
By once or twice I mean maybe a couple a hundred times
So let me, oh let me redeem, oh redeem, oh myself tonight
Cause I just need one more shot at second chances

Yeah, is it too late now to say sorry?
Cause I'm missing more than just your body
Is it too late now to say sorry?
Yeah I know that I let you down
Is it too late to say I'm sorry now?

Can't you just say something, can you just say something ?
That's it
So let me, oh let me redeem, oh redeem
I know that I let you down
Is it too late now to say I'm sorry?
I think it hurts to think that you're just another one of those young boys who just tried to get a job like a lawyer and then couldn't
Is it too late now to say I'm sorry?
```
