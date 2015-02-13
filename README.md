# CodeIgniter Recaptcha
An easy-to-use CodeIgniter library to work with reCAPTCHA version 2.0 a.k.a NO CAPTCHA reCAPTCHA.

![reCAPTCHA version 2.0 demo](https://www.google.com/recaptcha/intro/images/hero-recaptcha-demo.gif)

## Installation
Copy the files to their respective location.

##Configuration
Open "**application/config/recaptcha.php**" and put your SITE key, SECRET key, and desired language there.

```php
$config['recaptcha_sitekey'] = "";
$config['recaptcha_secretkey'] = "";
$config['lang'] = "";
```

Site key and secret key can be obtained from [https://www.google.com/recaptcha/admin/](https://www.google.com/recaptcha/admin/), while language code can be obtained from [https://developers.google.com/recaptcha/docs/language](https://developers.google.com/recaptcha/docs/language).

## Basic Usage Instruction
#### Call `render()` method from your VIEW file.
It will render reCAPTCHA widget onto your view
```php
<?php echo $this->recaptcha->render(); ?>
```
#### Validate in your CONTROLLER
```php
// Load the library
$this->load->library('recaptcha');

// Catch the user's answer
$captcha_answer = $this->input->post('g-recaptcha-response');

// Verify user's answer
$response = $this->recaptcha->verifyResponse($captcha_answer);

// Processing ...
if ($response['success']) {
    // Your success code here
} else {
    // Something goes wrong
    var_dump($response);
}
```

## Live demo
[http://rajaongkir.com/kontak](http://rajaongkir.com/kontak)