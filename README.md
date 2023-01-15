# onshapeLastModified

### Setup Pre-requisites:
1. Sign in to the [Developer Portal](https://dev-portal.onshape.com/signin)
2. Choose `OAuth applications` in the left frame or click [here](https://dev-portal.onshape.com/oauthApps)
3. Click on `Create new OAuth application` in the upper right corner
    1. Name: *Your Application Name*
    2. Primary format: *Inverse of your domain name* *e.g. org.angelbotics.onshape* 
    3. Summary: *Application description*
    4. Redirect URLs: *urn:ietf:wg:oauth:2.0:oob*
    5. Admin Team: *choose your team*
    6. OAuth URL: *leave blank*
    7. Permissions:
        1. *Application can read your profile information*
        2. *Application can read your documents*
    8. Click `Create application`
4. Create your own `.env` file to store your credentials
    ```
    ONSHAPE_CLIENT_SECRET='<your secret>'
    ONSHAPE_CLIENT_ID='<your client id>'
    ```
5. If you don't already have `pipenv` installed, instructions are available [here](https://pypi.org/project/pipenv/)
6. Run `pipenv install` to handle dependencies
7. Run `pipenv shell` to activate the virtual environment
8. Ensure you are still signed in to onshape and then run `./lastModified.py`
9. Your browser will open and prompt you to authorize the OAuth application. Click `Authorize application`
10. Run `./lastModified.py` again, copy the token from the /oauth/approval page, and paste it in the Python prompt.  **Note that python `pass` is being used so you wont see the pasted value
11. Press Enter.  Your bearer token is now in token.json and is good for an hour
12. You can re-run `./lastModified.py` or use `./obs.py` to automatically open the latest document in your default browser.
