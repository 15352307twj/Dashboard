---
layout: default
title: API Design
---

# Owl Design

## 7.3 API design
FORMAT: 1A
HOST: http://owl.apiblueprint.org/

## Owl API

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
            "Phone Num": "13536875792",
            "Password": "pwd@owl",
            "Nick Name": "Jacky",
            "Portrait": "some chosen image",
            "Gender": "male",
            "Birthday": "2000-04-12"
        }

+ Response 201 (application/json)

        {
            "State": "Signed Up Successfully!"
        }

### Log In [POST]

+ Request (application/json)

        {
            "Nick Name/Phone Num": "Jacky",
            "Password": "pwd@owl",
        }

+ Response 201 (application/json)

        {
            "State": "Logged In Successfully!"
        }
        
### Log Out [POST]

+ Request (application/json)

        {
            "Nick Name/Phone Num": "Jacky",
        }

+ Response 201 (application/json)

        {
            "State": "Logged Out Successfully!"
        }
        
### Comment on Movie [POST]

+ Request (application/json)

        {
            "Name": "Jacky's Adventure in HK",
            "Score": "7.5"
        }

+ Response (application/json)

        {
            "State": "Comment Successfully!"
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
            "Name": "Jacky's Adventure in HK",
            "Summary": "Jacky is spending his holiday in HK..."
        }

+ Response 201 (application/json)

        {
            "State": "successfully add movie",
            "ID": "114514",
            "Name": "Jacky's Adventure in HK",
            "Summary": "Jacky is spending his holiday in HK..."
            "Score": "7.0"
        }

### Delete Movie [POST]

This action should only be used by the system.

+ Request (application/json)

        {
            "Name": "Jacky's Adventure in HK"
        }

+ Response 201 (application/json)

        {
            "State": "Delete this movie?",
            "ID": "114514",
            "Name": "Jacky's Adventure in HK",
            "Summary": "Jacky is spending his holiday in HK..."
            "Score": "7.0"
        }

+ Request (application/json)

        {
            "Confirm Info": "Yes"
        }

+ Response 201 (application/json)

        {
            "State": "Delete movie successfully!"
        }
        
### Search Movie [POST]

+ Request (application/json)

        {
            "Name": "Jacky's Adventure in HK"
        }

+ Response 200 (application/json)

        [
            {
                "Movie Name": "Jacky's Adventure in HK",
                "Summary": "Jacky is spending his holiday in HK...",
                "Score": "7.0"
                "Available Cinemas": [
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

### Search Cinema by Name[POST]

+ Request (application/json)

        {
            "Name": "Jacky's Cinema"
        }

+ Response 200 (application/json)

        [
            {
                "Name": "Jacky's Cinema",
                "Location": "Guangzhou",
                "Movie Number": "7"
                "Food Suppliers": [
                                        "Mc Turkey",
                                        "Ken Hut"
                                ]
            }
        ]

### Search Cinema by District[POST]

+ Request (application/json)

        {
            "District": "BaiYun District"
        }

+ Response 200 (application/json)

        [
            {
                "Name": "Jacky's Cinema",
                "Location": "BaiYun District Jacky Road 114",
                "Movie Number": "7"
                "Food Suppliers": [
                                        "Mc Turkey",
                                        "Ken Hut"
                                ]
            }
        ]

### List All Movies [GET]

+ Response 200 (application/json)

        [
            {
                "Movie Name": "Jacky's Adventure in HK",
                "Summary": "Jacky is spending his holiday in HK...",
                "Score": "7.0"
            }
        ]

## Tickets Collection [/tickets]

A movie ticket has the following attributes:
- MovieID
- CinemaID
- Price

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
