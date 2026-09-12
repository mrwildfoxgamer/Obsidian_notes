### Authentication
It verifies the identity of a user.
- username/password
- multi-factor authentication

The purpose is to establish the user's identity.

### Authorization

After identifying the user, the application determines what resources or operations that user can access.

# SQL Injection
**SQL Injection** occurs when malicious input manipulates a database query.
Frameworks can reduce this risk through **ORMs (Object Relational Mappers)**.
An ORM provides an abstraction between application code and SQL queries and can parameterize database operations rather than directly constructing unsafe SQL strings.

# Cross-Site Scripting — XSS

**XSS** is an attack where malicious JavaScript or HTML is injected into content displayed to users.
Jinja2's **automatic HTML escaping** helps prevent this by treating dangerous HTML characters as data.

# CSRF

**CSRF = Cross-Site Request Forgery**
The basic problem is that an attacker attempts to cause a user's browser to perform an unwanted state-changing action on a website where the user is already authenticated.
CSRF protection uses **tokens** to verify that a request originated from a legitimate application context

# Session Management

A **session** allows an application to maintain information associated with a user across multiple requests.

This matters because HTTP itself is fundamentally stateless.

Security mechanisms can protect session cookies using attributes such as:
- **Secure**
- **HTTPOnly**

# Password Hashing

Passwords should **not be stored as plain text**.
Instead, applications use password hashing.
# Input Validation

**Input validation** means checking user-provided data before processing it.

It helps prevent:

- invalid data
- unexpected values
- malicious input
# HTTPS

HTTP sends application traffic over a network.

**HTTPS** adds TLS encryption to protect communication between the client and server.

It is particularly important for protecting sensitive information during transmission.