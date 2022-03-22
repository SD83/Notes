1. Describe a situation in which you were able to use persuasion to successfully convince someone to see things your way.

S : This is a very recent scenario. As the architect in the payment domain I was included in a discussion where we were building our first online check out experience which will involve payment in the process. Earlier you would do everything else online but you will either had to call or come in person to the store to make the payment. This was teh first experience where we wanted to take payments online. Traditionally this kind of UI would be build by a experience team as a microsite but in case of payment I wanted to try micro front end pattern which makes it easier to expose reusable enterprise capability like payment. The product management team was apprehensive about the new approach and wanted to go a more traditional route.

T : My task was to persuade the product team by highlighting the benefits of the approach at the organization level while making sure we will not be putting the product roll out plan in jeopardy.

A : I partnered with our design team and created a small prototype with a very trimmed down capability. Then I set up meeting with the development team from the experience side to show my prototype and plan for integration. I also referenced similar experiences which already used micro front end. Once the technical feasibility was established I drew up a timeline and measurable matrices to track progress according to timeline.

R : With both the technical and delivery management team convinced I was able to pursuade the product owner to agree to be the first use case to use the micro front end.


2. Describe a time when you were faced with a stressful situation that demonstrated your
coping skills.

S : This was during the start of the pandemic. We have been working on a plan to introduce digital payments. Traditionally they were all physical checks. With the social distancing and store closure this moved quickly from a planning stage to we need it immediately. 

T : I was tasked with setting up a MVP solution for the digital payment. This was challenging and stressful because I was designing a solution in ASP .net core and Azure both of which I was not familiar with and we were working on a very tight deadline and failure to meet the timeline would directly impact the sales.

A : First thing I did was I marked a drop dead date by which I have to move the system to QA to give us enough time to test the process. I did a number of online trainings to gather as much knowledge as possible in .Net and Azure. I followed a extensive agile method in developing one piece of the solution at a time deploying multiple time in QA. This is a very stressful time and I was able to cope with it. 

R : I was able to finish the coding on time and the system went live during the may 2020. A number of initiative like curb side delivery was fueled by this. This was probably the highest moment in my career.

3. Give me a specific example of a time when you used good judgment and logic in solving
a problem.

S : This was during a sunday when I got paged by the support team that we are seeing a flood of errors in our payment platform. The errors were due to the reason that the web app in one region was not able connect to Azure keyvault.

T : My task was to figure out what was the issue and make the platform 100% operational again.

A : The first thing I did was to disable the faulty instance in traffic manager. Which stopped the bleeding. The next step was to identify the issue. Once I saw there have been no changes deployed for the application I concluded that logically this is something at the Azure side. When I investigated the web app history I saw the error started when Azure provisioned a new instance for the web app. This meant we have an issue with that Azure instance. I took a judgement call to scale up the web app instance because when we scale up Azure actually provisions a bigger instance and we would be able to get a fresh instance. I quickly got the required approvals from the management side and scaled up.

R : Immidiately after scaling up I saw that the connection to keyvault was restored and the platform came back to 100  operational.

4. Give me an example of a time when you set a goal and were able to meet or achieve it.

S : This scenario is during the end of 2019 and beginning of 2020. Our api management was done through Apigee Edge which is a SAAS solution. In Apigee Edge you need to write a proxy and then deploy it using the Apigee management API. To deploy you would have to provide a username and password with admin access. Traditionally the deployments were done by the admin team since the admin credential could not be shared.

T : I set a goal for myself to change this process to bring a more federated model where the teams should be able to own the complete deployment process as a CI-CD pipeline removing the admin team as the bottleneck.

A : I chalked out a plan to stand up a new Apigee proxy in front of the Apigee management API. I brought the plan up to my manager and our security and internal audit team to get their buy in by addressing all the security and guard rails around the process. Then I developed a custom maven plugin which would invoke the proxy end point rather than the actual endpoint and hosted that as apart of Azure devops pipeline.

R : Currently we have a fully self service process where each team can build and deploy their proxies using Azure dev ops pipeline.


• Tell me about a time when you had to use your presentation skills to influence someone's
opinion.
• Give me a specific example of a time when you had to conform to a policy with which you
did not agree.
• Please discuss an important written document you were required to complete.
• Tell me about a time when you had to go above and beyond the call of duty in order to
get a job done.
• Tell me about a time when you had too many things to do and you were required to
prioritize your tasks.
• Give me an example of a time when you had to make a split second decision.
• What is your typical way of dealing with conflict? Give me an example.
• Tell me about a time you were able to successfully deal with another person even when
that individual may not have personally liked you (or vice versa).
• Tell me about a difficult decision you've made in the last year.
• Give me an example of a time when something you tried to accomplish and failed.
8. Give me an example of when you showed initiative and took the lead.

S : This is a very recent scenario. As the architect in the payments domain I was included in a discussion on how we can enable digital payments for a particular business use case which is always have been handled traditionally with a paper check or draft. This business use case involved different technical systems and also other business unit like accounting and treasury. Although we had very capable individuals who were expert in there area we were not making much progress in the design.

T : I was able to quickly realize that before we dive deep into a single area or system we needed a common understanding of how the customer experience should look like.

A : I took the initiative to set up a workshop with representative from different teams and also with the business stake holders to create a customer journey map for the new process.

R : With a step by step visualization of the experience each team was able to identify what needs to be done in their area to drive the experience and we were able to make significant progress on the design. 

• Tell me about a recent situation in which you had to deal with a very upset customer or
co-worker.
• Give me an example of a time when you motivated others.
• Tell me about a time when you delegated a project effectively.
• Give me an example of a time when you used your fact-finding skills to solve a problem.
• Tell me about a time when you missed an obvious solution to a problem.
• Describe a time when you anticipated potential problems and developed preventive
measures.
• Tell me about a time when you were forced to make an unpopular decision.
• Please tell me about a time you had to fire a friend.
• Describe a time when you set your sights too high (or too low).