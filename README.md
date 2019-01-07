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

### 3/1 Set an authentication state observer and get user data (for client authentication)

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

### 3/2. Set a redicet to callback adress in setting project (for server authentication)

If you are using server authorization, in the project settings add the callback address and set the flag to redirect to the callback address. 
After successful authorization, the user will be redirected to callback address from project settings
```bash
https://site.com/login/?auth_uid={user id}
```

#### Sample server handler (login.php)

```bash
<?php
    if(isset($_GET('auth_uid'))) {
        //active session
        session_start();
        
        $uid = $_GET('auth_uid');
        $url = 'https://authui.com/api/getUserFromId/'.$uid;
        
        //get user info to uid
        $result = file_get_contents($url);
        $user_data = json_decode($result)->data;
        
        //create session
        $_SESSION['user'] = $user_data;
        
        //reditet to user page
        header("Location:../");
    }
?>
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
