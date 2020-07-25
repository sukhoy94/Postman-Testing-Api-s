# Testing APi's in POSTMAN
Useful snippets for writing tests in postman / docs

### Check status code

```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

```


### Match strings

```
pm.test("Body matches string accessToken", function () {
    pm.expect(pm.response.text()).to.include("accessToken");
});


pm.test("Body matches string accessToken", function () {
    pm.expect(pm.response.text()).to.include("refreshToken");
});
```

### Check if property exists in response body

```
pm.test("Login response structure", function () {
    var jsonResponse = pm.response.json();
    pm.expect(jsonResponse).to.have.property('data');
    pm.expect(jsonResponse.data).to.have.property('accessToken');
    pm.expect(jsonResponse.data).to.have.property('refreshToken');
});
```
