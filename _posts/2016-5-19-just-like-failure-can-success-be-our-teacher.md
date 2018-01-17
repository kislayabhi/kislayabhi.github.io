---
layout: post
title: Just like failure, can success be our teacher?  
published: true
comments: true
categories: 
- Life philosophy
---

It had been a long time since I came here. Our Summer vacations have started and I am trying to kick start my todo list for summers (which is another post just so that I can remind it to myself). I got a roadbike and am lately enjoying the biking experience along the beautiful trails present in Minneapolis.

Recently, I got a good chunk of research done where I wanted to parallelize some sequential Image Processing code by writing it in CUDA. It was something I really wanted to do and now it looks very much complete. I was rejoiced seeing the awesome results. I stopped working after getting the results and have till now spent more that 20 hours doing absolutely nothing… but why? because I am happy and I don’t want to work now. I felt a sense of accomplishment which restricts me working more.

These things suggest that I stumbled onto **success!** And not working and taking a rest was my way of celebrating this.

**But!** Can I re-evaluate myself at the current moment and see what are the things that contributed to this success?
Let’s try.

First of all, It is not **I** succeeded or **My** idea worked. I realize now that I am not the only one who is to be attributed for the result. It is the sum total of efforts of people whose open-source libraries I use everyday, my advisor, my friends who helped me with their valuable suggestions and discussions. It is the result of the professor who taught MOOC’s. Moreover, it is the result of my Dad and Mom and brother for giving me solace in the times of trouble. Well Mom and Dad are the ones who paid for me and helped me learn the basics anyways. The list goes on and on …

From this you can see that **Nothing is mine!** **It is a sum total of the contributions of thousands of people either directly or indirectly. I happened to be the one who built upon their ideas and got things working.**
Quoting Bhagvad Geeta:

![Image 1](/images/geeta1.png)

>That person attains peace who giving up all material desires for sense gratification lives free from attachment, free from false ego and sense of proprietorship.

Secondly, I think analyzing what worked for me this time can help me get a pattern on which I can rely on in future. It does not mean that it will work everytime but still it would be a good back up plan to rely on when every other thing falls apart.
Let’s bullet the things.

1. I got to know about superpixels. I spent time reading it’s actual implementation in the literature. I ran the OpenCV demo.

2. Then came the time when I was asked to parallelize it using CUDA. I had no idea what CUDA is. I tried to follow a cuda book in haste. I got a open-source library that finds that superpixels on GPU. I am reigning high on confidence now since things are running now.

3. Then I tried implementing some minor improvements which my advisor suggested. This was the time where I tried reading a CUDA library without knowing much about it. I did read the code many times but my understanding was at most superficial.

4. I perfected the code in Matlab without caring about GPU or OpenCV.

5. Then I perfected the code in OpenCV without caring about GPU.

6. Then at last I had no choice but to enroll in the parallel programming class of Udacity. I completed its 2 chapter’s lectures. Now I knew a lot more about parallel programming and reading the library once more made me understand everything that was needed as for now. I got some ideas on how to hack that library and get things working.

7. Now I again went to step 3 (but after coming to step 7, I now know what is happening around). Then only I was able to implement the code as it was required on GPU.

One takeaway is that: **Untill you have the actual understanding of what is happening around, you won’t go much far. + for proof of concept, make sure everything works in Maltab. Then jump step by step.**

So these are the two simple takeaways.
