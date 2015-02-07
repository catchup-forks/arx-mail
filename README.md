# Arx Mail

[![Latest Stable Version](https://poser.pugx.org/arx/mail/v/stable.png)](https://packagist.org/packages/arx/mail)
[![Total Downloads](https://poser.pugx.org/arx/mail/downloads.png)](https://packagist.org/packages/arx/mail)
[![License](https://poser.pugx.org/arx/mail/license.png)](http://opensource.org/licenses/MIT)


## Features

* Simple Wrapper for Mail Sending

## Getting started

### Requirements

- PHP > 5.3
- [Composer](http://www.getcomposer.org)

### Installation

```bash
$ composer require arx/mail
```

Or in the `require` key of your `composer.json` file add the following

```json
"arx/mail": "dev-master"
```

then 

```bash
$ composer update
```

### How to use it

```php
    <?php
    
    require_once __DIR__ . '/../vendor/autoload.php';
    
    use Arx\Mail\Mail;
    
    #1. Config the Mail class
    Mail::config(array(
        /*
            |--------------------------------------------------------------------------
            | Mail Driver
            |--------------------------------------------------------------------------
            |
            | Laravel supports both SMTP and PHP's "mail" function as drivers for the
            | sending of e-mail. You may specify which one you're using throughout
            | your application here. By default, Laravel is setup for SMTP mail.
            |
            | Supported: "smtp", "mail", "sendmail"
            |
            */
    
        'driver' => 'smtp',
    
        /*
        |--------------------------------------------------------------------------
        | SMTP Host Address
        |--------------------------------------------------------------------------
        |
        | Here you may provide the host address of the SMTP server used by your
        | applications. A default option is provided that is compatible with
        | the Postmark mail service, which will provide reliable delivery.
        |
        */
    
        'host' => 'smtp.mailgun.org',
    
        /*
        |--------------------------------------------------------------------------
        | SMTP Host Port
        |--------------------------------------------------------------------------
        |
        | This is the SMTP port used by your application to delivery e-mails to
        | users of your application. Like the host we have set this value to
        | stay compatible with the Postmark e-mail application by default.
        |
        */
    
        'port' => 587,
    
        /*
        |--------------------------------------------------------------------------
        | Global "From" Address
        |--------------------------------------------------------------------------
        |
        | You may wish for all e-mails sent by your application to be sent from
        | the same address. Here, you may specify a name and address that is
        | used globally for all e-mails that are sent by your application.
        |
        */
    
        'from' => array('address' => 'private@cherrypulp.com', 'name' => 'Arxmin-Contrib'),
    
        /*
        |--------------------------------------------------------------------------
        | E-Mail Encryption Protocol
        |--------------------------------------------------------------------------
        |
        | Here you may specify the encryption protocol that should be used when
        | the application send e-mail messages. A sensible default using the
        | transport layer security protocol should provide great security.
        |
        */
    
        'encryption' => 'tls',
    
        /*
        |--------------------------------------------------------------------------
        | SMTP Server Username
        |--------------------------------------------------------------------------
        |
        | If your SMTP server requires a username for authentication, you should
        | set it here. This will get used to authenticate with your server on
        | connection. You may also set the "password" value below this one.
        |
        */
    
        'username' => null,
    
        /*
        |--------------------------------------------------------------------------
        | SMTP Server Password
        |--------------------------------------------------------------------------
        |
        | Here you may set the password required by your SMTP server to send out
        | messages from your application. This will be given to the server on
        | connection so that the application will be able to send messages.
        |
        */
    
        'password' => null,
    
        /*
        |--------------------------------------------------------------------------
        | Sendmail System Path
        |--------------------------------------------------------------------------
        |
        | When using the "sendmail" driver to send e-mails, we will need to know
        | the path to where Sendmail lives on this server. A default path has
        | been provided here, which will work well on most of your systems.
        |
        */
    
        'sendmail' => '/usr/sbin/sendmail -bs',
    
        /*
        |--------------------------------------------------------------------------
        | Mail "Pretend"
        |--------------------------------------------------------------------------
        |
        | When this option is enabled, e-mail will not actually be sent over the
        | web and will instead be written to your application's logs files so
        | you may inspect the message. This is great for local development.
        |
        */
    
        'pretend' => false,
    
    ));
    
    # Send and email
    Mail::send(
        // Send message like the SwiftMessage : http://swiftmailer.org/docs/messages.html
        Mail::message()
            ->setFrom('test@test.com', 'TEST')
            ->setTo(array('test@test.com'))
            ->setBody('TEST')
    );
    
```

### Advanced

See ** [the wiki page for more infos](https://github.com/arx/php-mail/wiki) **

## Release Notes

### Version 4.2.0

- use Laravel tagging version to simplify the version correspondance (so yes we start directly from 4.2 instead of 1.0)


## License

Arx Mail is free software distributed under the terms of the MIT license

## Aditional information

Any questions, feel free to contact me or ask [here](https://github.com/arx/php-mail/issues)

Any issues, please [report here](https://github.com/arx/php-mail/issues)