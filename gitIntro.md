# Git INTRODUCTION

### what is Git?

<<<<<<< HEAD
=======
![git](https://miro.medium.com/max/910/1*Wjxx83j-qyiNvFBy1yOA1w.jpeg)
>>>>>>> 3f16bd60ea55eb4481d47e7aaa48accebb66d3d8


***Snapshots***

<<<<<<< HEAD
Git is a DVCS that stores data in a file system made up of snapshots. Each time you save a changed version of your project — called commit — Git creates a snapshot of the file and stores a reference to it. If the file has not changed, Git only stores a reference to the already-stored identical version of it.
=======
Git is a [DVCS](lawrenceabudubai.github.io/reading-notes/versionControlTypes) that stores data in a file system made up of snapshots. Each time you save a changed version of your project — called commit — Git creates a snapshot of the file and stores a reference to it. If the file has not changed, Git only stores a reference to the already-stored identical version of it.
>>>>>>> 3f16bd60ea55eb4481d47e7aaa48accebb66d3d8

***Local Operations***


Because the majority of necessary information may be obtained in local resources, Git primarily relies on local activities. Because a project's history is stored on the local disk, it eliminates the need to retrieve information from the server, allowing you to work on a project even while you're not connected to the internet or using a VPN.

***Tracking Changes***


Git keeps track of every modification made to any file or directory. Git will always detect file corruption or information loss in transit since it is the gatekeeper. 


***Loss of Data***

Git is designed to significantly reduce the risk of irreversible file damage, such as data loss due to human error. Git makes it incredibly impossible for a committed snapshot of your file to be lost.

***States***

Files in Git can reside in three main states: committed, modified and staged.



**Committed** : Data is securely stored in a local database

**Modified** : File has been changed but not committed to the database

**Staged** : Flagged a file’s changed version to be committed in the next snapshot

