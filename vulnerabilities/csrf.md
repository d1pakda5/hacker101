Lack of CSRF Tokens
===================

Related Session
---------------

[The Web In Depth](../sessions/web_in_depth.md)

<iframe id="ytplayer" type="text/html" width="640" height="360" src="https://www.youtube-nocookie.com/embed/DWBUQiaN5ZM?rel=0&autoplay=0&origin=https://hacker101.com" frameborder="0"></iframe>

Severity Range
--------------

- Low to Critical

Description
-----------

CSRF tokens are session-unique values sent along with stateful requests.  These prevent Cross-Site Request Forgery attacks, where an attacker can force a victim's browser to perform an action.

Security Impact
---------------

If an attacker is able to get a victim to go to a URL they control, they may be able to perform sensitive actions in the context of the victim.  Any action not requiring CSRF tokens would be able to be performed by the attacker.

Remediation
-----------

When generating sessions for users, generate a random string (a CSRF token) and associate it with this session.  For each stateful action the user can perform, send this CSRF token along with the other request data, then check that it matches on the server.  If the CSRF token isn't present or doesn't match the expected value, deny the request.

References
----------

- [https://www.owasp.org/index.php/Cross-Site%5FRequest%5FForgery%5F(CSRF)](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_%28CSRF%29)

