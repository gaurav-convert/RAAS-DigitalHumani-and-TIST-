# RAAS-DigitalHumani-and-TIST-
RaaS is an Application Programming Interface that integrates with websites and applications.
GitHub documentation for RaaS(Reforestation as a Service)


**About**

Reforestation as a Service(RaaS) is an Application Programming Interface(API) that integrates with websites and applications. It facilitates the interaction between enterprises and reforestation organizations.
By automating the donation process with trusted reforestation partners, it enables enterprises to plant trees and track their reforestation efforts.

**How it works**

1- Choose a reforestation project: You can choose a project from worldwide reforestation organizations list to plant trees (We have chosen “TIST”).

You can find the list of reforestation organizations from all over the world in this document  Here.

2- Add Integration or Code to your project: Use integration or add a few lines of code in your website or mobile app to call the API requesting the planting of trees.You can add this on the actions of user  in your website or app of your choice(Subscribe to online billing, buying an specific products/services, purchasing from app, etc.)

3- User makes an Action: When a user makes an action on your website or apps(buying, purchasing,subscribing, etc.) a request to plant trees will be made to a trusted organization.

4- Trees are planted: That’s it! You will be billed by the trusted reforestation organization of your choice at a cost of ($1 USD per tree). You will receive an invoice monthly and a report( That specifies how many trees are planted on your behalf).

You can get all the above information in here: https://www.digitalhumani.com/

Detailed guide on How to integrate Tree Planting API with Zapier and generates certificate for user 

You can get started using the API by registering on the DigitalHumani dashboard at Dashboard. Once signed up, navigate to the “Developer” page to find your API key. You’ll need that key to authenticate with the API. 
There is an API that can help to plant single/multiple trees accordingly.

API - https://api.digitalhumani.com/tree [To plant trees]
Request Method - POST
Request Body- (sends data in json format)
{
  "treeCount": “Number of trees a user requested to plant”,[Dynamic Value]
  "enterpriseId": “ID we will get when you Sign Up in digitalhumani.com”,[Static value]
  "projectId": “Will get this ID when you choose a reforestation project”,[Static value]
  "user": “End user’s Email  by whom the trees were planted”[Dynamic Value]
}

  You can get all the API related detailed information on this Page.

You can create a Google Form which will be used to collect information like:

A Password field can be created to limit the access to few users by providing data validation to the Password field.





NAME- User Name for TIST Certificate
Email- User’s email for the request body of the DigitalHumani and TIST API 
Number of Trees wants to plant- treeCount for the request body of the DigitalHumani API




Submitting the Google Form will trigger the Zapier’s Flow that hits DigitalHumani and TIST API.


You can create a zap in Zapier using a trigger “New Form Response” comes from Google Form. It will fetch “treeCount” and “User’s email” from the Form Response for the request body of the API.(“enterpriseId” and “projectId” remain static by default), after the flow hits the Tree Planting API it will move to TIST API to create a certificate.






You can also get the TIST API (Provided by the TIST Reforestation Organization support) that sends Tree Plant Certificates to the user's email and organization’s Email(Your organization Email) 

.
Certificate API Request Method:- POST
Certificate API Request Body:- 
			{
   "Name": " user name from the Form Response",
   "User_email": "user’s email from the Form Response where user will receives certificate",
   "Company_email": "Email of your organization where you also receives a copy of  the user’s certificate",
   "Date": "Date can also be fetched from the Form Response in DD-MM-YYYY",
   "Tree": "treeCount from the Form Response"

}

You can use Zapier to fetch the certificate from the email and save in a database as well.

This TIST API will send certificates to end users as an appreciation.
