---
title: 'Verify webhooks from Terapi'
sidebarTitle: 'Verify webhooks from Terapi'
description: 'Step-by-step guide on how to verify the signatures of webhooks from Terapi.'
---

Validate webhook provenance by looking at the `X-Terapi-Signature` header. 

It's a SHA-256 hash generated using the secret key found in the _Environment Settings_ in the Terapi UI. 

The webhook signature can be generated with the following code:





```typescript
import crypto from 'crypto';

const secretKeyDev = 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx';
const signature = `$$`;
const hash = crypto.createHash('sha256').update(signature).digest('hex');
```





```python
import hashlib
import json

secret_key_dev = 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx'
signature = f""
hash = hashlib.sha256(signature.encode('utf-8')).hexdigest()
```





```java
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;
import javax.xml.bind.DatatypeConverter;

public class Main 
}
```





```ruby
require 'json'
require 'digest'

secret_key_dev = 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx'
signature = "##"
hash = Digest::SHA256.hexdigest(signature)
```





```go
package main

import (
    "crypto/sha256"
    "encoding/hex"
    "encoding/json"
)

func main() 
```





```rust
use sha2::;
use serde_json::json; // Assuming use of serde_json for JSON serialization

let secret_key_dev = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx";
let signature = format!("", secret_key_dev, serde_json::to_string(&payload).unwrap());
let mut hasher = Sha256::new();
hasher.update(signature.as_bytes());
let hash = format!("", hasher.finalize());
```





```php
<?php
$secretKeyDev = 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx';
$signature = $secretKeyDev . json_encode($payload);
$hash = hash('sha256', $signature);
?>
```





Only accept a webhook if the `X-Terapi-Signature` header value matches the webhook signature.

