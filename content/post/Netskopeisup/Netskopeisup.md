---
title: "Netskope is up"
date: 2022-04-22T15:15:45-07:00
description: "Now that you have your Netskope Tenant, what do you do now?"
draft: falses
---



##  You have your Netskope cloud account, now what do you do with it? 



1. Create a basic real-time policy to “watch” traffic 
2. Steer client traffic to your Netskope tenant

## Testing tools. 



* The Netskope notskope site will verify that you are steering your traffic via the Netskope tenant. 

[https://www.notskope.com/](https://www.notskope.com/)



* Once you start blocking traffic a good way to test is with the Netskope Security Check.

[https://www.netskopesecuritycheck.com/](https://www.netskopesecuritycheck.com/)

## Real-time Protection Policy

>Policies > Real-time Protection > New Policy > Web Access



<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (/Netskopeisup/p1.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![1](/Netskopeisup/p1.png)


I go back and forth on if it is worth putting the system to just monitor. In this one, I list all web traffic and select all activities (browse, download, formpost, login attempt, and upload). I then watch for CCI rating. CCI is Netskope’s Cloud Confidence Index, basically their rating on how safe a cloudapp/website is. Setting the action to Alert will show you activity in the SkopeIT logs. I am always a little surprised about what I see. 

It might make more sense to create a policy to block malware but unless you hit some malware, Netskope wouldn’t generate any logs on it. 

Fields 

* Source: leave blank for all users

* Destination: Category (select all)

* Activities & Constraints: Activity = browse, download,formpost,login attempt,upload

* CCL = Excellent, High, Medium, Low, Poor, Unknown

* Profile & Action: Action:Alert

* Set Policy: &lt;name>

Save and Apply Changes



<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to /Netskopeisup/p2.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![2](/Netskopeisup/p2.jpg)


## Steer client traffic

Now you just need to get traffic to the tenant. Of course, you can send a GRE, IPsec, or SD-WAN tunnel to it but in this case, we will use the Netskope Client to steer traffic to it. 

At the bottom of the page select > Settings

>Security Cloud Platform > Traffic Steering > Steering Configuration

Go ahead and steer all users and all traffic.



<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to Netskopeisup/P3.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![3](/Netskopeisup/P3.jpg)


>Security Cloud Platform > Netskope Client > Users

Add the user's email address that you want. They will get an email to set up the client. 



<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to /Netskopeisup/P4.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![4](/Netskopeisup/P4.jpg)


## Once you have the client installed give the notskope site a try. 

[https://www.notskope.com/](https://www.notskope.com/)

It should show that your traffic is going through the NewEdge network. 



<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to /Netskopeisup/P5.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![5](/Netskopeisup/P5.jpg)


## What about the security check? 

https://www.netskopesecuritycheck.com/



<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to /Netskopeisup/P6.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![6](/Netskopeisup/P6.jpg)


Go back into the Netskope interface and look at Skope IT > Application Events. Click on the magnifying glass for detailed information. 





<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to /Netskopeisup/P7.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![7](/Netskopeisup/P7.jpg)

