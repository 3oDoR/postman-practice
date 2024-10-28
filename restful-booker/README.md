# Postman practice

For my practice in postman, I found the [restful-booker API](https://restful-booker.herokuapp.com/apidoc/index.html).

The documentation says that to get access to put and delete, you need to get a token. So first I'm going to try to execute **get** to make sure I can get the allowed information and then I'm going to try to use **put** and **delete** to make sure  I don't have access.

#### GET without token

1. The first get request is https://restful-booker.herokuapp.com/booking and I get all the bookingid.
![IMG 1](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/1.png?token=GHSAT0AAAAAACYQERGXUBFW2NGTGP2LLGTUZY74J6Q)
2. After that, I select any id from the list. And I'm sending another get - https://restful-booker.herokuapp.com/booking/203 . I have received information about this booking.
![IMG 2](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/2.png?token=GHSAT0AAAAAACYQERGXTD5VEVQJHH2IH4USZY74KRQ)
3. Now I will create a new booking using the post method and add path: https://restful-booker.herokuapp.com/booking
![IMG 3](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/3.png?token=GHSAT0AAAAAACYQERGWRX3DRTXUEQUUBUDCZY74LDQ)
4. Now let's try to update our booking using the received id and try to change the totalprice to 155. We will expect failure because the documentation says that put and delete requests are prohibited without authorization.
![IMG 4](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/4.png?token=GHSAT0AAAAAACYQERGXKGJVYXKVMUTV5SUMZY74LVQ)
5. Now let's try the Partial Update Booking method. Although it is not written in the documentation that there should be a refusal without authorization, but the method does the same as the last one only partially.Use method  PATCH and path https://restful-booker.herokuapp.com/booking/:4730. Put it in the body:
![IMG 5](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/5.png?token=GHSAT0AAAAAACYQERGWXLQNJIJIOKBHDFTOZY74MBQ)
6. Now let's try to delete our booking without a token. We use the DELETE method and the path https://restful-booker.herokuapp.com/booking/:4730.
![IMG 6](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/6.png?token=GHSAT0AAAAAACYQERGW2EZL6BYBKU4BVYRSZY74MQA)
7. Let's try to get a token using the createToken method. Put json with its own values in the body.
![IMG 7](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/7.png?token=GHSAT0AAAAAACYQERGWZW2ZRMW4SHCVHJ2SZY74NDQ)
Now send the default data to receive the token.
![IMG 8](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/8.png?token=GHSAT0AAAAAACYQERGXKS7GHRW4HG7YKG7WZY74NTA)
8. Now let's try to update the booking using the UpdateBooking method and use token and all necessary headers.
The server replied "Forbitten".
![IMG 9](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/9.png?token=GHSAT0AAAAAACYQERGWDSVSGPJ6GZJPB34KZY74OMA)

![IMG 10](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/10.png?token=GHSAT0AAAAAACYQERGW32TGYMF6FCTKUIW6ZY74PAQ)

![IMG 11](https://raw.githubusercontent.com/3oDoR/postman-practice/refs/heads/main/restful-booker/Screens/11.png?token=GHSAT0AAAAAACYQERGXQUGAEI6UT5U65UWQZY74PMQ)

Just in case, I checked and repeated the request with all the data given in the sample documentation, but the result was unsuccessful again. I also tried with the created postan packages and failed again.

 I couldn't figure out the reason for a long time and found on the Internet that other people have exactly the same problems with requests for update and deletion methods. 


