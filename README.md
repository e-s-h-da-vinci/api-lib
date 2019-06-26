### Da Vinci API
At the TU/e and Fontys we have a lot of technical knowledge. Also at Da Vinci, we have some apps that we have developed ourselves. To link these apps to our member administration system, this library has been developed.

##### Create a Client
You should import the `Client` class through Composer (`composer require e-s-h-da-vinci\api-lib`) into your application. You can then use the following code to get an example member list:

```
use ESHDaVinci\API\Client;
$client = new Client(
  "your-api-key",
  "your-api-secret"
);

var_dump($client->getListOfNames(true));
```

This will give you a list of all active members.
You should replace `your-api-key` and `your-api-secret` with the key and secret that you got from the Communicacie!


##### Available functions
###### getListOfNames($active = false)
Gets a list of the names of all members of Da Vinci. The key represents an ID and the value is the full name. You can optionally give a parameter $active, representing if you only want active members, or all members (true is only active).

###### authenticate(int $id, string $pass)
Checks a password against the stored password for user $id. Returns boolean.

###### getNameByID(int $id)
Gets name corresponding to given ID

###### getMemberList($active = false)
Gets a member list, similar to getListOfNames, but returns array of arrays with more info, such as the initials.
