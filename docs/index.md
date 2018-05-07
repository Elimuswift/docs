### Geting Started
Extract the contents of the zip to your server. If you are on CPanel create a domain or subdomain and set the Document  Root to be `yourdomain.com/public` the contents of `yourdomain.com` should look like this:
```
youdomain.com
	app
	bootstrap
	config
	database
	public
	resources
	routes
	storage
	vendor
		.env
		.htaccess
		VERSION
		artisan
		composer.json
		....
```
Now open `.htaccess` file in the root directory and change `example.com` to your domain name. Now give write permissions to your web server these directories `storage/, bootstrap/cache, public/images public/tmp`.

```bash
$ chmod 775 storage -R
$ chmod 775 bootstrap/cache
$ chmod 775 public/images -R
$ chmod 775 public/tmp
```

### Set Up The Environment

The easiest way to get started is by using the web installer, this will handle evrything for for you. 
Before you launch the application make sure you have created a datbase and you have a username and password to connect to your database.
Next on the root of the application look for a file named `.env` the file will look simmilar to:

```bash
APP_ENV=production
APP_KEY=
APP_DEBUG=false
APP_LOG_LEVEL=debug
BROADCAST_DRIVER=log

PUSHER_APP_ID=
PUSHER_KEY=
PUSHER_SECRET=

APP_URL=http://localhost

....
```
 - Set the `APP_URL` key to be your sites domain,
 - Set your `#Database connection` details `(DB_USERNAME,DB_DATABASE, DB_PASSWORD)`

### Installation
With the database configured you are now ready to install *Elimuswift Ultimate School Manager* on your server. Now go to `yourdomain.com` and you will see the installation wizard follow the steps until you complete the installation process.

## Configuration
There are a few things that have to be set up before you start using *Elimuswift Ultimate School Manager* 

## Emails
For emails to be sent from your application you have to configure the connection details. Mailgun, Sparkpost and SMPT are all supported out of the box

### Mailgun
To use mailgun go to your mailgun dashboard and get your credentials.

- From the administrator dashboard of your site go to `Settings > Email Settigs` you will see mailgun there paste your credentials and save.

### Sparkpost 
Similar to [Mailgun](#mailgun) only that you have to save your keys on the sparkpost part.

## SMS
Student results and other notifications can be sent through SMS by default 11 SMS gatways are supported. [Africas Talking,](https://www.africastalking.com/) [Nexmo,](https://www.nexmo.com/) [Twilio](https://www.twilio.com) 
To configure sms go to `Settings > SMS Settings` and configure your preffered Gateway and then set it as the default SMS Gateway. 

If your local SMS provider is not supported please contact us to help you out. If you feel you can do it yourself then got to [SMS Driver Package](https://github.com/Elimuswift/sms) fork it and implement your driver then create a pull request 

## System Configuration

Before you start admiting students and staff please make sure you have created and set an academic and billig session after that set the academic session as active.

### Billing Cycles  
A billing session is used to group bills that recur. For instace Every January - April Semester There are bills that are always billed to student during this period. By default this convention is used throughout the Application so it is very important for you to understand thi concept. When creating bills and academic sessions you have to specify which billing perriod they fall into. *The Ultimate School Manager* comes configured with three billing sessions `(Term One, Term Two, Term Three)` If these does not fit into you plans you can create your own from 'Settings > Academic Settings' Then click on `Billing Cycles` Tab 

### Academic Session
This denotes the current Academic period  all school activites a grouped using an academic session. An academec session is simmilar to a billing cycle with the main diference being an academic session is unique.

### User Accounts
All Staff accounts have a default password of `staff123` and Parent Accounts have a default password `parent123` however when a user is signed up a confirmation link  is send to them from which they can set their passwords.