#Module: Salesforce Mobile Services Implementation Guidelines

Successful mobile solutions can mean many different things to different organizations. Some may require highly customized user interfaces for millions of users, whilst others are trying to break free of cumbersome desktop apps to enhance employee productivity and retention. How do you determine what is the right strategy for you? 

When determining the right strategy it is often helpful to define your implementation goals  two dimensions: app category, and app driver.


##Unit 1: App Cloud Mobile Service 
The App Cloud provides the following mobile services.

###Salesforce1
Salesforce1 is an enterprise-ready mobile app container users can install from public app stores. Salesforce1 provides instant access to much of the Salesforce products and capabilities such as Sales & Services. In addition, customizations can be make quickly using configuration tools. Developers can expose Visualforce and Lightning Component customizations, but Salesforce1 is not intended to provide a highly, pixel-perfect customized mobile app. Salesforce1 does not support offline capabilities and is generally intended for use by employees of a particular company, or a relatively small community of customers. 

###Mobile SDK
The Mobile SDK is an open source SDK which provides access to the App Cloud REST APIs for iOS, Android, and Windows Mobile developers. In addition to native access to APIs the Mobile SDK provides comprehensive support for enterprise requirements including authentication, pin code protection, data synchronization, encrypted data storage and offline support. The Mobile SDK does not provide any form of UI making it ideal for customers who require fully custom native mobile applications. 

###Heroku
Heroku provides the ideal cloud app platform for developers building highly scalable consumer facing applications. With full support for all of the leading programming languages and frameworks, developers can easily build hybrid,  web-based, mobile apps, or fully independent micro-services for partners and native mobile apps to consume. In addition, Heroku provides a suite of add-ons to connect consumer facing mobile apps to other Salesforce products such as Sales, Services, and Marketing to allow organizations to deliver a highly engaging app experience. 

##Unit 2: App Categories
Your mobile app category determines the primary audience or users of your app. 

####B2E
Business to Enterprise (B2E) apps provide services to their own employees. For mobile implementations, this may be the ability to transform a traditional desktop solution into an app accessible anywhere via a mobile device. Successful B2E mobile apps re-imaging the app experience in a mobile-first way, rather than simply recreating, or exposing an existing process, on a smaller interface. Examples for B2E mobile apps may be employee self-service, sales tracking, or expense reporting. User-base is typically a known number, and in the order of tens or hundreds for small businesses, to tens of thousands for larger enterprise. 

####B2B
Business to Business (B2B) apps provide the ability for one business to transact with another. For mobile implementations, this may be the ability for business partners to complete cross business processes such partner API integration,  fulfillment, or provide community and self-service capabilities. Many modern B2B scenarios also involve the white-labeling of services or apps to partners. White-labeling offers partners with a brand-able version of an app that the partner can customize certain aspects of the UI and offer to their employees. User-base can cover a broad range into the hundreds of thousands if the business is providing a mobile community for customers and partners. User-base scale is typically known and planned for as part of the mobile strategy.

####B2C
Business to Consumer (B2C) apps provide users an app downloadable from public app stores and marketplaces. The emphasis is on user experience with the goal to reach as many users as possible. B2C mobile apps must be build with a massively scalable backend that supports elastic growth. Successful B2C mobile apps also provide the ability to track customer usage and offer the ability to engage with users via marketing campaigns. 

B2C Applications can often be further divided in high volume and low volume categories. Whilst both apps focus on *public* customers signing up and downloading the app via public app stores, low volume apps typically do not expect massive scale should a service become incredibly popular. Such an example of a low volume app would include an airline or banking app - the user base is generally known and not expected to require elasticity in growth. A high volume app may be a shopping app, ride share, or similar.


 The following 6 drivers are the most common requirements Salesforce customers must evaluate. By examining these drivers, and how important they are to your business, you are more easily able to make the best technology decisions and set your mobile initiatives up for success.

##Unit 2: Mobile Drivers
Within an understanding of the available App Cloud Mobile Series, and identifying your app category, it is possible to map the key mobile drivers which influence technology choices and implementation patterns. The following 6 drivers are the most common requirements Salesforce customers must consider when building mobile apps.


###Branding
How much does the app require custom branding? This may include light customization of  logos, and colors, through to graphic-intense user experience and layouts

###Development Model
What is the organizations ability to create apps based on current skillsets? Can existing web developers be utilized, or do they need to outsource native development to specialized mobile app companies. Can   the organization leverage drag and drop tools to compose app? 

