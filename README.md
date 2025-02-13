# CyberJS
A Cybersecurity scripts that allows anyone to _check-attack-fix (CAF)_ on the site to make sure nobody can hack and steal information that you might not want to steal.

**Do not misuse this software for illegal activity, this is for production testing purposes or educational use!**

## Table of Contents
* [Initiate](#Initiate)
* [Cryptographies](#Cryptographies)
   * [Ciphers](#ciphers)
     * [Caesar Cipher](#Caesar-Cipher)
       * [Encrypt](#caesar-cipher-encrypt)
       * [Decrypt](#caesar-cipher-decrypt)
       * [Configuration](#caesar-cipher-configuration)
     * [Vigenère Cipher](#Vigenère-Cipher)
       * [Encrypt](#Vigenère-Cipher-encrypt)
       * [Decrypt](#Vigenère-Cipher-decrypt)
       * [Configuration](#Vigenère-Cipher-configuration)
     * [One-Time Pad](#one-time-pad)
       * [Encrypt](#one-time-pad-encrypt)
       * [Decrypt](#one-time-pad-decrypt)
       * [Configuration](#one-time-pad-decrypt)
   * [Encoding](#encoding)
     * [Base64](#base64)
       * [Encode](#base64-encode)
       * [Decode](#base64-decode)
     * [Base32](#base32)
       * [Encode](#base32-encode)
       * [Decode](#base32-decode)
   * [Hashing](#hashing)
     * [MD2](#md2)
     * [MD4](#md4)
     * [MD5](#md5)
     * [SHA-1](#sha-1)
     * [SHA-224](#sha-224)
     * [SHA-256](#sha-256)
     * [SHA-384](#sha-384)
     * [Hash](#hash)
* [Hacking](#hacking)
  * [Google Hacking](#google-hacking)
  * [Pinging](#ping)
  * [Web Scraping](#web-scraping)
  * [XSS](#xss)
    * [Persistent](#xss-persistent)
    * [DOM](#xss-dom)
    * [Reflected](#xss-reflected)
    * [Sanitize](#xss-sanitize)
  * [SQL Injection](#sql-injection) 
* [Detections](#detections)
  * [Device](#device)
  * [Browser](#browser)
* [Flags](#flags)
***
## Initiate
To load up the script:
```html
<script type="module">
 import {Cryptography, Hacking, Detections} from './cyber.min.js';
 //Script goes here
</script>
```
**OR**
You can use the CDN
```html
<script type="module">
import {Cryptography, Hacking, Detections} from "https://cdn.jsdelivr.net/gh/XHiddenProjects/CyberWeb@1.0.9/cyber.min.js"
 //Script goes here
</script>
```

***
## Cryptographies
Here is the current list of cryptographies

**KEY**
- **Name**: Name of the cryptography
- **Encryptable/Encodable**: If the cryptography can be encrypted/encoded
- **Decryptable/Decodable**: If the cryptography can be decrypted/decoded
- **Forcable**: If the cryptography can be _brute-forced_
- **Description**: A small description of what cryptography can do.

| Name | Encryptable/Encodable | Decryptable/Decodable | Forcable | Description |
| ---- | --------------------- | --------------------- | -------- | ----------- |
| CaesarCipher  | ✔️  | ✔️   |    ✔️      | Encodes/Decodes string in Caesar Cipher |
| VigenereCipher| ✔️ | ✔️ | ❌  |          Encodes/Decodes string in Vigenere Cipher |
| OneTimePad | ✔️ | ✔️ | ❌  | Encryps/Decrypts string using One-Time pad |
| Base64 | ✔️ | ✔️ | ❌  | Encodes/Decodes string in base64 |
| Base32 | ✔️ | ✔️ | ❌ | Encodes/Decodes string in base32 |
| MD2 | ✔️ | ❌  | ❌ | Hashes the string in MD2 |
| MD4 | ✔️ | ❌  | ❌ | Hashes the string in MD4 |
| MD5 | ✔️ | ❌  | ❌ | Hashes the string in MD5 |
| SHA-1 | ✔️ | ❌  | ❌ | Hashes the string in SHA-1 |
| SHA-224 | ✔️ | ❌  | ❌ | Hashes the string in SHA-224 |
| SHA-256 | ✔️ | ❌  | ❌ | Hashes the string in SHA-256 |
| SHA-384 | ✔️ | ❌  | ❌ | Hashes the string in SHA-384 |

***
## Ciphers
List of ciphers

### Caesar Cipher
Caesar Cipher is a common cipher that shifts letters based on key value

#### Caesar Cipher (Encrypt)
To encode the Caesar Cipher write this code:
```js
Cryptography.CaesarCipher.encrypt('Test',7); //Returns ALZA
```

#### Caesar Cipher (Decrypt)
To decode the Caesar Cipher write this code:
```js
console.log(Cryptography.CaesarCipher.decrypt('ALZA',7)); //TEST
```

**OR**

Leave the key out to _brute force_ through
```js
console.log(Cryptography.CaesarCipher.decrypt('QYYQVO'));
/*
{
    "1": "PXXPUN",
    "2": "OWWOTM",
    "3": "NVVNSL",
    "4": "MUUMRK",
    "5": "LTTLQJ",
    "6": "KSSKPI",
    "7": "JRRJOH",
    "8": "IQQING",
    "9": "HPPHMF",
    "10": "GOOGLE", // Correct brute force
    "11": "FNNFKD",
    "12": "EMMEJC",
    "13": "DLLDIB",
    "14": "CKKCHA",
    "15": "BJJBGZ",
    "16": "AIIAFY",
    "17": "ZHHZEX",
    "18": "YGGYDW",
    "19": "XFFXCV",
    "20": "WEEWBU",
    "21": "VDDVAT",
    "22": "UCCUZS",
    "23": "TBBTYR",
    "24": "SAASXQ",
    "25": "RZZRWP",
    "26": "QYYQVO",
    "27": "PXXPUN",
    "28": "OWWOTM",
    "29": "NVVNSL",
    "30": "MUUMRK",
    "31": "LTTLQJ",
    "32": "KSSKPI",
    "33": "JRRJOH",
    "34": "IQQING",
    "35": "HPPHMF",
    "36": "GOOGLE",
    "37": "FNNFKD",
    "38": "EMMEJC",
    "39": "DLLDIB",
    "40": "CKKCHA"
}
*/
```

#### Caesar Cipher (Configuration)
To configure what can be loaded in use this code:
```js
console.log(Cryptography.CaesarCipher.settings({chars: `${Cryptography.options.UPPERCASE_LETTERS}${Cryptography.options.LOWERCASE_LETTERS}`}).encrypt('Test',7)); //alzA
console.log(Cryptography.CaesarCipher.settings({chars: `${Cryptography.options.UPPERCASE_LETTERS}${Cryptography.options.LOWERCASE_LETTERS}`}).decrypt('alzA',7)); //Test
console.log(Cryptography.CaesarCipher.settings({chars: `${Cryptography.options.UPPERCASE_LETTERS}${Cryptography.options.LOWERCASE_LETTERS}`}).decrypt('alzA'));
/*
{
    "1": "Zkyz",
    "2": "Yjxy",
    "3": "Xiwx",
    "4": "Whvw",
    "5": "Vguv",
    "6": "Uftu",
    "7": "Test", //Correct Brute force
    "8": "Sdrs",
    "9": "Rcqr",
    "10": "Qbpq",
    "11": "Paop",
    "12": "OZno",
    "13": "NYmn",
    "14": "MXlm",
    "15": "LWkl",
    "16": "KVjk",
    "17": "JUij",
    "18": "IThi",
    "19": "HSgh",
    "20": "GRfg",
    "21": "FQef",
    "22": "EPde",
    "23": "DOcd",
    "24": "CNbc",
    "25": "BMab",
    "26": "ALZa",
    "27": "zKYZ",
    "28": "yJXY",
    "29": "xIWX",
    "30": "wHVW",
    "31": "vGUV",
    "32": "uFTU",
    "33": "tEST",
    "34": "sDRS",
    "35": "rCQR",
    "36": "qBPQ",
    "37": "pAOP",
    "38": "ozNO",
    "39": "nyMN",
    "40": "mxLM",
    "41": "lwKL",
    "42": "kvJK",
    "43": "juIJ",
    "44": "itHI",
    "45": "hsGH",
    "46": "grFG",
    "47": "fqEF",
    "48": "epDE",
    "49": "doCD",
    "50": "cnBC",
    "51": "bmAB",
    "52": "alzA"
}
*/
```

### Vigenère Cipher
Vigenère Cipher, just like Caesar Cipher, uses string length as a key.

#### Vigenère Cipher (Encrypt)
To encode the Vigenère Cipher write this code:
```js
console.log(Cryptography.VigenereCipher.encrypt('Hello World','KickMeNowP')); //RMNVAABFHS
```

#### Vigenère Cipher (Decrypt)
To decode the Vigenère Cipher write this code:
```js
console.log(Cryptography.VigenereCipher.decrypt('RMNVAABFHS', 'KickMeNowP')); //HelloWorld
```

#### Vigenère Cipher (Configuration)
**Refer back to [Ceasar Cipher (Configuration)](#caesar-cipher-configuration)**
One thing added is:

**repeatMode** - Automatically fixes the key to be added/removed characters based on string length.

```js
console.log(Cryptography.VigenereCipher.settings({repeatMode:Cryptography.flags.KEY_MODE_REPEAT}).encrypt('AttackAtDawn', 'LEMON')); //LXFOPVEFRNHR
console.log(Cryptography.VigenereCipher.settings({repeatMode:Cryptography.flags.KEY_MODE_REPEAT}).decrypt('LXFOPVEFRNHR', 'LEMON')); //ATTACKATDAWN
```

### One-Time Pad
Encryption technique utilizing a one-time pre-shared key at least as long as the encrypted message

#### One-Time Pad (Encrypt)
To encode the Vigenère Cipher write this code:
```js
console.log(Cryptography.OneTimePad.settings({repeatMode:true}).encrypt('TEST', 'Lemon')); //EIEH
```

#### One-time Pad (Decrypt)
To decode the Vigenère Cipher write this code:
```js
console.log(Cryptography.OneTimePad.settings({repeatMode:true}).decrypt('EIEH', 'Lemon')); //TEST
```

#### One-time Pad (Configuration)
**Refer back to [Vigenère Cipher (Configuration)](#vigenère-cipher-configuration)**

***

## Encoding
This is a list of encodings/decodings you can have.

### Base64
Base64 is an encoded text by a group of binary-to-text using 64 symbols

#### Base64 (Encode)
Encode string using base64
```js
console.log(Cryptography.Base64.encode('Test')); //VGVzdA==
```

#### Base64 (Decode)
Decode Base64 string
```js
console.log(Cryptography.Base64.decode('VGVzdA=='));
```

### Base32
Base32 is an encoded text by a group of binary-to-text using 64 symbols

#### Base32 (Encode)
Encode string using base32
```js
console.log(Cryptography.Base32.encode('Test')); //KRSXG5A=
```

#### Base32 (Decode)
Decode Base32 string
```js
console.log(Cryptography.Base32.decode('KRSXG5A=')); //Test
```

***

## Hashing
This is a list of hash algorithms.

### MD2
To hash MD2
```js
console.log(Cryptography.hash.md2('A')); //08e2a3810d8426443ecacaf47aeedd17
```

### MD4
To hash MD4
```js
console.log(Cryptography.hash.md4('A')); //d5ef20eeb3f75679f86cf57f93ed0ffe
```

### MD5
To hash MD2
```js
console.log(Cryptography.hash.md5('A')); //7fc56270e7a70fa81a5935b72eacbe29
```

### SHA-1
To hash SHA-1
```js
console.log(Cryptography.hash.sha1('Cybersecurity')); //7b7a8d8e9435d1064967f8ba2a43eee1f7804f5e
```

### SHA-224
To hash SHA-224
```js
console.log(Cryptography.hash.sha224('Hello World!')); //4575bb4ec129df6380cedde6d71217fe0536f8ffc4e18bca530a7a1b
```

### SHA-256
To hash SHA-256
```js
console.log(Cryptography.hash.sha256('Test')); //532eaabd9574880dbf76b9b8cc00832c20a6ec113d682299550d7a6e0f345e25
```

### SHA-384
To hash SHA-384
```js
console.log(Cryptography.hash.sha384('Google')); //2af172307e1317b9c04187cc7f664e5ea7907df8523c409bc2f226ab05f3ca031a966d86db52bc3a3600bd97bd8f2e50
```


### Hash
```js
const algo = 'md2', str='String';
console.log(Cryptography.hash.hash(algo,str));
```

***
## Hacking
These are some hacking tools that can be used

### Google Hacking
Google hacking, aka. Google Dorking, is an information-gathering technique used by an attacker leveraging advanced Google searching techniques.
How to use:
1. As an string
```js
/**
 * Opens a google hacking URL
 * @param {String|{site: string|null, filetype: string|null, link: string|null, cache: string|null, intitle: string|null, inurl: string|null}} query Query search to hack
 * @returns {void} Opens url in new tab
 */
Hacking.google(`${Hacking.flags.IN_TITLE('"Index Of"')} ${Hacking.flags.FILE_TYPE('sql')}`);
```
2. As an object
```js
/**
 * Opens a google hacking URL
 * @param {String|{site: string|null, filetype: string|null, link: string|null, cache: string|null, intitle: string|null, inurl: string|null}} query Query search to hack
 * @returns {void} Opens url in new tab
 */
Hacking.google({
  intitle: '"index of"',
  filetype: 'sql'
});
```

## Ping
ping is a computer network administration software utility used to test the reachability of a host on an Internet Protocol (IP) network
```js
/**
 * Pings IP address
 * @param {String} ip IP/URL Address
 * @param {Function} callback Callback
 * @param {Number} [count=4] How many times to call
 */
Hacking.ping('ip',(e)=>{
  console.log(e);
},4);
```
## Web Scraping
Data scraping used for extracting data from websites
```js
/**
 * URL to scrape
 * @param {String} url URL to scrape
 * @param {Function} callback Callback 
 * @param {"html"|"xml"|"tree"} [format='html'] Format of the output
 * @returns {JSON}
 */
Hacking.scrape('url',(e)=>{
  console.log(e);
 },'tree');
```

## XSS
Cross-site scripting is a common hacking technique here is the same tests and security measures to prevent this

### XSS-Persistent
XSS-Persistent is using a Script code inside of inputs, this will render a script value for any input to test out
```js
/**
  * Renders a js code to all inputs to make sure that it cannot
  * @param {String} JS code to inject
  * @returns {void}
  */
Hacking.xss.persistent('alert("test")');
```

### XSS-DOM
Injects a script code into the URL to inject
```js
/**
  * Injects JavaScript code through URL
  * @param {String} JSCode code to inject
  * @returns {void}
  */
Hacking.xss.dom('alert("test");');
```

### XSS-Reflected
Injects a script code from backend XMLHttpRequest
```js
/**
  * Injects code through HTTP requests
  * @param {String} url URL to target
  * @param {String} key Key to return injection
  * @param {String} JSCode code to inject
  */
Hacking.xss.reflected(URL,key,JSCode);
```

### XSS-Sanitize
This code will automatically sanitize URLs and inputs so it doesn't hacked
```js
/**
  * Sanitizes string
  * @returns {String} Sanitized URL and inputs
  */
Hacking.xss.sanitize();
```

## SQL Injection
This code will insert a basic SQL injection code into the textarea or textbox.
```js
/**
 * Checks for SQL Injection
 * @param {String} [sql=`' OR 1=1;#`] SQL code 
 */
Hacking.sql(sql);
```

***
## Detections
These are some detections to see the users' browser and device information

### Device
Here are ways to detect users' device information
```js
/**
 * Checks for virtual machine
 * @returns {Boolean} True if VM, False if not
 */
Detections.device.isVM();
/**
 * Get OS
 * @returns {String} OS
 */
Detections.device.os();
/**
 * Returns the OS architecture
 * @returns {String} architecture
 */
Detections.device.arch();
/**
 * Returns the screen information
 * @returns {{height: number, width: number, depth: number, orientation: ScreenOrientation, extended: boolean}} Screen information
 */
Detections.device.screen();
```

### Browser
Here are ways you can get users' browser information
```js
/**
 * Get Full browser
 * @returns {String} Browser information
 */
Detections.browser.get();
/**
 * Get Browser name
 * @returns {String} Browser name
 */
Detections.browser.browser();
/**
 * Get Browser Version
 * @returns {String} Browsers version
 */
Detections.browser.version();
/**
 * Returns the browsers media
 * @returns {{display: string, hover: boolean, orientation: "landscape"|"portrait", pointer:"fine"|"coarse"|"none", colorScheme: "dark"|"light"|"none"}} Browsers media information
 */
Detections.browser.media();
/**
 * Returns the available Web APIs
 * @returns {String[]}
 */
Detections.browser.apis();
```

***

## Flags
These are some options that you can use for parameters. **Note:** This only works for `.settings(...)` methods for any acceptable cryptography.
| Constant | Value | Type | Path |
| -------- | ----- | ---- | ---- |
| UPPERCASE_LETTERS | 'ABCDEFGHIJKLMNOPQRSTUVWXYZ' | String | _Cryptography.flags.UPPERCASE_LETTERS_ |
| LOWERCASE_LETTERS | 'abcdefghijklmnopqrstuvwxyz' | String | _Cryptography.flags.LOWERCASE_LETTERS_ |
| NUMBERS | '0123456789' | String | _Cryptography.flags.NUMBERS_ |
| SPACE | ' ' | String | _Cryptography.flags.SPACE_ |
| SPECIAL_CHARS | '!@#$%^&*()_+-=[]{}\|;:\'",.<>?/~' | String | _Cryptography.flags.SPECIAL_CHARS_ |
| KEY_MODE_REPEAT | TRUE | Boolean | _Cryptography.flags.KEY_MODE_REPEAT_ |
| PARSE_URL | Function | URL | _Hacking.flags.PARSE_URL_ |
| SITE | Function | String | _Hacking.flags.SITE_ |
| FILE_TYPE | Function | String | _Hacking.flags.FILE_TYPE_ |
| LINK | Function | String | _Hacking.flags.LINK_ |
| CACHE | Function | String | _Hacking.flags.CACHE_ |
| IN_TITLE | Function | String | _Hacking.flags.IN_TITLE_ |
| IN_URL | Function | String | _Hacking.flags.IN_URL_ |

