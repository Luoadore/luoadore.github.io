---
title: Localization
date: 2020-11-14 12:48:00
tags: 5 Minutes with Cyrill
---

# Localization

So with localization we refer to estimating the position, and most of time the rotation of an object moving through our world. This can be robot navigating through the environment, a car driving around, a uav flying or in general sensor. And what we want to do is we take those sensor readings we want to estimate **where is the system** in a given coordinate frame. And often this coordinate is defined **based on a map** of the environment. So you can make an example from about yourself. You are in a new city and you take out a map of the city and you use your perceptions for example your eyes to read street signs and then estimate where you are. That's the form of localization. Or use a GPS receiver which gives you a coordinate which provides you then some information about where you are in the environment. And this localization task is highly relevant in robotics and in photogrammetry, in computer vision in autonomous car driving in using your smart phone you always use services which require post information about where you are in the world. So that's super relevant and a **building block** for most navigation systems or autonomous systems in general. 

We typically distinguish between **online and offline** approaches once you want to estimate where's the system right now and given the information that I have so far or in the offline the approaches where you have all the data at hand and want to reconstruct the full trajectory. We further more distinguish typically between **pose tracking**, which means we want to estimate where systems starting from a known location or having an initial estimate. Or **global localization** where we have no idea where we are and we want to globally estimate our position without any prior information. How do you solve the localization problem? Typically use probabilistic approacher and most of the online approaches rely on a recursive based filter which is technique for state estimation. There are different realizations of this space filter for example, a kalman filter, a particle filter, a histogram filter or even optimization based approaches are used. This has led to popular algorithms such as the EKF localization, Monte Carlo localization, Markov localization, or sliding window based least square approaches which are somewhat a hybird between an online and an offline approach. They all have different advantages and disadvantages such as being restricted to certain types of probability distributions such as gaussians or being computationally very efficient compared to computationally more demanding and which algorithm you choose basically depands on your application, on your constraints with respect to assumptions you can make about the world, with respect to your constraints on robustness, your precision, your computational resources that are available. So a lot of those factors need to be taken into account to evaluate which localization system is good for you. 

In general, the localization systems use **control** information, that means for example, steering information of the vehicle. In a car what's the angle of this your steering wheel how hard do you press the gas pedal would be control information. It's important to predict where the system will be at the next point in time. You can use or then use a second step sensor information (**observations**) such as camera or laser range filter in order to perceive the world and estimate where could you be what's an unlikely the position you might be in. Then you combine the prediction and this correction information in order to estimate where you are.

So in practice, localization plays an important role in the key building block of every autonomous system of every navigation system which is out there. And again they differ in with terms of robustness with terms of the assumptions of the underlying, the distributions about the motion models are either linear or non-linear, what are your runtime constraints you want to do global localizations. This always important things that impact the design decision of what localization system to choose.