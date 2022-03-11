# friendly-lite-server - Self Hosted Captcha Server, compatible with Friendly Captcha

[**Friendly Captcha**](https://friendlycaptcha.com) offers a privacy aware captcha service. This repository provides a lite server version of the service with some basic features for puzzle and verification on your own machine. The Friendly Captcha service normally works by serving challenges with the difficulty based on the likelihood of being a real human user, as well as being highly available. This implementation is much simpler but will work for small hobby projects.

This distribution is licensed under a non-commercial source available license, which means you can run this server yourself for non-commercial or internal projects. 

If you need more advanced security features and reliability or want to support our work, we highly recommend to [**subscribe**](https://friendlycaptcha.com/signup) to the Friendly Captcha service.

## Requirements

* PHP 7.4 or higher
* sodium support
* apcu support

## Installation

You need a web server running PHP 7.4 or later.

1. Install the public folder to the your document root.
2. Copy and adapt env.template.php to env.php 
3. Change the friendly captcha widgets endpoint to user your server
4. In your backend configuration, use the your own server endpoint and

## Endpoints

Instead of `https://api.friendlycaptcha.com/api/v1/siteverify` use `https://yourserver/siteverify.php`.
Instead of `https://(eu-)api.friendlycaptcha.eu/api/v1/puzzle"` use `https://yourserver/puzzle.php`. 

## What works

* Check of signature
* Check of puzzles
* Check of timestamps
* Replay checks
* Basic difficulty scaling

## License 
This software is [**fair-code**](http://faircode.io) distributed under [**Apache 2.0 with Commons Clause**](https://github.com/FriendlyCaptcha/friendly-captcha-lite-server/blob/main/LICENSE) license.

## Troubleshooting 

### The widget shows an error when loading the puzzle 

* Check your server log for errors 
* Open /puzzle.php manually and see if there are any errors displayed
* Is LibSodium available?

### Captcha is not validated, even generated by the widget itself

* This should not happen, maybe file an issue including the server logs

### Invalid Captchas are accepted (for example form submitted before captcha was solved) 

* Friendly Captcha recommends to accept Captcha solutions on server errors, so also here check for server errors
* Is APCU and LibSodium available?

