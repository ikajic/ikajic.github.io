---
layout: post
title: "Computers, Brains and Creative Matters"
date: 2017-02-08
---

While working as a research fellow at the Plymouth University in
England I was part of <a href="http://cognovo.eu/">Cognovo</a>, an interdisciplinary group that 
investigates creativity.
The research I did in Plymouth and in the <a
href="http://compneuro.uwaterloo.ca/">Computational Neuroscience Research Group
(CNRG)</a> in Waterloo was recently published in Frontiers in Psychology.
The article is titled
<a href="http://journal.frontiersin.org/article/10.3389/fpsyg.2017.00099">A Spiking Neuron Model of Word Associations for the Remote Associates Test</a> and can be download for free.
If you are wondering what the title means, this post should shed some light on why me and my colleagues did what we did, how we did it and why it matters.

Traditionally, creativity has been studied within the discipline of psychology.
In some branches of psychology, researchers like to make tests to measure human cognitive skills and abilities (think of the IQ test and different personality tests). 
Similarly, there have been tests that aim to measure the ability of an individual to think creatively.
One of the commonly used tests is the Remote Associates Test (RAT). 
It was developed in early 60s under the assumption that creative individuals
are more likely to think of unstereotypical and remote word associations.
The instruction for a person performing the test is fairly simple: find a word that is associated with all three given
words in a meaningful way. For example, what is a single word that is associated with <i>night, wrist, stop</i>?
The solution is available at the bottom of this page.
More examples of the test are available <a href="https://www.remote-associates-test.com/"> here</a> (disclaimer: it is very easy to spend a lot of time on this website!).
Over the last decade, this test also gained popularity among cognitive neuroscientists, who study how neural activity changes when an individual is engaged in a task.
More specifically, in the context of the RAT, scientist are trying to understand what happens in the brain when people are thinking about different words when trying to solve a RAT problem.

My colleagues and I developed a computer simulation of an artificial brain network that
solves that task.
The simulated network contains thousands of artificial neurons that are mimicking how biological neurons behave.
We know that biological neurons communicate by emitting action potentials, electrical impulses transmitted over connections between neurons.
If an artificial neuron communicates in a similar way, we call it <i>a spiking neuron</i>.
Although the behavior of a single neuron can be interesting, the human brain
contains billions of neurons, so what matters more is the way neurons behave when they are connected together.
In this research, we used a <a href="http://compneuro.uwaterloo.ca/research/nef.html">particular theoretical framework</a> that describes how to connect neurons to do useful things.
In words of a computational modeller, a "useful thing" is a function.
That means, given some input, how can we connect neurons in a network so that they transform that input to produce an
output.
For example, in our model, there is a network of neurons that has been connected in such a way that it can generate associations for a given word. There is also a network that acts as a memory and remembers words that were generated previously, so it does not try to guess the same word as a solution again.
It is possible that networks performing such functions also exist in the human brain.

We showed that it is possible to create a neural network that not only solves the task,
but it does so in a way similar to humans.
That is, some RAT problems which are easy for humans are also easy for the
model, and problems which are hard for humans are also hard for the model.
In contrast to approaches in traditional artificial intelligence, where systems
often outperform humans on a particular task
(e.g., chess playing), we are making artificial intelligence that
is more human-like in terms of its behavior.
Using brain-like algorithms is a first step towards understanding what
mechanisms and representations of the environment are needed in neural networks to achieve
intelligent behavior.
Also, by connecting neurons and making them perform certain functions, we discovered
what kind of computations neurons have to support to do this task.


The solution: Watch.
