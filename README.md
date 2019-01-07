# authui.com

Simple, free platform sign in

## Installation

include authui.js

```bash
<script src="https://authui.com/cloud/1.0/authui.js"></script>
```
Set an authentication state observer and get user data
For each of your app's pages that need information about the signed-in user, attach an observer to the global authentication object. This observer gets called whenever the user's sign-in state changes.

Attach the observer using the onAuthStateChanged method. When a user successfully signs in, you can get information about the user in the observer.

```bash
authui.onAuthStateChanged(function (user) {
                if (user) {
                    app.login = false;
                    app.user = user;
                    app.get_project(user.uid);
                } else {
                    app.login = true;
                }
});
```

## Usage

```python
import foobar

foobar.pluralize('word') # returns 'words'
foobar.pluralize('goose') # returns 'geese'
foobar.singularize('phenomena') # returns 'phenomenon'
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
