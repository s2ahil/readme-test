---
id: express-mongoose-application
title: sample course selling api (express)
sidebar_label: NodeJS - Express + Mongoose
description: The following sample app showcases how to use NodeJS framework and the Keploy Platform.
tags:
  - javascript
  - quickstart
  - samples
  - examples
  - tutorial
keyword:
  - NodeJS Framework
  - MongoDB
  - NodeJS
  - API Test generator
  - Auto Testcase generation
---

## Introduction

A simple sample CRUD application and see how seamlessly Keploy integrates with [Express](https://expressjs.com/) and [MongoDB](https://www.mongodb.com/). Buckle up, it's gonna be a fun ride! 🎢

import InstallationGuide from '../concepts/installation.md'

<InstallationGuide/>

## Get Started! 🎬

Clone the repository and move to express-mongoose folder

```bash
git clone https://github.com/keploy/samples-typescript && cd samples-typescript/express-mongoose-Sahil

# Install the dependencies
npm install
```

## Installation 📥

Let's get started by setting up the Keploy with this command:

``` bash
curl --silent --location "https://github.com/keploy/keploy/releases/latest/download/keploy_linux_amd64.tar.gz" | tar xz -C /tmp

sudo mkdir -p /usr/local/bin && sudo mv /tmp/keploy /usr/local/bin && keploy
```



### Lights, Camera, Record! 🎥


#### Capturing Testcases

```bash
keploy record -c "npm start"
```

if using wsl use this :
```bash
sudo -E env PATH=$PATH keploy record -c 'npm start'
```


🔥 Challenge time! Generate some test cases. How? Just **make some API calls**. Postman, Hoppscotch or even curl - take your pick!

#### Let's generate the testcases.

Make API Calls using [Hoppscotch](https://hoppscotch.io), [Postman](https://postman.com) or cURL command. Keploy with capture those calls to generate the test-suites containing testcases and data mocks.


🎉 Woohoo! With a simple API call, you've crafted a test case with a mock! Dive into the Keploy directory and feast your eyes on the newly minted `test-1.yml` and `mocks.yml` after doing below steps 

_Time to perform  API magic!_
Follow the breadcrumbs... or Make more API Calls

Some api calls you can make 

Get request - Get all courses
```bash
curl --request GET \
--url http://localhost:3000/courses
```

Post request  - Add a new course
```bash
curl --location 'http://localhost:3000/courses' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'title=react advance' \
--data-urlencode 'description=advance' \
--data-urlencode 'price=1000' \
--data-urlencode 'published=true'
```

Put request - Add a new course
- Make sure to replace id of course 
```bash
curl --location --request PUT 'http://localhost:3000/courses/6626a9cd3840cb305c0a6d52' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'title=react advance'
```

Delete request - Delete a course 
- Make sure to replace id of course 
```bash
curl --location --request DELETE 'http://localhost:3000/courses/6626a9cd3840cb305c0a6d52'
```


Or simply wander over to your browser and visit `http://localhost:3000/courses`.

Did you spot the new test and mock scrolls in your project library? Awesome! 👏

### Run Tests

Time to put things to the test 🧪

```bash
keploy test -c "npm start" --delay 10
```
If using wsl use this :
```bash
keploy -E env PATH=$PATH keploy test -c 'npm start' --delay 10
```

Keploy test report:
![image](https://github.com/s2ahil/samples-typescript/assets/101473078/48f2b866-04d1-433b-9270-34c15786893c)

> The `--delay` flag? Oh, that's just giving your app a little breather (in seconds) before the test cases come knocking.


### To Run test using jest use this command : 
``` bash
npm test
```
jest test coverage report : 
![Screenshot 2024-04-22 025850](https://github.com/s2ahil/samples-typescript/assets/101473078/f60570d0-b998-4b4a-912d-80d4c73604e3)

### Wrapping it up 🎉

Congrats on the journey so far! You've seen Keploy's power, flexed your coding muscles, and had a bit of fun too! Now, go out there and keep exploring, innovating, and creating! Remember, with the right tools and a sprinkle of fun, anything's possible.😊🚀

Happy coding! ✨👩‍💻👨‍💻✨


