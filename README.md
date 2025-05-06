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
