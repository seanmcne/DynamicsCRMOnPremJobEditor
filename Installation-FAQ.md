How to install this utility: 
# Locate your CRM installation directory, this is usually "C:\Program Files\Microsoft Dynamics CRM"
# Place the .exe and config.exe file in the \Tools directory
# Run the exe from this directory to make sure it loads properly 

**NOTES:**
* The index management job should be run frequently and be run during off hours.  This job is responsible for creating new indexes after a solution import, entity creation, relationship creation/modification, etc.  If you schedule the gap too long, indexes may not be properly created after update rollups or solution imports which could cause some severe negative impacts. 
* CRM's re-indexing job, as of UR11, will also run a SHRINK on your database which can cause excessive file grows and poor performance, in addition any custom indexes are not automatically rebuilt by the system job.  If you wish to effectively 'disable' the re-index job, you must have another indexing job put in place that will re-index and defragment indexes.  This will then become your responsibility to monitor and maintain this job going forward.
