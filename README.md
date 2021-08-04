# Using `authcode` flow with Salesforce using PKCS #

1. Create Connected App in Salesforce with following parameters:
    1. Set `Callback URL` to `http://localhost:8080/index.html`
    2. Untick "Require Secret for Web Server Flow"
    3. Set scopes
        * Access your basic information (id, profile, email, address, phone)
        * Access and manage your data (api)
        * Perform requests on your behalf at any time (refresh_token, offline_access)
        * Allow access to your unique identifier (openid)
2. Search for `CORS` in Salesforce Setup and enable CORS for OAuth endpoints. Add the callback URL from above (http://localhost:8080/index.html) to the whitelist.
3. Update `index.html` and set correct values for the following Javascript constant:
    * `CLIENT_ID`
    * `MY_DOMAIN`
4. Run `npm install` and start local server with `npm run start`
5. Using `authcode` flow with Salesforce using PKCS should now work and on loading index.html and clicking the link on the page.