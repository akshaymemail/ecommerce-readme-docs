# E-Commerce Docs

Requirements of a ecommerce app

## Home Scree

Home screen gives popular categories, navbars and more

## Sub Category Screens

Gives popular sub categories according to selected category

## Products Screens

Give all products according to selected category

```
Method : GET https://yourdomain.com/endpoint
Response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"},}, ..........]
```

## Product Details

Get requested products details

```
Method : GET https://yourdomain.com/id
Response : {"_id":"604f7a4e255ceb1a10d6152c","name":"Nike Slim Shirt","category":"Shirts","image":"/images/p1.jpg","price":1299,"countInStock":10,"brand":"Nike","rating":4.5,"numReview":34,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.036Z","updatedAt":"2021-03-15T15:16:30.036Z"}
```

## Cart Screen

Get user all cart items

```
Method : GET https://yourdomain.com/endpoint
Response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"},}, ..........]
```

## Login Screen

Validate and login the already exist user

```
Method : POST https://yourdomain.com/endpoint
Payload : {"email":"akshaymemail@gmail.com","password":"akshay"}
Response : {"_id":"6051a10b64bf1f31ac562950","firstName":"AKSHAY","lastName":"SINGH","middleName":"KUMAR","email":"akshaymemail@gmail.com","isAdmin":true,"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MDUxYTEwYjY0YmYxZjMxYWM1NjI5NTAiLCJlbWFpbCI6ImFrc2hheW1lbWFpbEBnbWFpbC5jb20iLCJpc0FkbWluIjp0cnVlLCJpYXQiOjE2NTYzMjQyNzMsImV4cCI6MTY1ODkxNjI3M30.w8ZT-_0DUJQN8o5f6YlbCqLptvBOJ254j0o0FuTGcfg"}
```

## Register Screen

Register the user

```
Method : POST https://yourdomain.com/endpoint
Payload :- {"firstName":"AKSHAY","lastName":"KUMAR","email":"akshaymemail1@gmail.com","password":"123456"}
Response :- {"_id":"62b9815ebd8fb1001549ea1d","firstName":"AKSHAY","lastName":"KUMAR","email":"akshaymemail1@gmail.com","isAdmin":false,"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MmI5ODE1ZWJkOGZiMTAwMTU0OWVhMWQiLCJlbWFpbCI6ImFrc2hheW1lbWFpbDFAZ21haWwuY29tIiwiaXNBZG1pbiI6ZmFsc2UsImlhdCI6MTY1NjMyNDQ0NiwiZXhwIjoxNjU4OTE2NDQ2fQ.JiUTKomUjySvQSWV8E0Gh-Ye6B16dvLUJIYJbLlQSO0"}
```

## Shipping Screen

Add the user shipping address or use existing one

- get all user address

```
    Method : GET https://yourdomain.com/endpoint
    Response : [{.....}, {.......}]
```

- Add new shipping address

```
Method : POST https://yourdomain.com/endpoint
Payload : {"fullName":"john doe","mobileNumber":"283928323","pinCode":"323232","locality":"346dsfgsdf","address":"asda, ahdkhafs, akds","city":"adsla","state":"adfadsfad"}
Response : 201
```

## Payment Options

Responsible to show all payment options according to server side decision or static

## Payment Screen

Responsible for payment activity

## Success Screen

A success page screen that user have successfully ordered the item

## Order History Screen

Get user order history

```
Method : GET https://yourdomain.com/endpoint
Response : [{"shippingAddress":{"fullName":"AKSHAY SINGH","mobileNumber":"+918271097843","pinCode":"841301","locality":"JAY PRAKASH UNIVERSITY","address":"SHIVNAGRY","city":"CHAPRA","state":"BIHAR"},"isPaid":false,"isDelivered":false,"_id":"605eed0f821e03244c60692c","orderItems":[{"_id":"605eed0f821e03244c60692d","name":"Nike Slim Shirt","image":"/images/p1.jpg","price":1,"product":"604f7a4e255ceb1a10d6152c","quantity":1}],"paymentMethod":"PayPal","itemPrice":1,"shippingPrice":40,"totalPrice":1,"user":"6051a10b64bf1f31ac562950","createdAt":"2021-03-27T08:30:07.598Z","updatedAt":"2021-03-27T08:30:07.598Z","__v":0},{"shippingAddress":{"fullName":"AKSHAY SINGH","mobileNumber":"+918271097843","pinCode":"841301","locality":"JAY PRAKASH UNIVERSITY","address":"SHIVNAGRY","city":"CHAPRA","state":"BIHAR"},"isPaid":false,"isDelivered":false,"_id":"605ef092821e03244c60692e","orderItems":[{"_id":"605ef092821e03244c60692f","name":"Nike Slim Pant","image":"/images/p4.jpg","price":982,"product":"604f7a4e255ceb1a10d6152f","quantity":1}],"paymentMethod":"PayPal","itemPrice":982,"shippingPrice":0,"totalPrice":982,"user":"6051a10b64bf1f31ac562950","createdAt":"2021-03-27T08:45:06.746Z","updatedAt":"2021-03-27T08:45:06.746Z","__v":0}, ............]
```

## Order Details Screen

Get requested products details

```
Method : GET https://yourdomain.com/id
Response : {"shippingAddress":{"fullName":"AKSHAY KUMAR SINGH","mobileNumber":"8271097843","pinCode":"1234","locality":"6765756","address":"new shivpuri hapur","city":"Hapur","state":"BIHAR"},"isPaid":false,"isDelivered":false,"\_id":"621da98e94e4d600152b7bf0","orderItems":[{"_id":"621da98e94e4d600152b7bf1","name":"Nike Slim Pant","image":"/images/p4.jpg","price":982,"product":"604f7a4e255ceb1a10d6152f","quantity":2}],"paymentMethod":"PayPal","itemPrice":1964,"shippingPrice":0,"totalPrice":1964,"user":"6051a10b64bf1f31ac562950","createdAt":"2022-03-01T05:05:18.591Z","updatedAt":"2022-03-01T05:05:18.591Z","\_\_v":0}
```

## User Profile Details Screen

Get requested products details

```
Method : GET https://yourdomain.com/endpoint
Response : {"_id":"6051a10b64bf1f31ac562950","firstName":"AKSHAY","lastName":"SINGH","middleName":"KUMAR","email":"akshaymemail@gmail.com","isAdmin":true,"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MDUxYTEwYjY0YmYxZjMxYWM1NjI5NTAiLCJlbWFpbCI6ImFrc2hheW1lbWFpbEBnbWFpbC5jb20iLCJpc0FkbWluIjp0cnVlLCJpYXQiOjE2NTYzMjU5MjAsImV4cCI6MTY1ODkxNzkyMH0.8Zuxe8_Dwwp7u_ObYyEmV4CcGg_tBauVyFlpIeK5xL8"}
```
