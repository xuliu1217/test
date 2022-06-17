1. Database
   -- for mysql, please check the coding part
   -- mongodb
      -- Create `test`DB: `use test`
      -- Create `oms_company_address` collection: `db.createCollection("oms_company_address")`
      -- Insert few random entries to `oms_company_address` collection (method: insert() )
```
db.oms_company_address.insertMany ( [
      { id: 1, address_name: "1st street", send_status: 1, receive_status: 1, name: "Alice", phone: "111-111-1111", province: "A", city: "A", region: "A", detail_address: "1st AVE" },
      { id: 2, address_name: "2nd street", send_status: 1, receive_status: 1, name: "Bob", phone: "222-222-2222", province: "B", city: "B", region: "B", detail_address: "2nd AVE" },
      { id: 3, address_name: "3rd street", send_status: 0, receive_status: 0, name: "Cindy", phone: "333-333-3333", province: "C", city: "C", region: "C", detail_address: "3rd AVE" },
      { id: 4, address_name: "4th street", send_status: 0, receive_status: 0, name: "Dave", phone: "444-444-4444", province: "D", city: "D", region: "D", detail_address: "4th AVE" },
      { id: 5, address_name: "5th street", send_status: 1, receive_status: 0, name: "Emma", phone: "555-555-5555", province: "E", city: "E", region: "E", detail_address: "5th AVE" } ] );
```
      -- Read one entry from `oms_company_address` collection: `db.oms_company_address.findOne()`;
      -- Read all entries from `oms_company_address`: `db.oms_company_address.find()`;
      -- Update one entry from `oms_company_address`collection
`db.oms_company_address.update({"id":1},{$set:{"send_status":0}} )`;
      -- Remove one entry from `oms_company_address`collection :
`db.oms_company_address.remove({"id":1})`;

2. POSTMAN
   -- GET
      -- GET https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87abe
      -- response type: 200 OK
      -- response body
```
{
    "id": "2baf70d1-42bb-4437-b551-e5fed5a87abe",
    "title": "Castle in the Sky",
    "original_title": "天空の城ラピュタ",
    "original_title_romanised": "Tenkū no shiro Rapyuta",
    "image": "https://image.tmdb.org/t/p/w600_and_h900_bestv2/npOnzAbLh6VOIu3naU5QaEcTepo.jpg",
    "movie_banner": "https://image.tmdb.org/t/p/w533_and_h300_bestv2/3cyjYtLWCBE1uvWINHFsFnE8LUK.jpg",
    "description": "The orphan Sheeta inherited a mysterious crystal that links her to the mythical sky-kingdom of Laputa. With the help of resourceful Pazu and a rollicking band of sky pirates, she makes her way to the ruins of the once-great civilization. Sheeta and Pazu must outwit the evil Muska, who plans to use Laputa's science to make himself ruler of the world.",
    "director": "Hayao Miyazaki",
    "producer": "Isao Takahata",
    "release_date": "1986",
    "running_time": "124",
    "rt_score": "95",
    "people": [
        "https://ghibliapi.herokuapp.com/people/598f7048-74ff-41e0-92ef-87dc1ad980a9",
        "https://ghibliapi.herokuapp.com/people/fe93adf2-2f3a-4ec4-9f68-5422f1b87c01",
        "https://ghibliapi.herokuapp.com/people/3bc0b41e-3569-4d20-ae73-2da329bf0786",
        "https://ghibliapi.herokuapp.com/people/40c005ce-3725-4f15-8409-3e1b1b14b583",
        "https://ghibliapi.herokuapp.com/people/5c83c12a-62d5-4e92-8672-33ac76ae1fa0",
        "https://ghibliapi.herokuapp.com/people/e08880d0-6938-44f3-b179-81947e7873fc",
        "https://ghibliapi.herokuapp.com/people/2a1dad70-802a-459d-8cc2-4ebd8821248b"
    ],
    "species": [
        "https://ghibliapi.herokuapp.com/species/af3910a6-429f-4c74-9ad5-dfe1c4aa04f2"
    ],
    "locations": [
        "https://ghibliapi.herokuapp.com/locations/"
    ],
    "vehicles": [
        "https://ghibliapi.herokuapp.com/vehicles/4e09b023-f650-4747-9ab9-eacf14540cfb"
    ],
    "url": "https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87abe"
}
    ```
      -- ----------------------------------------------------------------------
      -- GET https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87dec
      -- response type: 404 Not Found
      -- no response body
      -- ----------------------------------------------------------------------

      -- GET https://web.postman.co/workspace
      -- response type: 401 Unauthorized
      -- response body: 
