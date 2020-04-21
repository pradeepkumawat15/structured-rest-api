# structured_rest_api
To run this project
a) clone this repo to your local system.
b) open the project in vd code. Open the terminal of the vs-code (you can use your system terminal as well)
   in terminal type <npm install> , this command should run in the root folder of the project. Make sure internet is available to your system.
c) next run this comman <npm start> , this will start the server on port 3000.

How to use this API  ? :
1. you can create any front-end application and use this api. But if you don't want to create any front-end app then follow next steps.
2. install postman to your system.
3. Base URL : localhost:3000/hotels

	a) get method to fetch all hotels data: 
		hit this url in postman : localhost:3000/hotels
		you will get reponse : 
		
		{"message":"Handling get requests to /hotels. All hotels list is provided to you as following","hotels":{"hotel1":{"label":"My Hotel","locationName":"Siliguri","locationId":"734006","id":"777","fullName":"My Hotel Full Name","full_address":"siliguri Isckon Temple"},"hotel2":{"label":"My Hotel","locationName":"Siliguri","locationId":"734006","id":"777","fullName":"My Hotel Full Name","full_address":"siliguri Isckon Temple"}}}
		
	b) get method to fetch single hotel data 
		hit this url in postman : localhost:3000/hotels/25  (25 is hotel id of which data needs to be fetched)
		you will get response : 
		
		{"message":"Handling get requests to /hotels. A request  to fetch a particulal hotel with hotelId = 25","hotel":{"label":"My Hotel","locationName":"Siliguri","locationId":"734006","id":"777","fullName":"My Hotel Full Name","full_address":"siliguri Isckon Temple"}}
		
	c) post method to create a hotel
		Enter this json body in the body of the request : 
		
		{
    "label": "My Hotel",
    "locationName": "Siliguri",
    "locationId": "734006",
    "id": "777",
    "fullName": "My Hotel Full Name",
    "full_address": "siliguri Isckon Temple"
}

		hit this url in postman : localhost:3000/hotels
		you will get following response : 
		
		{"message":"Handling post requests to /hotels. A request to create a hotel is sujbmitted with following request_body","request_body":{"label":"My Hotel","locationName":"Siliguri","locationId":"734006","id":"777","fullName":"My Hotel Full Name","full_address":"siliguri Isckon Temple"}}
		
		
	d) PATCH method to update a hotel data
				hit this url in postman : localhost:3000/hotels/63  (63 is hotel id of which data needs to be fetched)
		you will get response : 
		
		{"message":"Handling patch requests to /hotels. A request to update a particulal hotel with hotelId = 63"}
		
	e) DELETE method to delete a hotel data
				hit this url in postman : localhost:3000/hotels/60  (60 is hotel id of which data needs to be fetched)
		you will get response : 
		
		{"message":"Handling delete requests to /hotels. A request to delete a particulal hotel with hotelId = 60"}
		
Note  : If you will try to send request which is not defined as mentioned above, you should get error.

e.g. : In our case we have designed POST method in such a way that it does not accept any request parameter in the URL.
		Correct : localhost:3000/hotels
		Incorrect : localhost:3000/hotels/65   (THis should generate error which we are handling in our code)
		response : {"error":{"message":"Not found"}}
		
