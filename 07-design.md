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

### Sign In [POST]

You may creat your account using this action. It takes a JSON object
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

    + Body
    
                {
                    "info": "Sign In Successfully!"
                }