```
{
    "error": {
        "name": "authenticationError",
        "message": "You are not authenticated by the server."
    }
}
```
      -- --------------------------------------------------------------
      -- GET https://ghibliapi.herokuapp.com/Vehicles
      -- response type: 200 OK
      -- response body: 
```
[
    {
        "id": "4e09b023-f650-4747-9ab9-eacf14540cfb",
        "name": "Air Destroyer Goliath",
        "description": "A military airship utilized by the government to access Laputa",
        "vehicle_class": "Airship",
        "length": "1,000",
        "pilot": "https://ghibliapi.herokuapp.com/people/40c005ce-3725-4f15-8409-3e1b1b14b583",
        "films": [
            "https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87abe"
        ],
        "url": "https://ghibliapi.herokuapp.com/vehicles/4e09b023-f650-4747-9ab9-eacf14540cfb"
    },
    {
        "id": "d8f893b5-1dd9-41a1-9918-0099c1aa2de8",
        "name": "Red Wing",
        "description": "An experimental aircraft captured by Porco. Named Savoia S.21",
        "vehicle_class": "Airplane",
        "length": "20",
        "pilot": "https://ghibliapi.herokuapp.com/people/6523068d-f5a9-4150-bf5b-76abe6fb42c3",
        "films": [
            "https://ghibliapi.herokuapp.com/films/ebbb6b7c-945c-41ee-a792-de0e43191bd8"
        ],
        "url": "https://ghibliapi.herokuapp.com/vehicles/d8f893b5-1dd9-41a1-9918-0099c1aa2de8"
    },
    {
        "id": "923d70c9-8f15-4972-ad53-0128b261d628",
        "name": "Sosuke's Boat",
        "description": "A toy boat where Sosuke plays",
        "vehicle_class": "Boat",
        "length": "10",
        "pilot": "https://ghibliapi.herokuapp.com/people/a10f64f3-e0b6-4a94-bf30-87ad8bc51607",
        "films": [
            "https://ghibliapi.herokuapp.com/films/758bf02e-3122-46e0-884e-67cf83df1786"
        ],
        "url": "https://ghibliapi.herokuapp.com/vehicles/923d70c9-8f15-4972-ad53-0128b261d628"
    }
]
```
      -- -----------------------------------------------------------------
      -- GET https://www.liaoxuefeng.com/wiki
      -- response type: 404 NOT FOUND
      -- response body:
```
{
    "timestamp": "2022-06-17T18:53:32.547+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/wiki"
}
```
      -- ---------------------------------------------------------------------


   -- post
      --POST https://ghibliapi.herokuapp.com/Vehicles
      --request body
