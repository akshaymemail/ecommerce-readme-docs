# API requirements of a ecommerce app

## PRODUCTS AND CATEGORIES

Top categories

```
Method : GET https://api.domain.com/v1/categories/page=1&limit=10
response : [
    {
        id : 1,
        name : fashion,
        ...
        ...
    }
    ...
    ...
]
```

Product Category

```
Method : GET https://api.domain.com/v1/category/1
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"},}, ..........]
```

Banners

```
Method : GET https://api.domain.com/v1/banners
response : [
    {
        id : 1,
        banner : 'https://domain.com/assets/banner1.jpg,
        action : 'new-products'
        ...
        ...
    }
    ...
    ...
]
```

New Products

```
Method : GET https://api.domain.com/v1/products/page=1&limit=10
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]
```

Product details

```
Method : GET https://api.domain.com/v1/product/604f7a4e255ceb1a10d61
response : {
    details : {"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"},
    similar : [
        {"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"},
        {"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}
    ]
}
```

Deals of the day

```
Method : GET https://api.domain.com/v1/deals/page=1&limit=10
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]
```

Trending Products

```
Method : GET https://api.domain.com/v1/trending/page=1&limit=10
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]
```

Filter Rules for each category

```
Method : GET https://api.domain.com/v1/category/id/filter_rules
response : [{
    tags : ['t-shirt', 'women clothes', 'shoes' ....]
    sizes : [10,2,3,4,34,35]
    colors : ['red', 'gree', 'blue']
    price : {
        min : 1000,
        max : 500000
    }
}]
```

Filter by category

```
Method : POST https://api.domain.com/v1/category/id/filter
payload : {
    tags : ['t-shirt' 'shoes' ....]
    sizes : [10,35]
    colors : ['red']
    price : {
        min : 3000,
        max : 4000
    }
}
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]

```

Search

```

Method : POST https://api.domain.com/v1/search
payload : {
    query : "new jeans"
    page : 1,
    limit : 10
}
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]

```

## CART

Add to cart

```

Method : POST https://api.domain.com/v1/user/cart
payload : [
    {"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"},
    {"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}
]
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]

```

Get User Cart

```

Method : GET https://api.domain.com/v1/user/cart
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]

```

Place Order

```

Placing order will includes payments integration and more

```

## USER

Register a new user

```
Method : POST https://api.domain.com/v1/user/signup
payload : {
    first_name : "john"
    last_name : "doe"
    email : "something@example.com"
    phone : +919823832323
    password : '232#03023"
}

response : {
    message : "An 6 digit otp is sent to your mobile and email address"
}

```

Verify the user

```
Method : POST https://api.domain.com/v1/user/signup/verify
payload : {
    phone : "233233"
    email : "040334"
}
response : {
    message : "You have successfully verified"
}

```

Login user

```
Method : POST https://api.domain.com/v1/user/login
payload : {

    email : "something@example.com"
    password : '232#03023"
}

response : {"_id":"6051a10b64bf1f31ac562950","firstName":"AKSHAY","lastName":"SINGH","middleName":"KUMAR","email":"akshaymemail@gmail.com","isAdmin":true,"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2MDUxYTEwYjY0YmYxZjMxYWM1NjI5NTAiLCJlbWFpbCI6ImFrc2hheW1lbWFpbEBnbWFpbC5jb20iLCJpc0FkbWluIjp0cnVlLCJpYXQiOjE2NTcwMTk4MjgsImV4cCI6MTY1OTYxMTgyOH0.ULmehdsOOVX7-3sG_8jVl5rmUq17DDTDGXkX1-5Z4Mo"}

```

Update Profile

```
Method : UPDATE https://api.domain.com/v1/user/update
payload : {

    name : "john doe"
    email : 'something@example.com"
    phone : "974923

}

response : {
    message : "Updated successfully!"
}

```

Get Wish List

```
Method : GET https://api.domain.com/v1/user/wish_list
response : {[{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]

```

Add a Wish

```
Method : POST https://api.domain.com/v1/user/wish_add
payload : {
    id : 6051a10b64bf1f31ac562950

}

response : {
    message : "Added successfully!"
}

```

Remove a Wish

```
Method : POST https://api.domain.com/v1/user/wish_add
payload : {
    id : 6051a10b64bf1f31ac562950

}

response : {
    message : "Removed successfully!"
}

```

Get all address

```
Method : GET https://api.domain.com/v1/user/addresses
response : [{name : "john", street : '11 new york", locality : "subway park"}, ..........]

```

Add a address

```
Method : POST https://api.domain.com/v1/user/address/add
payload : {
    name : "john", street : '11 new york", locality : "subway park"
    }
response : {
    message : "Added successfully!"
}

```

Update address

```
Method : UPDATE https://api.domain.com/v1/user/address/update/:id
payload : {
    name : "john", street : '11 new york", locality : "subway park"
    }

response : {
    message : "Updated successfully!"
}

```

Delete address

```
Method : POST https://api.domain.com/v1/user/address/delete
payload : {
    id : 6051a10b64bf1f31ac562950

}

response : {
    message : "Removed successfully!"
}

```

Get Orders

```
Method : GET https://api.domain.com/v1/user/orders
response : [{"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}, ..........]

```

Orders Details

```
Method : GET https://api.domain.com/v1/user/orders/:id
response : {"_id":"604f7a4e255ceb1a10d6152f","name":"Nike Slim Pant","category":"Pants","image":"/images/p4.jpg","price":982,"countInStock":12,"brand":"Nike","rating":4.5,"numReview":56,"description":"Best in class","__v":0,"createdAt":"2021-03-15T15:16:30.039Z","updatedAt":"2021-03-15T15:16:30.039Z"}

```

update password

```
Method : UPDATE https://api.domain.com/v1/user/password
payload : {
    old_password : "928323ed"
    new_password : "02eod23f"
}

response : {
    message : "Updated successfully!"
}

```

Logout user

```
Method : POST https://api.domain.com/v1/user/logout


```
