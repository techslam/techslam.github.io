---
title: "Autosys - How to remove conditions"
date: 2019-10-28 20:30:00 +0100
categories: [Scheduler, Autosys]
tags: [autosys, condition]
---

If you are like me starting up with Autosys development and encounter a requirement where you are asked to completely remove all the condition (start condition) from a job, And you are searching through CA documentation and various blogs for quick help, Sadly there isn't much out there.

Yes, it's little surprising that such a basic stuff isn't documented anywhere. Does this mean its very simple and easy that there isn't much to write or document about it. Probably that's the reason, because the solution is actually very simple, Atleast the solution that I finally used at my work.

Assume an example job, `dev_job_c` which is having below job condition :

`condition: s(dev_job_a) & s(dev_job_b)`

And now we just want this condition to be removed such that `dev_job_c` runs without waiting for the successful run of `dev_job_a` and `dev_job_b`.

This can be achieved using a simple `update_job` command as below :

`update_job: dev_job_c condition:`

Yes, we just have to leave blank after `condtion` and that is all required.

If you are reading through this post looking for 'how to remove autosys job condition', hope this might have helped you.

## See Also

* [Autosys - How to prevent multiple jobs from running at the same time]({{ site.baseurl }}/posts/Autosys-How-to-prevent-multiple-jobs-from-running-at-the-same-time/)