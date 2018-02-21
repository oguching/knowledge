### What is a WordPress Nonce?  
The word nonce means "number used once". Nonces are cryptographic hashes that are used to verify that a request was made by the right person or client. Because they are cryptographic hashes they should be impossible to fake.

WordPress nonces last for about 12 hours by default. This lifetime can however be changed using the `nonce_life` filter. Nonces can be used to prevent CSRF. Every request to a WordPress site should be protected with a nonce.  

### Using Nonces  
WordPress nonce functions:  
wp_create_nonce()  
wp_verify_nonce()  

wp_create_nonce( string|int $action = -1 )
creates a cryptographic token tied to a specific action, user, user session, and window of time.  

wp_verify_nonce( string $nonce, string|int $action = -1 )  
verify that correct nonce was used with time limit.  
The user is given an amount of time to use the token, so therefore, since the UID and $action remain the same, the independent variable is the time.  


Reference  
[What's a WordPress Nonce?](https://torquemag.io/2016/09/whats-wordpress-nonce-use/)  
[WordPress Nonces and Caching](https://joshpress.net/wordpress-nonces-and-wordpress-caching/)