```

 {
        "id": "4e09b023-f650-4747-9ab9-eacf14540abc",
        "name": "Air Destroyer Goliath",
        "description": "A military airship utilized by the government to access Laputa",
        "vehicle_class": "Airship",
        "length": "1,000",
        "pilot": "https://ghibliapi.herokuapp.com/people/40c005ce-3725-4f15-8409-3e1b1b14b583",
        "films": [
            "https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87abe"
        ],
        "url": "https://ghibliapi.herokuapp.com/vehicles/4e09b023-f650-4747-9ab9-eacf14540abc"
    }
      -- response type: 201 Created
      -- response body:
```
  
 {
        "id": "4e09b023-f650-4747-9ab9-eacf14540abc",
        "name": "Air Destroyer Goliath",
        "description": "A military airship utilized by the government to access Laputa",
        "vehicle_class": "Airship",
        "length": "1,000",
        "pilot": "https://ghibliapi.herokuapp.com/people/40c005ce-3725-4f15-8409-3e1b1b14b583",
        "films": [
            "https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87abe"
        ],
        "url": "https://ghibliapi.herokuapp.com/vehicles/4e09b023-f650-4747-9ab9-eacf14540abc"
    }
```
      -- --------------------------------------------------------------------
      -- POST https://www.liaoxuefeng.com/wiki
      -- response type: 404 NOT FOUND
      -- response body:
```
{
    "timestamp": "2022-06-17T18:56:01.909+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/wiki"
}
```
      -- ---------------------------------------------------------------------

      -- POST https://ghibliapi.herokuapp.com/#section/Use-Case
      -- response type: 404 NOT FOUND
      -- response body:
```
{}
```
            -- ------------------------------------------------------------------

      -- POST https://ghibliapi.herokuapp.com/Species
      -- response type: 201 Created
      -- response body:
```
{
    "id": "203c49c5-7eed-4c98-ade7-7d00b802511b"
}
```
      -- ----------------------------------------------------------------------


      -- POST https://ghibliapi.herokuapp.com/Species
      -- request body
```
{
    "id": "203c49c5-7eed-4c98-ade7-7d00b8025220"
}
```
      -- response type: 201 Created
      -- response body:
```
{
    "id": "203c49c5-7eed-4c98-ade7-7d00b802511b"
}
```
      -- ----------------------------------------------------------------------
   
   -- put
      -- PUT https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT/new.html
      -- request body:none
      -- response type: 403 Forbidden
      -- response body
```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<HTML>

<HEAD>
	<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">
	<TITLE>ERROR: The request could not be satisfied</TITLE>
</HEAD>

<BODY>
	<H1>403 ERROR</H1>
	<H2>The request could not be satisfied.</H2>
	<HR noshade size="1px">
	This distribution is not configured to allow the HTTP request method that was used for this request. The
	distribution supports only cachable requests.
	We can't connect to the server for this app or website at this time. There might be too much traffic or a
	configuration error. Try again later, or contact the app or website owner.
	<BR clear="all">
If you provide content to customers through CloudFront, you can find steps to troubleshoot and help prevent this error by reviewing the CloudFront documentation.
	<BR clear="all">
	<HR noshade size="1px">
	<PRE>
Generated by cloudfront (CloudFront)
Request ID: RF56dpWkEoFOhBS-hElmTUtLUiWtsDoksfii0Z1_nbble9TWxtAo3Q==
</PRE>
	<ADDRESS>
	</ADDRESS>
</BODY>

