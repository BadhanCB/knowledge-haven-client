># [Knowledge Haven](https://knowledge-haven.web.app/)
# A Full-Stack React _Single Page Application_ with `React-Router`, `Firebase Authentication`, `Firebase Hosting` & `Restfull NodeJS API`. React UI Library `React-Bootstarp`, `Material-UI`. 

### IN this Application Fetch http CRUD method.

### To read all book from mongoDB at Home.js
```
fetch('https://knowledge-haven-server.onrender.com/allBooks')
.then(res => res.json())
.then(data => setAllBooks(data));
```
### To Create a book Product at mongoDB at ADDBook.js
```
fetch('https://knowledge-haven-server.onrender.com/addBook', {
    method: 'POST',
    headers: {
    'Content-Type': 'application/json'
    },
    body: JSON.stringify(newBookInfo),
})
.then(res => res.json())
.then(result => {
     setIsSendingData(false);
    if (result) {
    alert("Book Information Added Successfully");
}
});
```
### To Update a book Details to mongoDB at EditBook.js
```
fetch(`https://knowledge-haven-server.onrender.com/updateBook/${bookForEdit._id}`,{
    method: 'PATCH',
    headers: {'Content-Type': 'application/json'},
    body: JSON.stringify(newBookInfo),
}).then(res => res.json())
.then(result => {
    setIsSendingData(false);
    if(result){
        alert('Book Info Updated Successfully.');
    } else{
        alert('Failed to Updated Book Info!');
    }
}).catch(() =>{
    setIsSendingData(false);
    alert('Failed to Updated Book Info!');
})
```
### To Delete a book Product at mongoDB at ManageBooks.js
```
fetch(`https://knowledge-haven-server.onrender.com/deleteBook/${id}`, {
    method: "DELETE"
})
.then(res => res.json())
.then(result => {
    setIsFetchData(false);
    if (result) {
        fetchAddedBooksData(email);
        alert('Book Deleted Successfully!');
    }
})
```
### To fetch specific data
#### at Orders.js
```
fetch(`https://knowledge-haven-server.onrender.com/submitedOrders/${email}`)
    .then(res => res.json())
    .then(data => {
        setAllOrders(data);
        setIsFetchData(false);
});
```
#### at ManageBooks.js
```
fetch(`https://knowledge-haven-server.onrender.com/addedBooks/${userEmail}`)
.then(res => res.json())
.then(data => {
    setIsFetchData(false);
    setAddedBooks(data);
});
```
