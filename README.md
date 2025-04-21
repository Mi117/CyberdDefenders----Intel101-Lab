# CyberdDefenders----Intel101-Lab
CyberDefenders —  Intel101 LAB Walkthrough


INTRO

Open Source Intelligence (OSINT) tools comprise a diverse collection of digital resources designed to gather, analyze, and correlate publicly available information from across the internet and other accessible sources. These specialized tools—ranging from advanced search engines and social media scrapers to domain analysis platforms and archived content repositories—enable investigators to transform scattered fragments of public data into coherent intelligence narratives. Their importance extends far beyond simple information gathering; OSINT tools have become fundamental components of modern security operations, allowing analysts to monitor digital footprints, identify potential threats, map adversary infrastructure, and detect data exposures before they can be exploited. In today's interconnected digital landscape, where information constantly flows through numerous channels, these tools provide security professionals with the capability to extract meaningful signals from the overwhelming noise of public data, ultimately helping organizations strengthen their security posture through enhanced situational awareness and proactive threat identification.

Link to the challenge: https://cyberdefenders.org/blueteam-ctf-challenges/intel101/

SCENARIO

This exercise focuses on Open-Source Intelligence (OSINT) as a method for mining and analysing publicly available data. It aims to enhance skills in producing valuable insights when investigating external threats in the role of a security blue team analyst. Through practical application, participants will learn to effectively gather and interpret information to improve overall security measures.

TOOLS USED

