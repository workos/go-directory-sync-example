# go-sso-example
An example Flask application demonstrating how to use the [WorkOS Python SDK](https://github.com/workos-inc/workos-python) to authenticate users via SSO.

## Prerequisites
- Go

## Flask Project Setup

1. In your CLI, navigate to the directory into which you want to clone this git repo.
   ```bash
   $ cd ~/Desktop/
   ```

2. Clone this git repo using your preferred secure method (HTTPS or SSH).
   ```bash
   # HTTPS
   $ git clone https://github.com/workos-inc/go-sso-example.git
   ```

   or

   ```bash
   # SSH
   $ git clone git@github.com:workos-inc/go-sso-example.git
   ```

3. Navigate to the cloned repo.
   ```bash
   $ cd go-sso-example
   ```

4. Obtain and make note of the following values. In the next step, these will be set as environment variables.
   - Your [WorkOS API key](https://dashboard.workos.com/api-keys)
   - Your [SSO-specific, WorkOS Project ID](https://dashboard.workos.com/configuration)


5. Edit the environmental variables in `main.go`.

6. The final setup step is to start the server.
   ```bash
   $ go run .
   ```

   You'll know the server is running when you see no errors in the CLI, and output similar to the following is displayed:

   ```bash
launching sso demo with configuration: {Addr::3042 APIKey: {your api key} ProjectID: {your project id} RedirectURI: {your redirect URI} Domain: {your domain} }
   ```

   Navigate to `localhost:3042` in your web browser. You should see a "Login" button. If you click this link, you'll be redirected to an HTTP `404` page because we haven't set up SSO yet!

   You can stop the local server for now by entering `CTRL + c` on the command line.


## SSO Setup with WorkOS

Follow the [SSO authentication flow instructions](https://workos.com/docs/sso/guide/introduction) to set up an SSO connection.

When you get to the step where you provide the `REDIRECT_URI` value, use http://localhost:3042/callback.

If you get stuck, please reach out to us at support@workos.com so we can help.

## Testing the Integration

1. Naviagte to the `go-sso-example` directory. 

   ```bash
   $ go run .
   ```

   Once running, navigate to http://localhost:3042 to test out the SSO workflow.

   Hooray!

## Need help?

If you get stuck and aren't able to resolve the issue by reading our API reference or tutorials, you can reach out to us at support@workos.com and we'll lend a hand.
