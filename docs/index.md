## Welcome to The Ultimate School Manager

### Introduction
The Ultimate School Manager is designed	to integrate the disparate school processes of financial management, enrolments, student management, student behavior, timetabling, and academic reporting into a user-friendly, technologically advanced solution.
The Ultimate School Manager is developed to be robust, powerful and extremely flexible in all aspects with an intuitive user interface, Hence 
providing secure access to data from any location (on and off School) via	a web browser. It can	be integrated with an existing school website or portal and can be fully configured to provide appropriate access to the wider	school community including teachers, staff and parents.

### Geting Started
Extract the contents of the zip to your server. If you are on CPanel create a domain or subdomain and set the Document  Root to be `yourdomain.com/public` the contents of `yourdomain.com` should look like this:
```
youdomain.com
	app
	bootstrap
	config
	database
	elimuswift
	public
	resources
	routes
	storage
	supervisor
	vendor
		.env
		VERSION
		artisan
		composer.json
		....
```

The easiest way to get started is by using the web installer, this will handle evrything for for you. 
Before you launch the application make sure you have created a datbase and you have a username and password to connect to you database.
Next on the root of the application look for a file named `.env` the file will look simmilar to:

```php
APP_ENV=production
APP_KEY=
APP_DEBUG=false
APP_LOG_LEVEL=debug

BROADCAST_DRIVER=log

PUSHER_APP_ID=
PUSHER_KEY=
PUSHER_SECRET=

APP_URL=http://localhost

#Database Connection

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=elimuswift
DB_USERNAME=root
DB_PASSWORD=null

CACHE_DRIVER=file
SESSION_DRIVER=file
QUEUE_DRIVER=file

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

# Mail Configuration

MAIL_DRIVER=smtp
MAIL_HOST=mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=
MAIL_PASSWORD=
MAIL_ENCRYPTION=tls

MAILGUN_DOMAIN=
MAILGUN_SECRET=
MAILGUN_PUBLIC=
MAILGUN_FROM_ADDRESS=
MAILGUN_FROM_NAME=

STRIPE_KEY=
STRIPE_SECRET=

DROPBOX_APP=
DROPBOX_TOKEN=

SPARKPOST_SECRET=

SENTRY_DSN=https://bff472954a2c4666844dec16839b4524:88ac05034ca3404e970dc3ad1395e620@sentry.io/93562
2CO_PUBLIC=
2CO_SECRET=
2CO_SELLER=
2CO_ENV=production

BRAINTREE_ENV=production
BRAINTREE_SECRET=
BRAINTREE_KEY=
MERCHANT_ID=
```
 - Set the `APP_URL` key to be your sites domain,
 - Set your `#Database connection` details `(DB_USERNAME,DB_DATABASE, DB_PASSWORD)`

### Installation
With the database configured you are now ready to install *The Ultimate School Manager* on your server. Now go to `yourdomain.com` and you will see the installation wizard follow the steps until you complete the installation process.

## Configuration
There are a few things that have to be set up before you start using *The Ultimate School Manager* 

- [Emails](#emails)
	- [Mailgun](#mailgun)
	- [Sparkpost](#sparkpost)
	- [SMPT](#smtp)

- [SMS](#sms) 

### Emails
For emails to be sent from your application you have to configure the connection details. Mailgun, Sparkpost and SMPT are all supported out of the box

#### Mailgun
To use mailgun go to your mailgun dashboard and get your credentials.
	- From the administrator dashboard of your site go to `Settings > Email Settigs` you will see mailgun there paste your credentials and save.

#### Sparkpost 
Similar to [Mailgun](#mailgun) only that you have to save your keys on the sparkpost part.

### SMS
Student results and other notifications can be sent through SMS by default 11 SMS gatways are supported. [Africas Talking,](https://www.africastalking.com/) [Call Fire,](https://www.callfire.com/) [EZTexting,](https://www.eztexting.com) [FlowRoute,](https://www.flowroute.com/) [LabsMobile,](http://www.labsmobile.com) [Mozeo,](https://www.mozeo.com/) [Nexmo,](https://www.nexmo.com/) [Plivo,](https://www.plivo.com/) [Sematime,](https://www.sematime.com/)[Twilio,](https://www.twilio.com) [Zenvia](http://www.zenvia.com.br/) 
To configure sms go to `Settings > SMS Settings` and configure your preffered Gateway and then set it as the default SMS Gateway


### System Configuration

Before you start admiting students and staff please make sure you have created and set an academic and billig session.

#### Billing Session  
A billing session is used to group bills that recur. For instace Every January - April Semester There are bills that are always billed to student during this period. By default this convention is used throughout the Application so it is very important for you to understand thi concept. When creating bills and academic sessions you have to specify which billing perriod they fall into. *The Ultimate School Manager* comes configured with three billing sessions `(Term One, Term Two, Term Three)` If these does not fit into you plans you can create your own from 'Settings > Academic Settings' Then click on `Billing Session' Button 

#### Academic Session
This denotes the current Academic period  all school activites a grouped using an academic session. Each academic session is unique   

#### User Accounts
All Staff accounts have a default password of `staff123` and Parent Accounts have a default password `parent123` however when a user is signed up a confirmation link  is send to them from which they can set their passwords.