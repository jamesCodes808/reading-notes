# Local Storage and How To Use It On Websites

- Why would a developer use local storage for a web application?

A developer would use local storage for a web application because in essence, it is like holding and keeping the key to a user's computer computer when they access your web application, and when they open it, you unlock it for them. 

You hold the state of the application for when they last visited on your local storage and can restore it when they visit again. Also, it is faster once the data is cached to local storage rather then pulling the data from a server side client everytime. 

- What information should not be stored in local storage?

Personally Identifiable Information, authentication tokens, user locations and API keys should never be stored in local storage.

- Local storage can store what type of data? How would you convert it to that type before storing?

Local storage can only store strings in different keys. To convert the strings back to objects you can use `JSON.stringify()` and `JSON.parse()` methods.

>References
>
>[Local Storage And How To Use It On Websites](https://www.smashingmagazine.com/2010/10/local-storage-and-how-to-use-it/)
>
>

## Things I want to know more about
- How to use jQuery and more JSON methods. 

- Setting up local storage on my applications