-	GOOGLE LENS
-	GOOGLE SEARCH
-	HOST.IO / WHOIS / VIEWDNS.INFO [https://host.io/][https://www.whoxy.com/][https://viewdns.info/]: protocols and platforms for checking domain names and IP addresses.
-	WAYBACK MACHINE [https://web.archive.org/]: a digital archive run by the Internet Archive that allows users to access past versions of websites.

WALKTRHOUGH

1)	Who is the Registrar for jameskainth.com?
   
By leveraging OSINT tools, such as HOST.IO or VIEWDNS.INFO, we can find to whom jameskainth.com is registered to, in this case NAMECHEAP, INC.

![Q1](https://github.com/user-attachments/assets/606f4785-5084-42bb-97ac-3e12bca8a47b)

2)	What is the Zoom meeting id of the British Prime Ministers Cabinet Meeting?

I have started by researching on the browser for the information, typing in key terms (such zoom/British Prime Minister/ID/ Cabinet Meeting) and found a vast list of articles and pages reporting the unfortunate accident.

![q2-1](https://github.com/user-attachments/assets/53bfc5f8-8f97-4175-aa1e-10c02430ecdf)

![q2-2](https://github.com/user-attachments/assets/fd63fb48-3c45-46b9-8171-3b93eba0d6dc)

4)	In 1998 specifically on February 12th, Champlain was planning on adding an exciting new building to its campus. Back then, it was called “The Information Commons”. Can you find a picture of what the inside would look like? Submit the SHA256 hash.
   
How to see a previous dated version of a webpage? Well, the answer is another powerful tool called “WayBackMachine”, a tool that allows researchers to retrieve historical web pages and archived content that is no longer available on live websites, and it does so by creating snapshots of the pages, freely viewable in the dedicated webpage portal.
In this specific case we have keyword that will help to identify what to search for:

-	**CHAMPLAIN** (sounds like a name)
-	**CAMPUS** (probably refers to a Uni or similar)
-	**THE INFORMATION COMMONS** (most likely to be a section on the website)
  
We conduct a quick search on the Internet, to find that the target is indeed a University campus of the **CHAMPLAIN University, in Vermont**.

![q3-1](https://github.com/user-attachments/assets/fe2ff3c5-d6d7-4b60-bf0d-055b20e84db3)

Now we head to our WayBackMachine and type in the home page of the University (www.champlain.edu) to find all the snapshot taken, 

![q3-2](https://github.com/user-attachments/assets/7ad0d448-a276-4263-aa18-ea79ade97879)

and we head to the one of interest: February 12th, 1998 and we see the “Information Common project” at the bottom of the webpage.

![q3-3](https://github.com/user-attachments/assets/1aecb548-0f4a-4eee-922e-241e72db3ba5)

By clicking on it we are prompted into the next webpage, and we can find the image of the interior of the campus; 

![q3-4](https://github.com/user-attachments/assets/23785073-35b9-40ac-af44-216e7dc5c529)

We then proceed to save the image on our machine and to extract the hash of the image via the following command on our Windows machine: Get-FileHash <file name>

![q3-5](https://github.com/user-attachments/assets/24677cfc-c232-4d37-806e-256ef06dd361)

Or using the following command on our Linux terminal: sha1sum <file name>

![q3-6](https://github.com/user-attachments/assets/c4a4b4f7-d454-497b-9b8c-07f23b803e10)

4)	In 2019 UVM’s Ichthyology Class Had to Name their fish for class. Can you find out what the last person on the public roster named their fish?
   
We leverage the browser search engine to find the relevant information by typing “uvms Ichthyology class” and we can find results directly leading back to Rubenstein Ecosystem Science Laboratory’s course page.

![q4-1](https://github.com/user-attachments/assets/f8ca0435-96ec-4314-a7fa-45e533f29945)

Next we target search within the Wayback Machine’s archive of the UVM School of Natural Resources (SENR) directory, and we see that revealed thousands of stored URLs.

![q4-2](https://github.com/user-attachments/assets/dd984e6f-52ab-45ab-947d-385a7f2c70e4)

![q4-3](https://github.com/user-attachments/assets/2c270cbf-15d5-48f4-9b46-982a09d23f14)

To refine the search we use the key terms **“fish name”** as requested in the question, to significantly narrow down the results. 

![q4-4](https://github.com/user-attachments/assets/5c08f60c-6eee-4dd3-85fd-bece39670f81)

Among the findings we see an archived spreadsheet, named “studentfishnames2018.xls”, which contained a list of students from the 2019 ichthyology class along with the names they assigned to their fish.
Upon downloading and examining the spreadsheet, we see that the last entry belonged to DYLAN D. WILKINS, who named the fish SACCOPHARYNGIFORMES.

![q4-5](https://github.com/user-attachments/assets/b2ec863b-3ab2-47d0-aab6-23cbdb86bba9)

6)	Can you identify the state from which this picture was taken? See the attached photo.
   
For this question we use the Google Lens tool to inspect the image:

![UNADJUSTEDNONRAW_thumb_4859](https://github.com/user-attachments/assets/85817c7f-746d-48c3-876b-e856f8e8f268)

![q5-1](https://github.com/user-attachments/assets/45dbdcd6-4e3a-4e35-b46f-1985b26806f4)

only to find a vast amount of information, which cannot really help us to identify the exact location of statue. We then start to analyze all the details such:
-	The statue is a representation of a pterodactyl.
-	Seems to be located in sort of set-up area (judging from the copies of the rock pillars behind it) which makes me thing it must be a theme-park based on dinosaurs.
-	I start by searching a full list of all the dinosaur-themed park in the world 
-	I then narrow down the research to the United States area (as in the previous questions we saw particular focus on the North America region)
-	I start by then typing all the States names and find out that the answer is **Virginia** *(Dinosaur Land)*.


CONCLUSIONS

OSINT tools are powerful instruments that can really enhance investigations and shed light on otherwise, previously unknown information, or simply they act as a ctalyst to connect all the dots during our investigations. 
They are essentially a MUST for every Cyber Defender! 
In modern threat intelligence operations security teams regularly use OSINT techniques to monitor for exposed credentials, identify potential phishing infrastructure, and track threat actor activities across the internet. The ability to correlate information from disparate sources often reveals patterns invisible when examining any single data point.
Most importantly, mastering these skills encourages the development of an investigative mindset—the ability to identify connections, recognize patterns, and pursue logical lines of inquiry that distinguish exceptional security professionals.

I want to thank the team of CyberDefenders.org and the challenge creators for a concise, yet insightful Lab as the practical application of concepts made this far more valuable than theoretical learning alone. I appreciate the time and effort put into creating such a valuable resource for the cybersecurity community. Thank you for contributing to my growth as a blue team analyst!
I hope you found this walkthrough insightful as well! If you found this content helpful, please consider giving it a clap! Your feedback is invaluable and motivates me to continue supporting your journey in the cybersecurity community. Remember, LET'S ALL BE MORE SECURE TOGETHER! For more insights and updates on cybersecurity analysis, follow me on Substack! [https://substack.com/@atlasprotect?r=1f5xo4&utm_campaign=profile&utm_medium=profile-page]

