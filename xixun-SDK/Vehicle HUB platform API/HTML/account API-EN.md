# Account API

Instructions

Catalogue

1.1 download platform confirmation sample file

1.2 upload company license and platform confirmation file for company account

1.3 upload personal ID card front and back photo for personal account

1.4 get the company account without real name certificate 

1.5 get the personal account without real name certificate 

1.6 download enterprise license

1.7 download the confirmation file that uploaded by the enterprise

1.8 download ID card front photo

1.9 download ID card back photo

1.10 do real name certification for the account

Download platform confirmation sample file

url:"/v1/cms/account/downloadConfirmationFile"

mehtod:"get"

Need token or not： need, put the token into the query parameters auth_token-xxx

Download success and return the file

Upload company license and confirmation file for the company account

url:"/v1/cms/account/uploadCompanyLicense"

method :"post"

Need token or not： need,

Request data: submit form, data inside of form as following

Field  type  instructions 

organization  string    company name, required

licence   file ，input name="licence"  license ，required

confirmation  file ，input name="confirmation"  confirmation file，required

Success and return data

```
{

  "error_code": 12000,

  "msg": "upload success"

}
```

Upload ID card front and back photo for personal account

url:"/v1/cms/account/uploadPersonalLicence"

method :"post"

Need token or not: Need

Request data: submit form, data inside of form as following

Field  type  instructions

ID_number   string    name

frontOfID file，input name="frontOfID"    front of ID card

backOfID file，input name="backOfID"  back of ID card

success and return data

```
{

  "error_code": 12001,

  "msg": "upload success"

}
```

Get company account without real name certificate

url:"/v1/cms/account/getUnAuthoredCompanyAccount"

method:"get"

Need token or not: Need

Server return data

```
{

  "data": [

    {

    "id": "5f0d993ca514083774ba9291",

      "name": "",

      "address": "",

      "tel": "",

      "not_active": false,

      "organization": "xxx company",

      "type": "company_account",

      "id_number": "3209",

      "not_authorized": true

    }

  ],

  "error_code": 1000,

  "msg": "get list data success",

  "totalCount": 1

}
```

Get personal account without real name certificate 

url :"/v1/cms/account/getUnAuthoredPersonalAccount"

method :"get"

Need token or not: Need

Server return data for example

```
{

  "data": [

    {

      "id": "5f4777cfa51408189cb64d04",

      "name": "",

      "address": "",

      "tel": "",

      "not_active": false,

      "organization": "xxx company",

      "type": "personal_account",

      "id_number": "3209",

      "not_authorized": true

    },

    {

      "id": "5f0d993ca514083774ba9291",

      "name": "",

      "address": "",

      "tel": "",

      "not_active": false,

      "type": "personal_account",

      "id_number": "3209",

      "not_authorized": true

    }

  ],

  "error_code": 1000,

  "msg": "get list success",

  "totalCount": 2

}
```

Download company license 

url:"/v1/cms/account/:id/downAuthLicence"

method :"get"

Need token or not: Need, joint the token auth_token=xxx as the query parameters 

Download success and return file

Download confirmation file uploaded by the enterprise

url:"/v1/cms/account/:id/downAuthConfirmation"

method :"get"

Need token or not: Need, joint the token auth_token=xxx as the query parameters 

Download success and return file

Download front of ID card

url:"/v1/cms/account/:id/downloadAuthFrontOfID"

method :"get"

Need token or not: Need, joint the token auth_token=xxx as the query parameters

Download success and return file

Download back of ID card

url:"/v1/cms/account/:id/downloadAuthBackOfID"

method :"get"

Need token or not: Need, joint the token auth_token=xxx as the query parameters

Download success and return file

Do real name certificate for the account

url :"/v1/cms/account/:id/authorizeAccount"

method:"post"

Need token or not: Need

Server return data

```
{

  "error_code": 12001,

  "msg": "upload success”

}
```

