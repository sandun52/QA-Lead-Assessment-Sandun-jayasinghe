

DEMO VIDEO Part 1: API Testing
https://drive.google.com/file/d/18dhxvXRK8NoBRG9NNLi5sF8qiRzGf_Qq/view?usp=drive_link





get 
https://jsonplaceholder.typicode.com//posts

test 
pm.test("Status code is 200",()=>{pm.response.to.have.status(200);});
pm.test("Response is an array",()=>{const jsonData=pm.response.json();
pm.expect(Array.isArray(jsonData)).to.be.true});

pm.test("Data verify",()=>{
    const jsonData=pm.response.json();
    const first=jsonData[0];
    pm.expect(first).to.have.property("userId");
     pm.expect(first).to.have.property("id");
     pm.expect(first).to.have.property("title");
     pm.expect(first).to.have.property("body");
   

})


post
https://jsonplaceholder.typicode.com//posts

pm.test("Status code is 201",()=>pm.response.to.have.status(201));

pm.test("Should have id ",()=>{
    let jsonData =pm.response.json();
    pm.expect(jsonData).to.have.property("id");
})

Body
  {
        "userId": 1,
        "id": 112,
        "title": "test",
        "body": "qtest_testuia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
    }



    newman

    D:\QA LEAD JASON\QA-Lead-Assessment-Sandun-jayasinghe>newman run jsonplaceholder_sandunj_qa.postman_collection.json
newman

jsonplaceholder_sandunj_qa

→ Get_jsonplaceholder
  GET https://jsonplaceholder.typicode.com//posts [200 OK, 28.65kB, 608ms]
  √  Status code is 200
  √  Response is an array
  √  Data verify

→ Post_jsonplaceholder
  POST https://jsonplaceholder.typicode.com//posts [201 Created, 1.45kB, 417ms]
  √  Status code is 201
  √  Should have id

→ Put_jsonplaceholder
  PUT https://jsonplaceholder.typicode.com//posts/1 [200 OK, 1.36kB, 436ms]
  √  Status code is 200

→ Delete_jsonplaceholder
  DELETE https://jsonplaceholder.typicode.com//posts/1 [200 OK, 1.11kB, 410ms]
  √  Status code is 200

┌─────────────────────────┬────────────────────┬────────────────────┐
│                         │           executed │             failed │
├─────────────────────────┼────────────────────┼────────────────────┤
│              iterations │                  1 │                  0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│                requests │                  4 │                  0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│            test-scripts │                  4 │                  0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│      prerequest-scripts │                  0 │                  0 │
├─────────────────────────┼────────────────────┼────────────────────┤
│              assertions │                  7 │                  0 │
├─────────────────────────┴────────────────────┴────────────────────┤
│ total run duration: 2.2s                                          │
├───────────────────────────────────────────────────────────────────┤
│ total data received: 27.99kB (approx)                             │
├───────────────────────────────────────────────────────────────────┤
│ average response time: 467ms [min: 410ms, max: 608ms, s.d.: 81ms] │
└───────────────────────────────────────────────────────────────────┘

D:\QA LEAD JASON\QA-Lead-Assessment-Sandun-jayasinghe>