###Offline Support
How important is offline support, and data synchronization? This is a very common requirement for many customers and impacts the technology choices of the implementation strategy. 

###Number of Users
Understanding the expected number of users is important in leveraging the best license and platform primitives for optimal app experience and ease of development. 

###Amount of Data
Similar to number of users, having a solid vision of the amount of data expected to be generated by the mobile app will allow the definition of appropriate data storage strategies from the beginning, thereby reducing risk further down the implementation path. 

###Back-office Integration
The back-office refers to any system that business users can define and create processes, retrieve data at a business level, user identity and data representation used to provide processes to the mobile app.

###Internal Integration
Depending on your app category the definition of exact what internal integration is may change. For example, for B2B and B2E solutions, integration typically refers to connecting to traditional back-office apps including Oracle, SAP, etc. as well as custom apps developed in-house. For B2C solutions. The backend may refer to Salesforce as the customer service system of record.




##Unit 3 Best Practice Mobile Implementation Guideline Matrix

How do you choose the right mobile service based on mobile drivers? We can begin by looking at the relative capability fit of each App Cloud Mobile Service to the drivers identified above. 

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-f4h2{font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;text-align:center;vertical-align:top}
.tg .tg-g0ut{font-weight:bold;font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#cbcefb;text-align:center;vertical-align:top}
.tg .tg-xxrt{font-weight:bold;font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#ffcc67;text-align:center;vertical-align:top}
.tg .tg-xozw{font-weight:bold;background-color:#ffcc67;text-align:center;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-g0ut">UI<br>Branding</th>
    <th class="tg-g0ut">Development<br>Model</th>
    <th class="tg-g0ut">Offline &amp; Sync<br>Support</th>
    <th class="tg-g0ut">Number <br>of Users</th>
    <th class="tg-g0ut">Amount <br>of Data</th>
    <th class="tg-g0ut">Back-office<br>Integration</th>
    <th class="tg-g0ut">Internal<br>Integration</th>
  </tr>
  <tr>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Config</td>
    <td class="tg-xxrt">Critical</td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Enterprise</td>
    <td class="tg-xxrt">on-prem</td>
  </tr>
  <tr>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
  </tr>
  <tr>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Heroku</td>
  </tr>
  <tr>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Mobile SDK</td>
  </tr>
  <tr>
    <td class="tg-xozw">Hgh<br></td>
    <td class="tg-xozw">Code</td>
    <td class="tg-xozw">Not Critical</td>
    <td class="tg-xozw">High</td>
    <td class="tg-xozw">High</td>
    <td class="tg-xozw">Consumer</td>
    <td class="tg-xozw">Cloud</td>
  </tr>
</table>


We can then take this information to map a relative importance/service fit of 1-3, with 1 representing the least important, and 3 representing the most.

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-f4h2{font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;text-align:center;vertical-align:top}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-f2to{font-weight:bold;background-color:#646809;text-align:center;vertical-align:top}
.tg .tg-yw4l{vertical-align:top}
.tg .tg-g0ut{font-weight:bold;font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#cbcefb;text-align:center;vertical-align:top}
.tg .tg-xxrt{font-weight:bold;font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#ffcc67;text-align:center;vertical-align:top}
.tg .tg-xozw{font-weight:bold;background-color:#ffcc67;text-align:center;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-yw4l"></th>
    <th class="tg-g0ut">UI<br>Branding</th>
    <th class="tg-g0ut">Development<br>Model</th>
    <th class="tg-g0ut">Offline &amp; Sync<br>Support</th>
    <th class="tg-g0ut">Number <br>of Users</th>
    <th class="tg-g0ut">Amount <br>of Data</th>
    <th class="tg-g0ut">Back-office<br>Integration</th>
    <th class="tg-g0ut">Internal<br>Integration</th>
  </tr>
  <tr>
    <td class="tg-yw4l"></td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Config</td>
    <td class="tg-xxrt">Critical</td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Enterprise</td>
    <td class="tg-xxrt">on-prem</td>
  </tr>
  <tr>
    <td class="tg-f2to">B2E</td>
    <td class="tg-f4h2">1</td>
    <td class="tg-f4h2">3</td>
    <td class="tg-f4h2">3</td>
    <td class="tg-f4h2">1</td>
    <td class="tg-f4h2">1</td>
    <td class="tg-f4h2">3</td>
    <td class="tg-f4h2">3</td>
  </tr>
  <tr>
    <td class="tg-f2to">B2B</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">2</td>
  </tr>
  <tr>
    <td class="tg-f2to">B2C<br>(low)</td>
    <td class="tg-f4h2">3</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">1</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">2</td>
    <td class="tg-f4h2">1</td>
    <td class="tg-f4h2">1</td>
  </tr>
  <tr>
    <td class="tg-f2to">B2C <br>(high)</td>
    <td class="tg-baqh">3</td>
    <td class="tg-baqh">3</td>
    <td class="tg-baqh">1</td>
    <td class="tg-baqh">3</td>
    <td class="tg-baqh">3</td>
    <td class="tg-baqh">1</td>
    <td class="tg-baqh">1</td>
  </tr>
  <tr>
    <td class="tg-yw4l"></td>
    <td class="tg-xozw">Hgh<br></td>
    <td class="tg-xozw">Code</td>
    <td class="tg-xozw">Not Critical</td>
    <td class="tg-xozw">High</td>
    <td class="tg-xozw">High</td>
    <td class="tg-xozw">Consumer</td>
    <td class="tg-xozw">Cloud</td>
  </tr>
</table>


And finally, map the relative importance to available mobile services to provide a best practice implementation guideline for any mobile app. The guidelines shall be used in subsequent modules to provide deeper dive implementation instructions. 


<!-- 
Use this to generate the tables
-->

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-f4h2{font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;text-align:center;vertical-align:top}
.tg .tg-yzt1{background-color:#efefef;vertical-align:top}
.tg .tg-8bad{font-weight:bold;font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#999903;text-align:center;vertical-align:top}
.tg .tg-sqxi{font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#efefef;text-align:center;vertical-align:top}
.tg .tg-g0ut{font-weight:bold;font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#cbcefb;text-align:center;vertical-align:top}
.tg .tg-xxrt{font-weight:bold;font-size:medium;font-family:Arial, Helvetica, sans-serif !important;;background-color:#ffcc67;text-align:center;vertical-align:top}
.tg .tg-xozw{font-weight:bold;background-color:#ffcc67;text-align:center;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <th class="tg-sqxi"></th>
    <th class="tg-g0ut">UI<br>Branding</th>
    <th class="tg-g0ut">Development<br>Model</th>
    <th class="tg-g0ut">Offline &amp; Sync<br>Support</th>
    <th class="tg-g0ut">Number <br>of Users</th>
    <th class="tg-g0ut">Amount <br>of Data</th>
    <th class="tg-g0ut">Back-office<br>Integration</th>
    <th class="tg-g0ut">Internal<br>Integration</th>
  </tr>
  <tr>
    <td class="tg-sqxi"></td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Config</td>
    <td class="tg-xxrt">Critical</td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Low</td>
    <td class="tg-xxrt">Enterprise</td>
    <td class="tg-xxrt">on-prem</td>
  </tr>
  <tr>
    <td class="tg-8bad">B2E</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
  </tr>
  <tr>
    <td class="tg-8bad">B2B</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Salesforce1</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Heroku</td>
  </tr>
  <tr>
    <td class="tg-8bad">B2C (low)</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Mobile SDK</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
  </tr>
  <tr>
    <td class="tg-8bad">B2C (high)</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
    <td class="tg-f4h2">Heroku</td>
  </tr>
  <tr>
    <td class="tg-yzt1"></td>
    <td class="tg-xozw">Hgh<br></td>
    <td class="tg-xozw">Code</td>
    <td class="tg-xozw">Not Critical</td>
    <td class="tg-xozw">High</td>
    <td class="tg-xozw">High</td>
    <td class="tg-xozw">Consumer</td>
    <td class="tg-xozw">Cloud</td>
  </tr>
</table>





##Unit 4: Create Your Own Guideline Matrix
Using the following matrix, add a 1-3 indicating relative importance to your business for each app category and driver. 1 representing the least important, and 3 representing the most. 

tool based on my spreadsheet model.

##Summary
By identifying the relative importance of a mobile app driver to your particular app category, customers can easily pinpoint the App Cloud Mobile Services which suit their specific needs. Subsequent modules will provide detailed implementation plans based on this best practice implementation matrix.

Of course, many customers have different requirements and levels of importance to a particular driver. You can easily take this matrix and plot your own weightings and implementation plan. 


