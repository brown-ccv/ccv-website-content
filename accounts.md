---
title: Accounts

tagTitle: Accounts - Center for Computation and Visualization
tagDescription: Check account types for advanced research computing that require extra resources.

date: 2020-08-05T18:04:51.000+00:00
lead: We provide services with limited resources at no cost to all
  members affiliated with Brown. See below the account tiers and limits for FY24.
---

# High Performance Computing Cluster (Oscar)

> The number and size of jobs allowed on Oscar vary with both partition and type of user account. The following partitions are available to all Oscar users:

- Batch - General Purpose Computing
- GPU - GPU Nodes
- BigMem - Large Memory Nodes

<div>

  <table style=" font-size:0.9rem; margin-bottom:2rem;">
    <thead>
      <tr>
        <th>Account Type</th>
        <th>Partition</th>
        <th>CPU Cores</th>
        <th>Memory(GB)</th>
        <th>GPU</th>
        <th>Max Walltime* (Hours)</th>
        <th>GPU Type</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td width="25%"> Basic <br> <!-- Make it Single Line. -->
        <td> <br> batch <br> gpu <br> bigmem</td>
        <td> <br> 64 <br> 12 <br> 32 <br> </td>
        <td> <br> 492 <br> 192 <br> 752 </td>
        <td> <br> None <br> 2 Std. <br> None </td>
        <td> 48</td>
        <td> A2, Titan RTX, QuadroRTX, RTX3090,A5000, A5500 </td>
      </tr>
      <tr>
        <td>Priority CPU </td>
        <td>batch</td>
        <td>416</td>
        <td>3,000</td>
        <td>N/A</td>
        <td>96</td>
        <td>N/A</td>
      </tr>
      <tr>
        <td>Priority GPU </td>
        <td>batch</td>
        <td>24</td>
        <td>192</td>
        <td>4 Std.</td>
        <td>96</td>
        <td>A2, Titan RTX, QuadroRTX, RTX3090,A5000, A5500</td>
      </tr>
      <tr>
        <td>Priority High-End GPU</td>
        <td>gpu-he</td>
        <td>24</td>
        <td>256</td>
        <td>4 high-end</td>
        <td>96</td>
        <td>V100,A40,A6000</td>
      </tr>
      <tr>
        <td>Priority Bigmem </td>
        <td>bigmem</td>
        <td>32</td>
        <td>2TB</td>
        <td>-</td>
        <td>96</td>
        <td>N/A</td>
      </tr>
    </tbody>
  </table>

</div>

- All Priority accounts require PI approval

- If you need resoucrses beyond this, please send a project proposal (fillout this google form). Its subject to approval from RCAC

- Note, these values are subject to periodic review and changes
- Each account is assigned 100G Home, 512G Scratch (purged every 30 days).
- Basic accounts without a PI have no data directory provided.
- The various priority accounts have a higher Quality-of-Service (QOS); thus, priority accounts will faster job start times than basic accounts.
- The maximum number of cores and duration may change based on cluster utilization.
  - Priority CPU account has a Quality-of-Service (QOS) allowing up to 208 cores, 1TB memory, and a total per-job limit of 1,198,080 core-minutes. This allows a 208-core job to run for 96 hours, a 104-core job to run for 192 hours, or 208 1-core jobs to run for 96 hours.
  - Basic account has a Quality-of-Service (QOS) allowing up to 2 GPUs and a total of 5760 GPU-minutes. This allows a 2 GPU job to run for 48 hours or 1 GPU job to run for 96 hours.
- GPU Definitions:
  - Std: QuadroRTX or lower
  - High End: Tesla V100
- For more technical details, please see this [link.](https://docs.ccv.brown.edu/oscar/system-overview)

# Condo Purchase

> An investigator may choose to purchase a condo to support their high performance computing needs.

## Benefits of condo ownership

- **5 year lifecycle** - condo resources will be available for a duration of 5 years.
- **Access to more cpu cores than purchased** - condo will have access to 1.25 times the number of cpu cores purchased for the first 3 years of its lifecycle. For the remaining 2 years, condo will have access to the same number of cpu cores purchased.
- **Support** - CCV staff will install, upgrade and maintain condo hardware throughout its lifecycle.
- **High job priority** - Jobs submitted to a condo have the highest priority to schedule.

## How to get started

- Contact [support@ccv.brown.edu](mailto:support@ccv.brown.edu) to discuss your needs and review purchase options

# Staff Services

<div>
  <table style=" font-size:0.9rem; margin-bottom:2rem;">
    <thead>
      <tr>
        <th>Support Level</th>
        <th>Description</th>
        <th>Cost</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Advanced Support</td>
        <td>Limited code troubleshooting, training, office-hours. Limited to 1 week per year</td>
        <td>$0</td>
      </tr>
      <tr>
        <td>General Support</td>
        <td>Any staff services requiring more than 1 week's effort per year</td>
        <td>$85/hour</td>
      </tr>
      <tr>
        <td>Project Collaboration</td>
        <td>Percent time of a specific staff member charged directly to the grant</td>
        <td>%FTE</td>
      </tr>
    </tbody>
  </table>
</div>
    
# Research Data Storage Allocations

- 5 TB per Brown Faculty Member
- 10 TB per awarded Grant at the request of the Brown PI
  - An active grant account number will be required to provide this allocation and the data will be migrated to archive storage at the end of the grant.
- Additional Storage Allocation
  - If faculty require additional storage beyond the 5 TB per PI, and 10 TB per active grant, this request should be submitted to the Research Computing Adviosry Committee (RCAC) sub-committee for allocations and exceptions.

## Pooled Storage Allocations

The transition from an essentially free service for researchers to one that anticipates that some of Brown's storage costs will be absorbed by other sources will be challenging for some researchers. Some research groups have proposed a variation on the individual payment model in order to smooth out these challenges. In this group plan, all the researchers' individual and grant allocations are pooled under the umbrella of the group; then, the billing takes place at the group/center/department level. CCV will be happy to accommodate a group payment/billing plan.

In order to do this, interested departments/centers/institutes should generate a list of researchers associated with the group as well as all grants with end dates for any PIs in the group. CCV will then be able to generate a new group-level bill. In addition, please let us know who is handling the invoicing.
