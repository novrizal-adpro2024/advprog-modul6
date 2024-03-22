# Module 6: Concurrency

> #### Novrizal Airsyahputra - 2206081780 - Advance Programming B

---

### Reflection

---

**1. What is inside the handle_connection method?**

The handle_connection function is responsible for processing the TCP stream received from a client.
This function reads lines from the TCP stream until it reaches an empty line, indicating the end of the HTTP request headers. 
It then prints out the HTTP request headers for further processing.

**a. Argument**

The handle_connection function takes a mutable reference to a TcpStream as its argument. 
This stream represents the connection to a client.

**b. Buffered Reader**

Inside the function, a BufReader is created wrapping the TcpStream. 
This is used to efficiently read from the stream line by line.

**c. HTTP Request Parsing**

The lines() method is called on the BufReader, which returns an iterator over the lines of the incoming stream.
Each line is then unwrapped from the Result using the map method.
The take_while method is used to collect lines until an empty line is encountered, 
indicating the end of the HTTP request headers.
The collected lines are stored in a vector named http_request.

**d. Printing the Request**

The contents of the http_request vector are printed using println!(), allowing to see the HTTP request headers.

