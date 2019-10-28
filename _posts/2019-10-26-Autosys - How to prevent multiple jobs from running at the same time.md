---
title: "Autosys - How to prevent multiple jobs from running at the same time"
date: 2019-10-26 13:00:00 +0100
categories: [Scheduler, Autosys]
tags: [autosys, renewable resource]
---

Last week at work I was asigned a product backlog item which involved a bit of Autosys Development work in it. The requirement for Autosys work involved creation of 6 new jobs that would run the same MEDM Solution but with different Configurable Parameters. All these 6 jobs would be scheduled at the same time without any dependency between them. Which means these jobs could run at the same time and result in deadlock problems in the batch.

So to prevent this , the requirement was to ensure they don't run at the same time and to use `GLOBAL_VARIABLE` functionality. I have previously worked on IBM TWS Scheduler, So I was aware about scheduler functionality of 'Special Resource' which could be used to prevent jobs from triggering at the same time. Autosys does have this feature and to my surprise my project Autosys developers were never aware of this and they would use `GLOBAL VARIABLE` based dependencies which made the batch too complex.

A quick read through about Autosys Rebewable Resource from CA website was enough and I implemented this on my current task and also educated rest of the team members about the same.

Suppose that your batch has 6 jobs. And at any time, you want to ensure that the maximum number of jobs that can run at the same time is 1. This can be achieved using Autosys Renewable Resource.

**Define a renewable resource at the global level with an amount of 1, as follows:**
```
insert_resource: r1
  res_type: R
  amount: 1
```

**Define each job that requires this resource with the following conditions:**

  * The job requires one unit of the renewable resource before it can start.
  * The job frees the renewable resource whether it completes successfully or not.

The job is defined as follows:
```
insert_job: my_job_1
  command: sleep 500
  machine: hostname
  resources: (r1,quantity=1, FREE=A)
```

When a job is submitted, one unit of the resource is temporarily removed from the resource pool. Because there are only 1 unit, only 1 of these jobs can run on any machine. Other jobs that require this resurce cannot be submitted because no resources are available. When a job that is running completes, one unit of the resource is returned to the resource pool. Another job can be submitted because a unit is now available.

If you are here searching for a solution on how Autosys can prevent multiple jobs from running at the same time, Hope this post might have been of some help.

## See Also

* [Autosys - How to remove conditions]({{ site.baseurl }}/posts/Autosys-How-to-remove-conditions/)