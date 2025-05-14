
![image](https://github.com/user-attachments/assets/436ea6e7-e0a7-4916-8f52-0d6763817b4f)

### What is API?

An API is a set of rules that allow different software applications to communicate with each other. 
Think of it like a bridge that connects two systems and lets them share data or services.

To make this clearer, let’s use an example:


Imagine you’re at a restaurant. The waiter (API) takes your order (request), brings it to the chef (server), and then brings the food back to you (response).

Similarly, when you search for a course on a website, you send a request through an API, which then checks the database and sends the result back to you.

Documentation:
https://www.geeksforgeeks.org/what-is-an-api/



![image](https://github.com/user-attachments/assets/fcac4453-8db6-4559-8998-9fb3c09dbee2)



**Traditional:**

* **Tightly Coupled:** Interdependent components.
* **Low Reusability:** Hard to reuse functionality.
* **Technology Limits:** Difficult to integrate different systems.
* **Monolithic:** Single, large applications.
* **Slow Development:** Building from scratch often required.
* **Complex Maintenance:** Changes risky and debugging hard.
* **Fragile:** Failures could cascade.

**APIs:**

* **Loosely Coupled:** Independent components.
* **High Reusability:** Easy to reuse functionality.
* **Technology Agnostic:** Enables integration across different systems.
* **Modular (Microservices):** Smaller, independent services.
* **Fast Development:** Leverage existing functionalities.
* **Easy Maintenance:** Independent updates and debugging.
* **Resilient:** Failures are often isolated.
* **Secure Access:** Controlled access to data and functions.
* **Abstracted:** Hides complexity.
* **Enables Sharing:** Facilitates data and function sharing.
* **Platform Independent:** Works across various environments.
  
### 
**Monolithic:** One big application, everything together. Updating or scaling one part means dealing with the whole thing. If one part breaks, it can all break.

**Microservices:** Many small, independent applications working together. Update or scale parts individually. If one breaks, the rest can often keep going. They talk to each other using APIs.


### Json:
https://jsonformatter.org/

### freeAPI

https://api.freeapi.app/#/%F0%9F%93%A2%20Public%20APIs/getARandomJoke


```python
import requests

def fetch_random_user_freeapi():
    url = "https://api.freeapi.app/api/v1/public/randomusers/user/random"
    response = requests.get(url)
    data = response.json()

    if data["success"] and "data" in data:
        user_data = data["data"]
        username = user_data["login"]["username"]
        country = user_data["location"]["country"]
        return username, country
    else:
        raise Exception("Failed to fetch user data")

def main():
    try:
        username, country = fetch_random_user_freeapi()
        print(f"Username: {username}")
        print(f"Country: {country}")
    except Exception as e:
        print(f"An error occurred: {e}")

if __name__ == '__main__':
    main()
```


### What is an HTTP Status Code?

https://careercenter.bauer.uh.edu/blog/2022/05/18/http-status-codes-why-are-they-important-for-search-engines/#:~:text=This%20makes%20it%20easy%20to%20identify%20and%20correct%20common%20website%20errors.


![image](https://github.com/user-attachments/assets/ea60aa79-6686-48b0-86aa-8279ef32541e)
