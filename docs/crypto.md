## Crypto

### import 
```
import { Crypto } from 'ye-js';
```

### MD5
```
Crypto.MD5('叶家伟') // e5f0979d37937e39b48093cb3b3b1a4a
```

### Html

+ Encoding HTML string
    ```
    Crypto.Html.escapeHTML('<div>abc</div>') // &lt;div&gt;abc&lt;/div&gt;
    ```

+ Decode HTML string
    ```
    Crypto.Html.unescapeHTML('&lt;div&gt;abc&lt;/div&gt;') // <div>abc</div>
    ```

### Base64

+ Converts the ArrayBuffer into a base64 string
    ```
    Crypto.Base64.bufferToBase64(new Uint8Array([97, 98, 99])) // YWJj
    ```

+ Converts the base64 string into ArrayBuffer
    ```
    Crypto.Base64.base64ToBuffer('YWJj') // Uint16Array(3) [97, 98, 99]
    ```

+ base64ToFile
    ```
    Crypto.Base64.base64ToFile(base64Str, fileType);
    ```

+ fileTobase64
    ```
    Crypto.Base64.fileTobase64(file);
    ```
    
+ base64ToBlob
    ```
    Crypto.Base64.base64ToBlob(base64Str);
    ```

+ blobTobase64
    ```
    Crypto.Base64.blobTobase64(blob);
    ```

+ base64ToUrl
    ```
    const url = Crypto.Base64.base64ToUrl(base64Str);
    image.src = url.value;
    url.revoke(); // remember to release
    ```

+ download
    ```
    Crypto.Base64.download(base64, 'test.jpeg');
    ```

+ compress
    ```
    compress image

    Crypto.Base64.compress(base64, 0.5).then(res => {
        console.log(res); // compress base64
    })
    ```

### Classical

> Classical cryptography

+ Shift
    ```
    Shift password algorithm, incoming code to move, can not exceed 65535

    const enc = Crypto.Classical.Shift.encode('I am 一个机智的 ヤード農', 30); // >>丞么杘暘皢>㄂ㄚョ运
    const dec = Crypto.Classical.Shift.decode(enc, 30);
    console.log('%s \r\n %s', dec, enc);
    ```

