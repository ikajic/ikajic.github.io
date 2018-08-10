---
layout: post
title: "Colorado magic, part 1: Telluride neuromorphic workshop"
date: 2018-08-10
---
&nbsp;
<img src="/files/telluride.jpg" alt="home" width="100%">
<p align="right"><small> The town of Telluride observed from Ajax Peak © Ivana Kajić </small></p>
&nbsp;

This year I had the pleasure of participating at the [25th Telluride
Neuromorphic Cognition Engineering Workshop](https://sites.google.com/view/telluride2018/home){:target="_new"}. When I tell people this is how
I spent my summer, I can not help but notice looks prompting questions such as
"You did *what?*... and *where*?". This post will summarize what was happening
during the three weeks of the workshop that took place in July this year.
Scientists and researchers from all over the world, also known as *neuromorphs*, gathered once again to study the brain
using a variety of approaches, to build robots and work with unconventional hardware.
They predicted what people listened to from brain signals, tracked sattelites
and made AI systems that play foosball. And all of that was happening in the small town of Telluride.

Telluride is a mountainous town with a rich history, located at an
altitude of 2,670 m (8,750 feet) in the heart of Colorado, USA. 
As it happens to be the case with many such towns in that part of the world, its history is rooted in a heavy mining activity that started some time in 19th century.
Today, rather than miners, the mountains of Telluride attract a variety of
adventure seekers and nature lovers including skiers, hikers, runners, mountain bikers and climbers, to
name a few. Also, there are the neuromorphs.

Neuromorphs are the adventure seekers of a different kind. Rather than
looking for gold, or adrenaline, they look for answers to really hard
questions about how the brain works. It is a community of scientists from
different backgrounds that gathers annually in this tiny town not only to
look for answers and build robots, but also to
disseminate the knowledge and impart the enthusiasm to newer
generations of scientists.

This year, the workshop was held in the local elementary school, a beautiful
building with picturesque views of the surrounding mountains. I did not
anticipate that waking up in the morning and strolling to the school to attend
the morning sessions will be such a pleasant activity.
During first two weeks, the morning schedule was mostly filled with different 
talks and tutorials.
Presentations covered a variety of areas such as neuroscience,
robotics, machine learning and emerging technologies; introduced various hardware such as
different neuromorphic chips, event-based cameras and all kinds of robots;
software for simulation of neural networks, both for cognitive modelling and
machine learning. During the first week, we also formed groups
to work on projects with other participants.


One "house specialty" of the workshop is the focus on neuromorphic hardware,
low-energy hardware specifically designed to support efficient computations in neural networks.
As deep neural networks gain more importance in computer vision and other
domains, optimized hardware requiring less power than their conventional counterparts such as CPUs and GPUs is
becoming increasingly relevant.
At this workshop, participants had an opportunity to work with two such new chips:
Intel's [Loihi](https://newsroom.intel.com/editorials/intels-new-self-learning-chip-promises-accelerate-artificial-intelligence){:target="_new"}, and [Braindrop](https://web.stanford.edu/group/brainsinsilicon/index.html){:target="_new"}, a chip designed by researchers from the Stanford University.

The last week of the workshop was centered around the projects. I was part
of a group that explored algorithms and approaches for agents that are able to
learn and function in real-world environments. While humans can quite easily
adapt to small changes in the environment, noise and even smallest
perturbations in the input signals can be problematic for machines and AI
systems.
Within my team, we built a minimalistic system that is able to recognize a few different kinds of 
objects in real-time. The system contains an [AIY vision kit](https://aiyprojects.withgoogle.com/vision){:target="_new"} and an [AIY voice kit](https://aiyprojects.withgoogle.com/voice/){:target="_new"}.
The vision kit contains a small camera attached to a Raspberry Pi, which in
turn communicates with a [Movidius](https://en.wikipedia.org/wiki/Movidius){:target="_black"} chip. 
The chip is equipped with neural networks precompiled for a variety of tasks,
including feature extraction which we used to collect the data on different
objects.
Then, we used those features to train a neural network in Keras that we ported onto the Raspberry Pi.
The model was running in real time and it was able to
recognize novel, previously unseen examples of familiar kinds of objects.
A short video of this system in action is available
[here](https://www.youtube.com/watch?v=_0ujfvPsT4E){:target="_new"}.
Since I found myself opening and closing the cardboard case that
contained vision kit components more often than I expected, I decided to make my own case out of Legos
which turned out to be a more robust (and colorful) solution.

Although the workshop was quite intense and long, I enjoyed every single day.
There were plenty of opportunities for interactions with other participants,
organizers and invited speakers. 
I learned as much during the talks and
tutorials as I did during random chats and conversations we had over BBQs,
poker evenings and hikes. 
Aside from being great scientists and researchers, individuals I interacted with were also
great people with wonderful personalities. I consider myself
lucky to have had a chance to get inspired by their stories and experiences.

Such a [remote location](/files/bear2.jpg){:target="_new"}* and the small size of the
town facilitated a collegial, collaborative atmosphere as it was easy to do things
spontaneously (such as re-arranging the talks so people can watch World Cup
matches... to joys of some and sorrows of others!).
I particularly liked how the free time was incorporated into
the official schedule every evening -- there was ample time to enjoy outdoors,
rest and have dinner.
I have learned a lot while having a great time, and I would encourage anyone working in this domain to
apply for the workshop.

I will follow-up with another, separate post on what I did in Colorado after
the workshop. The post will be about the road trip I did with a good friend of
mine, and our adventures in the unspoiled, captivating wilderness of Colorado.

&nbsp;
&nbsp;

<small> \* The photo was taken by Aaron Voelker. </small>