</HTML>
```
      -- ----------------------------------------------------------------------
      -- PUT https://ghibliapi.herokuapp.com/Films
      -- request body:
```
 {
        "id": "2baf70d1-42bb-4437-b551-e5fed5a87efg",
        "title": "Castle in the Sky",
        "original_title": "天空の城ラピュタ",
        "original_title_romanised": "Tenkū no shiro Rapyuta",
        "image": "https://image.tmdb.org/t/p/w600_and_h900_bestv2/npOnzAbLh6VOIu3naU5QaEcTepo.jpg",
        "movie_banner": "https://image.tmdb.org/t/p/w533_and_h300_bestv2/3cyjYtLWCBE1uvWINHFsFnE8LUK.jpg",
        "description": "The orphan Sheeta inherited a mysterious crystal that links her to the mythical sky-kingdom of Laputa. With the help of resourceful Pazu and a rollicking band of sky pirates, she makes her way to the ruins of the once-great civilization. Sheeta and Pazu must outwit the evil Muska, who plans to use Laputa's science to make himself ruler of the world.",
        "director": "Hayao Miyazaki",
        "producer": "Isao Takahata",
        "release_date": "1986",
        "running_time": "124",
        "rt_score": "95",
        "people": [
            "https://ghibliapi.herokuapp.com/people/598f7048-74ff-41e0-92ef-87dc1ad980a9",
            "https://ghibliapi.herokuapp.com/people/fe93adf2-2f3a-4ec4-9f68-5422f1b87c01",
            "https://ghibliapi.herokuapp.com/people/3bc0b41e-3569-4d20-ae73-2da329bf0786",
            "https://ghibliapi.herokuapp.com/people/40c005ce-3725-4f15-8409-3e1b1b14b583",
            "https://ghibliapi.herokuapp.com/people/5c83c12a-62d5-4e92-8672-33ac76ae1fa0",
            "https://ghibliapi.herokuapp.com/people/e08880d0-6938-44f3-b179-81947e7873fc",
            "https://ghibliapi.herokuapp.com/people/2a1dad70-802a-459d-8cc2-4ebd8821248b"
        ],
        "species": [
            "https://ghibliapi.herokuapp.com/species/af3910a6-429f-4c74-9ad5-dfe1c4aa04f2"
        ],
        "locations": [
            "https://ghibliapi.herokuapp.com/locations/"
        ],
        "vehicles": [
            "https://ghibliapi.herokuapp.com/vehicles/4e09b023-f650-4747-9ab9-eacf14540cfb"
        ],
        "url": "https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87efg"
    }
```
      -- response type:404 Not Found
      -- response body
```
{}
```
      -- ----------------------------------------------------------------------

      -- PUT  https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87abe
      -- request body: none
      -- response type: 200 OK
      -- response body:
```
{
    "id": "2baf70d1-42bb-4437-b551-e5fed5a87abe"
}
```
      -- ----------------------------------------------------------------------

   -- delete
      -- DELETE  https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87abe
      -- request body: none
      -- response type: 200 OK
      -- response body:
```
{}
```
      -- ----------------------------------------------------------------------
      -- DELETE  https://ghibliapi.herokuapp.com/films/2baf70d1-42bb-4437-b551-e5fed5a87ABF
      -- request body: none
      -- response type: 404 Not Found
      -- response body:
```
{}
```
   -- -----------------------------------------------------------------------
3. API
   -- twitter(twitter premium API/AccountActivity)
      -- List active subscripition: Get https://api.twitter.com/1.1/account_activity/all/{{environment}}/subscriptions/list.json
      -- Create subscription: POST https://api.twitter.com/1.1/account_activity/all/{{environment}}/subscriptions.json
      -- Check or reset webhook URL: PUT https://api.twitter.com/1.1/account_activity/all/{{environment}}/webhooks/:webhook_id?oauth_consumer_key=your premium App consumer key&oauth_nonce=UqnkudcQe1t&oauth_signature=DOlAihn1wQiWZVrvuGxK0+Dc+Yg=&oauth_signature_method=HMAC-SHA1&oauth_timestamp=1625004314&oauth_token=your user access token
   -- Delete subscription: DELETE https://api.twitter.com/1.1/account_activity/all/{{environment}}/subscriptions/:user_id

   -- META(On-premised API)
      -- create user: POST {{URL}}/v1/users
      -- get admin: {{URL}}/v1/users/{{AdminUsername}}
      -- update user: {{URL}}/v1/users/{{UserUsername}}
      -- delete use:{{URL}}/v1/users/{{UserUsername}}

   -- Design a collection of APIs for a blog website
      -- create user: POST https://weibo.com/us/v1/users
      -- get admin: https://weibo.com/us/v1/users/{{AdminUsername}}
      -- update user: https://weibo.com/us/v1/users/{{UserUsername}}
      -- delete use:https://weibo.com/us/v1/users/{{UserUsername}}
    
