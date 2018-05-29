To install this utility refer to the [Installation FAQ](Installation-FAQ.md)

Some basic information on how this utility works: 


This utility will give you full control of rescheduling all your system jobs for each and every org and every job within each org. The only way to change multiple job times automatically, without changing each individual value by hand, is by setting the checkbox to apply to all jobs in a given org. The goal of this utility is to give CRM partners, ISV’s, and customers the capability of rescheduling the system jobs to optimize performance or to run during specific maintnance windows.  

For background here is the way CRM system jobs work: 
* A recurrence schedule is set and maintained (Future Scheduled Jobs) 
	* This is simply a pattern to use when scheduling future jobs – not the current/next runtime job 
* There is a current / next runtime job instance that is pre-scheduled. 
	* When this job runs a future occurrence is then scheduled. 

Take for example: an org’s reindex all: recurrence schedule / future job schedule is set to: every 1440 minutes @ 1am and my next run date/time is 6/22 @ 11am.  
* 6/22 @ 11 my job will run as that’s when it’s scheduled to run
* When the job has completed CRM updates the future runtime using the base recurrence pattern and time 
* CRM will then use the time set for the future occurrence leaving in the recurrence schedule of every 1440 minutes @ 1am (that won’t change).  The next runtime job will now be 6/23 @ 1am which is now based on the recurrence schedule set above. 
