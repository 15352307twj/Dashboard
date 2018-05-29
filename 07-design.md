---
layout: default
title: 设计
---

# Owl Design

## 7.1 UI Design

1. 首页
![首页](/assets/首页.png)

2. 电影页面
![电影](/assets/电影.png)

3. 影院页面
![影院](/assets/影院.png)

4. 登陆注册
  ![注册](/assets/注册.png)

  ![登陆](/assets/登陆.png)

5. 购买影票
  ![影片详情](/assets/影片详情.png)

  ![座位](/assets/座位.png)

## 7.2 Database design
![7.2](/assets/7.2.png)
[Issue 1](https://github.com/Owl-Movies-Ticket-System/Dashboard/issues/2)
[Issue 2](https://github.com/Owl-Movies-Ticket-System/Dashboard/issues/3)

## 7.3 API design
FORMAT: 1A
HOST: http://owl.apiblueprint.org/

# Owl API

Owl is a system for buying movie tickets. You could look
for updated infomation about movies here, as well as ordering
snacks such as popcorn.

## Customer Collection [/customer]

Customers are people who have already signed in Owl. A customer
has the following attributes: 

- ID
- Phone Num
- Password
- Nick Name
- Portrait
- Gender
- Birthday

### Sign Up [POST]

You may create your account using this action. It takes a JSON object
containing your information.

+ Request (application/json)

        {
            "phone_number": "13536875792",
            "password": "pwd@owl",
            "nickname": "Jacky",
            "portrait": "some chosen image",
            "sex": "male",
            "birth": "2000-04-12"
        }

+ Response 201 (application/json)

        {
            "state": "Signed Up Successfully!"
        }

### Log In [POST]

+ Request (application/json)

        {
            "phone_number": "13536875792",
            "password": "pwd@owl",
        }

+ Response 201 (application/json)

        {
            "state": "Logged In Successfully!"
        }
        
### Log Out [POST]

+ Request (application/json)

        {
            "phone_number": "13536875792",
        }

+ Response 201 (application/json)

        {
            "state": "Logged Out Successfully!"
        }
        
### Comment on Movie [POST]

+ Request (application/json)

        {
            "name": "Jacky's Adventure in HK",
            "rate": "7.5"
        }

+ Response (application/json)

        {
            "state": "Comment Successfully!"
        }


## Movies Collection [/movies]

A movie has the following attributes:
- ID
- Name
- Summary
- Score

### Add Movie [POST]

This action should only be used by the system.

+ Request (application/json)

        {
            "name": "Jacky's Adventure in HK",
            "introduction": "Jacky is spending his holiday in HK..."
        }

+ Response 201 (application/json)

        {
            "state": "successfully add movie",
            "movie_id": "114514",
            "name": "Jacky's Adventure in HK",
            "introduction": "Jacky is spending his holiday in HK..."
            "rate": "7.0"
        }

### Delete Movie [POST]

This action should only be used by the system.

+ Request (application/json)

        {
            "Name": "Jacky's Adventure in HK"
        }

+ Response 201 (application/json)

        {
            "state": "Delete this movie?",
            "movie_id": "114514",
            "name": "Jacky's Adventure in HK",
            "introduction": "Jacky is spending his holiday in HK..."
            "rate": "7.0"
        }

+ Request (application/json)

        {
            "confirm_info": "Yes"
        }

+ Response 201 (application/json)

        {
            "state": "Delete movie successfully!"
        }
        
### Search Movie [POST]

+ Request (application/json)

        {
            "name": "Jacky's Adventure in HK"
        }

+ Response 200 (application/json)

        [
            {
                "name": "Jacky's Adventure in HK",
                "introduction": "Jacky is spending his holiday in HK...",
                "rate": "7.0"
                "available_cinemas": [
                                        "Jacky's Cinema",
                                        "Andy's Cinema"
                                    ]
            }
        ]

## Cinemas Collection [/cinemas]

A cinema has the following attributes:
- ID
- Location
- MovieNum

### Search Cinema [POST]

+ Request (application/json)

        {
            "name": "Jacky's Cinema"
        }

+ Response 200 (application/json)

        [
            {
                "name": "Jacky's Cinema",
                "location": "Guangzhou",
                "movie_number": "7"
                "food_suppliers": [
                                        "Mc Turkey",
                                        "Ken Hut"
                                ]
            }
        ]

### List All Movies [GET]

+ Response 200 (application/json)

        [
            {
                "name": "Jacky's Adventure in HK",
                "introduction": "Jacky is spending his holiday in HK...",
                "rate": "7.0"
            }
        ]

## Tickets Collection [/tickets]

A movie ticket has the following attributes:
- order_id
- member_id
- create_date
- movie_id
- cinema_id

## Food Suppliers Collection [/foodSuppliers]

A food supplier has the following attributes:
- ID
- CinemaID

### List All Service [GET]

+ Response 200 (application/json)

        [
            {
                "Name": "Jacky's Favourite Meal",
                "Content": "Hamburger, Cola...",
                "Price": "$50"
            }
        ]

## Food Services Collection [/foodServices]

A food service has the following attributes:
- ID
- SupplierID
- Name
- Content
- Price

## Payment Systems Collection [/paymentSystems]

A payment system has the following attributes:
- ID
- Name
