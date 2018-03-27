Appendix 
1.	API request for shipment rate.
2.	API request for create shipment
3.	API request for tracking order.
4.	API request for pickup number.



Test Keys 
App ID: CHWEBAPP171029095036 
Keys:    C913CC2948CF17406040F2C525E738A

 
<b>API Request for Shipment Rate</b>

Note: URL Method has to be POST<br>
URL: https://www.courierhome.com/apiservices/courier_rate <br>

Following parameters (all in small letter ) needs to be posted:<br>

appid : *******<br>
key : ******<br>
from_pincode : (pickup pincode) e.g. 110025<Br>
to_pincode : (destination pincode) e.g. 110025<Br>
weight : (in Kg) e.g  1<Br>
height : (in cm)<Br>
length : (in cm)<Br>
width : (in cm)<Br>
shipment_type :  (Prepaid or COD)<Br>
courier_type : document or parcel <Br>

Json Response <Br>
{
"response":"Success",
"rate_req_id":14,
"result":[
{
"courier_name":"aramex",
"from_pincode":"302021",
"to_pincode":"302034",
"image":"https:\/\/courierhome.com\/assets\/image\/aramex.png",
"weight":"2",
"type":"Prepaid",
"height":"4",
"length":"3",
"width":"2",
"base_price":123,
"fuel":46,
"weight_price":"",
"rto":"",
"dto":"",
"service_tax":34,
"expected_pickup_time":"5 PM",
"expected_pickup_date":"November 7, 2017",
"delivary_date":"November 11, 2017",
"total_amount":203
},
{
"courier_name":"delhivery",
"from_pincode":"302021",
"image":"https:\/\/courierhome.com\/assets\/image\/delhivery.png",
"to_pincode":"302034",
"weight":"2",
"type":"Prepaid",
"height":"4",
"length":"3",
"width":"2",
"base_price":189,
"fuel":95,
"weight_price":150,
"rto":150,
"dto":280,
"service_tax":49,
"expected_pickup_time":"1 PM",
"expected_pickup_date":"November 7, 2017",
"delivary_date":"November 11, 2017",
"total_amount":333
}
]
}
  
  
<b>API Request for Create Shipment</b>

Note: URL Method has to be POST<br>
URL: https://www.courierhome.com/apiservices/create_shipment_demo<br>

Following parameters (all in small letter ) needs to be posted:<br>

appid : *******<Br>
key : ******<Br>
courier_name: courier name from rate api<Br>
rate_req_id :  rate request id from rate api <Br>
order_no  : unique no to trace date <Br>
amount  : rate api response (total_amount) parameter<Br>
sender_name : test <Br>
sender_email :  sender email address (optional )<Br>
sender_phone : 1234567890 ( courier sender person phone  no )<Br>
sender_address :  test 1234 Delhi (courier pickup address)<Br>
sender_city : Delhi ( pickup city)<Br>
sender_state: Delhi ( pickup state)<Br>
sender_zipcode : 110025 (sender pickup pincode rate api (from_pincode) )<Br>
receiver_name : test (courier receiver name )<Br>
receiver_email : receiver email<Br>
receiver_phone : 1234567890 ( courier receiver person phone no  )<Br>
receiver_address : test 1234  Jaipur (courier pickup address)<Br>
receiver_city : Jaipur<Br>
receiver_state : Rajasthan (courier receiver State  )<Br>
receiver_zipcode : 110025 (sender pickup pincode rate api (to_pincode)<Br>
courier_type : document or parcel <Br>
shipment_type :  (Prepaid or COD)<Br>
item_decription : product description <Br>
item_value  : product value eg 1000<Br>
cod_value : 1000 (collectable price  for COD shipment type , for prepaid 0 )<Br>
quantity : 1 <Br>
weight : (in Kg) e.g  1<Br>
height : (in cm) 10<Br>
length : (in cm) 10<Br>
width : (in cm) 10<Br>


Response <Br>
{
"response":"Success",
"result":[
{
"order_no":"123456789",
"awb_number":"12345678",
"amount":"100",
"pickup_no":"12345678",
"pdf_url":"https:\/\/courierhome.com\/delhivery\/demo.pdf"
}
]
}
  
  
<b>API Request for Track Shipment</b>

Note: URL Method has to be POST<br>
URL: https://www.courierhome.com/apiservices/track_shipment<br>

Following parameters (all in small letter ) needs to be posted:<br>

appid : *******<br>
key : ******<br>
awb_number:2068724722<br>
courier_name : aramex    (holisol, delhivery, aramex, fedex_priority, fedex_economy)<br>

Json response <br>
{
"response":"Success",
"result":[
{
"UpdateDescription":"Delivered",
"UpdateDateTime":"2017-11-03T15:56:00",
"UpdateLocation":"Azadpur, India"
},
{
"UpdateDescription":"SMS Sent to Consignee",
"UpdateDateTime":"2017-11-03T09:09:00",
"UpdateLocation":"Gurgaon, India"
}
]
}



<b>API Request for Pickup Request</b>


Note: URL Method has to be POST<br>
URL: https://www.courierhome.com/apiservices/pickup_request<br>

Following parameters (all in small letter ) needs to be posted:<br>

appid : *******<br>
key : ******<br>
order_no:2068724722<br>
courier_name : aramex    ( delhivery, aramex, fedex_priority, fedex_economy)<br>

Json response <br>
{
"response":"Success",
"result":[
{
"pickup_no":"123456",
"message":"Updated Sucessfully"
}
]
}
