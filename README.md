# authui.com

Simple, free platform sign in

## Installation

### 1. Create a project in the Authui console
### 2. Include project to your app

```bash
<script src="https://authui.com/cloud/1.0/authui.js"></script>
<script>authui.initializeApp(publicKay);</script>
```
publicKay is a public kay in setting your project

### 3. Set an authentication state observer and get user data (for client authentication)

For each of your app's pages that need information about the signed-in user, attach an observer to the global authentication object. This observer gets called whenever the user's sign-in state changes.

```bash
authui.onAuthStateChanged(function (user) {
      if (user) {
        //view user page
      } else {
        //view login page
      }
});
```
Attach the observer using the onAuthStateChanged method. When a user successfully signs in, you can get information about the user in the observer.

### 3/1. Set a redicet to callback adress in setting project (for server authentication)

If 

## License
[MIT](https://choosealicense.com/licenses/mit/)
