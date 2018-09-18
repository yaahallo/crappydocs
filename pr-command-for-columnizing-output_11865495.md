1.  [Rubber Ducky](index.html)
2.  [Rubber Ducky](Rubber-Ducky_11863904.html)

<span id="title-text"> Rubber Ducky : pr command for columnizing output </span>
===============================================================================

Created by <span class="author"> Augy St. Clair</span> on Jun 14, 2017

<a href="https://files.slack.com/files-pri/T08UKLCCR-F5E12R66B/til__pr__command__which_is_damn_handy.txt" class="external-link">https://files.slack.com/files-pri/T08UKLCCR-F5E12R66B/til__pr__command__which_is_damn_handy.txt<br />
</a>

You give pr a set of files and a width. It'll give each file its own column and put them side-by-side.
------------------------------------------------------------------------------------------------------

 

Memory usage per node

    [root@scale-192-168-100-123 ~ 19:13:47 ]# type v
    v is a function
    v ()
    {
        sc vm show | egrep '\.'$1 | awk '{print $1 " " $2;}'
    }
    [root@scale-192-168-100-123 ~ 19:14:00 ]# pr -tm -w 200 <(v 221) <(v 222) <(v 223)
    56f3aeb9-3ee8-42c5-9cec-b0087d066eae 4.00GiB                       b257fe98-9fac-4bc8-af8c-41bc1c588ade 4.00GiB                       3d038ad7-3bae-4bb0-8c67-cdf2d722dcdf 16.00GiB
    52497b15-552d-48fa-a7a8-38b37341f1d7 4.00GiB                       822c73d4-4eee-4b04-b10a-24e1c8fb46c2 8.00GiB                       8ef99e1b-9834-46d4-9cc3-156c355ba0fa 16.00GiB
    34edba3a-4c02-491c-8127-0cf92ce56777 8.00GiB                       495ae476-fe35-47a0-b19d-105c40a661df 4.00GiB
    917c7541-ee11-40c2-b31b-07acce069e47 4.00GiB                       c8061427-671e-48e0-a46e-05aa57b6e6e2 4.00GiB
    34d9b5ee-96b1-49bc-a7b2-0c25566139e9 4.00GiB                       6509d2e0-c295-4f19-95aa-c0801a80e960 4.00GiB
    794fc837-202c-48de-8ab2-f8f72cd18af8 8.00GiB                       7481c1ab-bd26-464d-8292-06e8858c5048 8.00GiB

 

<a href="https://files.slack.com/files-pri/T08UKLCCR-F5E12R66B/til__pr__command__which_is_damn_handy.txt" class="external-link"><br />
</a>

Comparing tasks

    [root@scale-192-168-15-38 overrun 22:57:49 ]# pr -tm -w 250 <(grp cff45807-77278221) <(grp cff45807-77278222) <(grp cff45807-77278224) <(grp cff45807-77278227) <(grp cff45807-77278221) <(grp cff45807-77278228) <(grp cff45807-77278229) <(grp cff45807-77278230) <(grp cff45807-77278231)
    Step() extent V:2:0xfcc080 Step() extent V:2:0xfcc100 Step() extent V:2:0xfcc200 Step() extent V:2:0xfcc280 Step() extent V:2:0xfcc080 Step() extent V:2:0xfcc180 Step() extent V:2:0x191e00 Step() extent V:2:0xfcc380 Step() extent V:2:0xfcc300
    LockInterval() taskID 7727 LockInterval() taskID 7727 LockInterval() taskID 7727 LockInterval() taskID 7727 LockInterval() taskID 7727 LockInterval() taskID 7727 LockInterval() taskID 7727 LockInterval() taskID 7727 LockInterval() taskID 7727
    SetState() newState=1 (Int SetState() newState=1 (Int SetState() newState=1 (Int SetState() newState=1 (Int SetState() newState=1 (Int SetState() newState=1 (Int SetState() newState=1 (Int SetState() newState=1 (Int SetState() newState=1 (Int
    SetState() newState=2 (Dat SetState() newState=2 (Dat SetState() newState=2 (Dat SetState() newState=2 (Dat SetState() newState=2 (Dat SetState() newState=2 (Dat SetState() newState=2 (Dat SetState() newState=2 (Dat SetState() newState=2 (Dat
    SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne
    submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr SetEntryState() index=0 ne submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr
    TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas SetEntryState() index=0 ne TaskAdd() Checking for tas TaskAdd() Checking for tas
    submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr submitEntryAllocation() en submitEntryWrites() RSD Wr submitEntryWrites() RSD Wr
    TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas TaskAdd() Checking for tas submitEntryAllocation() en TaskAdd() Checking for tas TaskAdd() Checking for tas
    SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne submitEntryAllocation() en SetEntryState() index=0 ne SetEntryState() index=0 ne
    SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne SetEntryState() index=0 ne submitEntryAllocation() en SetEntryState() index=0 ne SetEntryState() index=0 ne
    UnlockIntervalForTask() ta UnlockIntervalForTask() ta UnlockIntervalForTask() ta UnlockIntervalForTask() ta UnlockIntervalForTask() ta UnlockIntervalForTask() ta inPlacePreplacedPick() rsd UnlockIntervalForTask() ta UnlockIntervalForTask() ta
    SetState() newState=4 (Ref SetState() newState=4 (Ref SetState() newState=4 (Ref SetState() newState=4 (Ref SetState() newState=4 (Ref SetState() newState=4 (Ref inPlacePreplacedPick() set SetState() newState=4 (Ref SetState() newState=4 (Ref
    SetState() newState=5 (Com SetState() newState=5 (Com SetState() newState=5 (Com SetState() newState=5 (Com SetState() newState=5 (Com SetState() newState=5 (Com inPlacePreplacedPick() set SetState() newState=5 (Com SetState() newState=5 (Com
                                                                                                                                                                      computeRSDPlacement() num=
                                                                                                                                                                      submitEntryAllocation() AL
                                                                                                                                                                      TaskAdd() Checking for tas
                                                                                                                                                                      submitEntryAllocation() AL
                                                                                                                                                                      TaskAdd() Checking for tas
                                                                                                                                                                      createZeroFillBuffer() cre
                                                                                                                                                                      SetEntryState() index=0 ne
                                                                                                                                                                      processEntry() entry 6430
                                                                                                                                                                      updateEntryL1FromAllocatio
                                                                                                                                                                      updateEntryL1FromAllocatio
                                                                                                                                                                      updateEntryL1FromAllocatio
                                                                                                                                                                      updateEntryL1FromAllocatio
                                                                                                                                                                      submitEntryWrites() RSD Re
                                                                                                                                                                      TaskAdd() Checking for tas
                                                                                                                                                                      submitEntryWrites() RSD Re
                                                                                                                                                                      TaskAdd() Checking for tas
                                                                                                                                                                      SetEntryState() index=0 ne
                                                                                                                                                                      SetEntryState() index=0 ne
                                                                                                                                                                      CommitL1() Commit on secto
                                                                                                                                                                      TaskAdd() Task bypasses an
                                                                                                                                                                      SetState() newState=3 (Met
                                                                                                                                                                      rsdRefcountBatchFinish() r
                                                                                                                                                                      UnlockIntervalForTask() ta
                                                                                                                                                                      SetState() newState=5 (Com
                                                                                                                                                                      depthFirstUpwardSearchToSt

   
-

Document generated by Confluence on Sep 18, 2018 18:02

[Atlassian](http://www.atlassian.com/)
