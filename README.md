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
