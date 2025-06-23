
life example you can't get a job without experience and experience can only come when you do some job so here we end up in a deadlock let's see a formal definition of deadlock so deadlock is a situation where a set of processes are blocked because each process is holding a resource and waiting for another resource acquired by some other process let us understand it with the help of an example so in this example process 1 is waiting for resource y but it is assigned to process 2 process 2 is not getting completed because it requires resource x which is assigned to process one ending up in a deadlock situation let's understand deadlock with one more real-life example of a wrongly managed school the school never performs good in board exams almost all the students get failed when the principle is asked why his straightforward answer is that teachers doesn't teach well when the teachers were asked about why the students were getting failed they said that they were not given their wages then again when the principal was asked why they are not giving the wages he replies that parents don't pay the fees and he does not have the funds to give the pay to the teachers the parents give the reason that school does not provide enough facilities but obviously principal cannot provide facilities unless the fees is paid which is depicted in this diagram and parents are not ready to pay the fees until facilities are enhanced in the school so here we end up in a deadlock situation and there's not much you can do for the school in the previous example we saw a deadlock between only two processes namely school and parents but a real operating system deadlock can be complex and it usually involves multiple processes and resources so now we are going to study four necessary conditions for a deadlock to happen so they are mutual exclusion hold and weight no preemption and circular wait let's see them all one by one so let's understand mutual exclusion if some resources are non-shareable which means that only a single process can use it for example here process one can use resource one and no other process can use resource one if this is not the case then process cannot be stopped from using a resource when they require it for example full screen processes in our computer cannot be used by two apps simultaneously so let's understand hold and wait now if a process holds some resource and waits for some other resource then the holding weight is occurred if this is not the case then the cycle of deadlock which we saw in the first diagram will not get completed and no deadlock will occur the above school example is a classic example of hold and weight as the school holds the facilities and parents hold the resources school needs the resources and parents need the facilities hence creating a hold and will situation now let's understand the third condition of no preemption a resource cannot be taken from a process unless the process releases the resource if preemption was allowed deadlock would never occur because then there would have been no process able to hold a resource for long amount of time for example if your speaker is running an audio and after some time you click on some another audio it starts playing it but in case if no preemption was allowed we would have to wait for the first audio to end it was on an infinite loop we will end up in a deadlock so let's understand the last condition circular weight a set of processes are waiting for each other in a circular form then circular weight happens for example if we extend the first example to multiple processes and resources waiting for each other's health resources in a circular fashion will end up in a circular weight condition so hope you understood the concept of deadlock and operating system please don't forget to subscribe to geeksforgeeks youtube channel and click on the bell icon you 




**Speech**
Hi everyone! Today, we will be talking about **deadlock** in operating systems and how we can handle them. 

> Imagine a city grid with four intersections. From all four directions long rows of cars trying to move forward.”

> “But each row enters the intersection and ends up blocking the next. No one can move forward, and no one can back up.”

> “Each lane is waiting for another to clear — but they’re all stuck. This is a perfect example of **deadlock**.”


**os example**

so in this example process 1 is waiting for resource y but it is assigned to process 2 process 2 is not getting completed because it requires resource x which is assigned to process one ending up in a deadlock situation
They're both stuck waiting for each other — and nothing moves forward.

**four conditions**
To understand how deadlock happens in an operating system, we need to look at four specific conditions. A deadlock can only occur when **all four** are true at the same time.

> “**First**, we have **Mutual Exclusion** — meaning only one process can use a resource at a time. If someone’s using it, others have to wait.”

> “**Second** is **Hold and Wait** — a process holds one resource while waiting to get another. It won’t let go until it has everything it needs.”

> “**Third**, we have **No Preemption** — the system won’t forcefully take a resource away from a process. It must release it voluntarily.”

> “And finally, **Circular Wait** — where a group of processes form a loop, each one waiting for the next.”
