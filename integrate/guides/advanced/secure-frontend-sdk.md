---
title: 'Secure the frontend SDK'
sidebarTitle: 'Secure the frontend SDK'
description: 'Step-by-step guide on how to secure the frontend SDK.'
---

Before moving to production, you must ensure nobody else can create a new connection.

Add a secret HMAC key (large, random value) in your _Environment Settings_ tab in the Terapi UI.

Generate the HMAC signature in your backend and pass it to your frontend before you make `terapi.auth` calls.

The HMAC signature can be generated with the following code:





```js
import * as crypto from 'node:crypto';

// Enforce backend authentication before generating the HMAC digest.
const hmac = crypto.createHmac('sha256', ''); // HMAC key set in your environment settings.
hmac.update(':');
const digest = hmac.digest('hex');
```





```python
import hmac
import hashlib

# HMAC key set in your environment settings.
hmac_key = ''
message = ':'

digest = hmac.new(hmac_key.encode('utf-8'), msg=message.encode('utf-8'), digestmod=hashlib.sha256).hexdigest()
```





```java
import javax.crypto.Mac;
import javax.crypto.spec.SecretKeySpec;
import java.security.InvalidKeyException;
import java.security.NoSuchAlgorithmException;

public class Main 
        String digest = hexString.toString();
    }
}
```





```ruby
require 'openssl'

hmac_key = ''
message = ':'

digest = OpenSSL::HMAC.hexdigest('SHA256', hmac_key, message)
```





```go
package main

import (
    "crypto/hmac"
    "crypto/sha256"
    "encoding/hex"
)

func main() 
```





```rust
use hmac::;
use sha2::Sha256;

type HmacSha256 = Hmac;

let hmac_key = "";
let message = ":";

let mut mac = HmacSha256::new_varkey(hmac_key.as_bytes()).expect("HMAC can take key of any size");
mac.update(message.as_bytes());
let result = mac.finalize();
let digest = hex::encode(result.into_bytes());
```





```php
<?php
$hmacKey = '';
$message = ':';

$digest = hash_hmac('sha256', $message, $hmacKey);
?>
```






Your backend should keep the secret HMAC key private and not reveal it to your frontend or end users.


In the frontend, pass the HMAC signature in `terapi.auth()`:

```ts
terapi.auth('', '', );
```

Enable the HMAC checkbox in the _Environment Settings_ tab in the Terapi UI. 


Terapi will reject auth calls without a proper HMAC signature, so make sure your code is ready before you flip the switch! 



**Questions, problems, feedback?** Please reach out in the Slack community.


