# Cookie's SameSite options can be confusing

`SameSite` attribute on a cookie provides three different ways to control the cookie's behaviour. You can choose to not specify the attribute, or you can use `Strict` or `Lax` to limit the cookie to same-site requests.

If you set `SameSite` to `Strict`, your cookie will only be sent in requests that originate "within" your website — aka a first-party context. This means that cookies with `Strict` would not be sent when following a link into your website for instance, which would be problematic for instance if you have a cookie that controls some behaviour on a landing page.

With `Lax` cookies are not sent on normal cross-site subrequests (for example to load images or frames into a third party site), but are sent when a user is navigating to the website (i.e., when following a link).

More info [here](https://web.dev/samesite-cookies-explained/).
