There are some queues we have access to that you didn't list in the doc (all the new-\* ones).

The new-\* are queues without GPU? 


I think, yes. I checked which hosts are inside new\* queues:

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.001.png)


and checked, for example the host group = ginossar\_host => it includes two hosts: cn242 and cn243:

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.002.png)

I run the command: ssh cn242 'nvidia-smi' => to see which type of GPU is there => the output was:

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.003.png)

or you can run:

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.004.png)

so, my conclusion => it is not GPU.

There are additional queue which includes GPU, like yan-gpu with even higher priority than waic\* queue:

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.005.png)

yam-gpu queue includes 2 hosts ibdgx011 and ibdgx012:

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.006.png)

and these hosts are GPUs =>

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.007.png)

However, we can not use this queue:

![A screenshot of a computer

Description automatically generated](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.008.png)

so, our GPUs are waic\* and gpu\*.

I forgot to mention in the Task 3 that waic-risk can be preempted by waic-short/long/medium

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.009.png)

But on the other side waic-risk has not limits 300/60, which we saw for other waic\*:

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.010.png)



Can you explain how the "Factor" works? 

According to IBM LSF manual:

<https://www.ibm.com/docs/en/spectrum-lsf/10.1.0?topic=reference-command>

<https://www.ibm.com/docs/en/spectrum-lsf/10.1.0?topic=reference-bqueues>

![](Aspose.Words.af45fbb7-2117-456d-a17c-2a99a7468b08.011.png)

The explanation is not clear for me. Don’t know. Lets leave this at his stage.



Does "RESRSV\_LIMIT:  [ngpus\_physical=0,8]" means we cant use less than 0 gpus or more than 8? 

I think yes, this is range for amount of GPU which can be used per job: from 0 till 8.


Can you explain how the "nfs4\_editfacl" command works? (the one from the jupyter tutorial in the hpcwiki)

I didn’t have a time yet to read HPC wiki. I will send the task related to Jupyter how I open and work with it => how I do it.

