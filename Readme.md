Engineering Design Center HRDC  
![download](https://user-images.githubusercontent.com/64484410/80700386-44910300-8afb-11ea-814f-7086cd3d3822.png)
 # **Platforms-How-To-GIT**
# **Carrier-Platforms**
## SRS Metadata
## This document extracted from database on: < date>
   
 **Note:**  _Printed or stored (independent file) versions of this document may not be current. See electronic document in Integrity database tool for current controlled version._
# **About this document**
Document revision --  
Document date --  
Document status --Open  
Integrity document title --  
Integrity document ID --  
Integrity Project Name --  
Document Authors – Annapurna Bommakanti, Prakash Nitsure, Mahesh Gaikwad, Siva Nallamalli  
Document change history:  
![Untitled picture](https://user-images.githubusercontent.com/64484410/80701585-3e038b00-8afd-11ea-93f7-6a0ef97a63b0.png)  
              **Document Approvals**      
Passport Review Board approved: <Yes, No> (manual entry (default No) or based upon object state)  
Project team approval:  
<Last, F.>, <date>  
<Last, F.>, <date>  
 [**Table of Contents**]()  
   [1	Checking for GIT]()  
    [1.1	Check your connection to Azure-DevOps]()   
 • Azure-DevOps: [www.utcbis.visualstudio.com](www.utcbis.visualstudio.com)        
 • Login with your carrier email id and windows login password (SAML credentials)    
![Annotation 2020-04-30 161720](https://user-images.githubusercontent.com/64484410/80702141-37c1de80-8afe-11ea-9f9a-e96d97b0090d.png)  
![Aotation 2020-04-30 163154](https://user-images.githubusercontent.com/64484410/80703397-545f1600-8b00-11ea-8fbd-558d2946be86.png)  
	     [1.2	Checking Repos]()  
 [2	Setting up your development machine]()  
    [2.1	SSH Key generation for GIT access]()      
    [2.2	Steps to generate ssh key]()  
    [2.3	Integrating generated key to GIT	]()    
 [3	Working with GIT	]()  
 [4	Adding passphrase	]()    
 [5	List of repositories	]()    
 [6	What Next]()  
 [7	Useful references]()  	
  # 1	Checking for GIT
  ## 1.1	Check your connection to Azure-DevOps  
   *Azure-DevOps: [www.utcbis.visualstudio.com](www.utcbis.visualstudio.com)  
   *Login with your carrier email id and windows login password (SAML credentials)  
   **1.2	Checking Repos**  
   You should be able to see following ribbon on left side of your screen  
   Below is something similar you might be able to see    
   # 2	Setting up your development machine
   **2.1	SSH Key generation for GIT access**  
Enrolling the SSH key on development (user Dev machine where he shall start his development work) machine shall enable ease of accessing   GIT without a need to every time enter user credentials and password. This especially useful when we developer is working with   creating YOCTO image and some of his scripts needs to have an inherent ability to pull the repositories from GITHUB.  
   **2.2	Steps to generate ssh key**  
    •	Open a terminal in Linux PC.  
    •	Navigate to home folder or any folder.  
    •	Enter the command “ssh-keygen” in the bash  
    •	It would prompt to enter the location to save the key file. By default it is ~/.ssh. It’s optional to change this path.  
    •	Once done, a passphrase is prompted for. Enter it as “platform”, as this has to be remembered while accessing git.  
    •	With the entered passphrase, a key is generated. The output is as in the screenshot.  
    •	In the ~/.ssh folder the id-rsa.pub file is generated. Copy the contents of this file.  
   **2.3	Integrating generated key to GIT**  
    •	Open the [https://utcbis.visualstudio.com/](https://utcbis.visualstudio.com/).   
    •	Go to one of the Repos in DEV branch/ branch to be cloned.  
    •	After you click on “clone” you should see something like below  
    •	Click on adding New Key  
    •	Click on adding New Key, name it with your name and the copy the content of id-rsa.pub here (refer section 2.2 line item g)  
    •	You are now ready to clone any repo from GIT onto this machine without passing user name and password   
      every time, be sure to use SSH links for cloning or any activity you wish to do.   
# 3	Working with GIT
# 4	Adding passphrase
Before using Git add your key to ssh-agent, this shall enable seamless cloning and other activities with GIT   
Start ssh-agent if not started:   
$ eval `ssh-agent -s`  
$ ssh-add ~/.ssh/id_rsa   
//Enter passphrase for /home/user/.ssh/id_rsa:  
Check if the key is added (parameter is a lowercase L): Below is an example output one could expect  
$ ssh-add –l   
2048 55:96:1a:b1:31:f6:f0:6f:d8:a7:49:1a:e5:4c:94:6f  
/home/user/.ssh/id_rsa_key (RSA)   
 # 5	List of repositories
**In case one needs to access individual repos before the do YOCTO, here is the available list of repos**  
1.	pic6-linux-kernel  
2.	platform-ko-modules  
3.	platform-meta-modules  
4.	platform-meta-pic6  
5.	platform-meta-sdk  
6.	platform-meta-ti  
7.	platform-poky  
8.	platform-sdk  
9.	project-cor9c  
10.     project-utilities  

# Command to clone repo is 
$CloneLocation> git clone --branch *dev [utcbis@vs-ssh.visualstudio.com:v3/utcbis/Embedded-OS-Platform/REPO-Name]()  
										*-indicate branch one would like to clone  

# 6	What Next
To build a YOCTO image, please refer document “How-To-Yocto.pdf” shared by platform team.  
# 7	Useful references
[https://rogerdudler.github.io/git-guide/](https://rogerdudler.github.io/git-guide/)    
[https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)  
[https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)  [https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/)  
[https://superuser.com/questions/988185/how-to-avoid-being-asked-enter-passphrase-for-key-when-im-doing-ssh-operatio](https://superuser.com/questions/988185/how-to-avoid-being-asked-enter-passphrase-for-key-when-im-doing-ssh-operatio)  



        

   


