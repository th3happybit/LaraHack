# EasyHack

EasyHack is a complete administration systems designed especially for hackathons and similar competitions .
For participants , it's a clean and simple to submit application with or without team and confirm attendance .
For Organizers , it's an easy way to create your hackathon website , view registrations , analyze statistics , Check-In and much more ! 

# Features 

- **WebSite Template** : Easyhack has a website template that contains all necessary sections ( About , Challenges , Sponsors .. ) with a clean code so you can modify and customize it . 

- **Registration** : With Easyhack hackers can register easily with or without a team through a register view that is similar to TypeForm and also.

- **Statistics** : The admin has access to a lot of statistics about registration such us registrations rate per day , decisions about hackers ... and muc more ! 

- **Dashboard** : Admin can view all applications to the hackathon , take a decision and export data to Excel or CSV .

- **Mailing** : Easyhack is able to send emails such as : 
    - Successful application: which is sent to every hacker who apply , informing him that his application is done successfully and providing him with his team's name and team's code if he choosed to register with a team .
    - Decision : Waiting list , Rejected Or Accepted with confirm attendance link .
- **Check-In** : Allows organizers to check the participants present at the event day . 

- **Settings** : Configure some essential settings ( at the moment it contains only the possibility to close or open registrations ) . 

# Screenshots 

![Statistics Page](/Screenshots/Statistics.png)
![Registration Page](/Screenshots/Register.PNG)
![Hackers Table](/Screenshots/Hackers.png)
![Check-In Page](/Screenshots/Checkin.png)

# Setup 

### Quick deploy with Heroku 

### Requirements 
| Requirement                                 | Version |
| ------------------------------------------- | ------- |
| [PHP](https://www.php.net)                | `7.1+`  |
| [Composer](https://getcomposer.org) | `1.8+`  |
| [MySQL](https://www.mysql.com) | `8.0+`  |

Run the following commands to check the current installed versions:

```bash
php --version
```

For MySQL You can run this command in MySQL Commande Line Client : 
```bash
select version() ;
```

### Deploy locally 

Getting a local instance of EasyHack up and running is very quickly ! Start By Creating A Database on MySQL and go with these steps : 

1 - Clone the repository and cd to the project folder:
```bash
git clone https://github.com/ScientificClubofESI/EasyHack 
cd EasyHack 
```

2 - Install the necessary dependencies:
```bash
composer install  
```

3 - Create your `.env` file from `.env.example` and generate an app key (Don't forget to configure it with the database, and your email , if the host is googlemail so let mail driver , host and port as it was in env.example ; else you should change them ) :
```bash
cp .env .env.example
php artisan key:generate  
```

4 - Migrate the database , start listening a queue and run the server (The 2 last in different terminals): 
```bash
php artisan migrate 
php artisan queue:listen database 
php artisan serve
```

# Customizing for your event 

### Hackathon name 

Don't forget to put your hackathon name in environment variable `APP_NAME` 

### Hackathon Logo 

Put your hackathon logo in the folder `/public/images` with the name of `LOGO.png`

### Hackathon Landing Page  

You find the hackathon landing page section in the folder `/resources/views/sections` with a clean and simple code 

### Mail Content 

To customize the decision and confirmation emails for your event, edit email templates in 
`/resources/views/emails` 

## Notes : 

- Access to the admin dashboard via the link `/admin` 
- The default mail and password are : `admin@cse.dz` and `cse` you can change them in the migrations folder `database/migrations`

# Contributing 

Do you have a feature request, bug report, or patch? Great! See
[CONTRIBUTING.md][contribute] for information on what you can do about that.
Contributions to EasyHack are welcome and appreciated !

# Feedback / Questions 

If you have any questions about this software, please contact ha_zellat@esi.dz or ga_namani@esi.dz .

# License 

Copyright (c) 2019 Scienitif Club Of ESI (https://github.com/ScientificClubofESI). Released under AGPLv3. See [`LICENSE`][license] for details.

[contribute]: https://github.com/ScientificClubofESI/EasyHack/blob/master/CONTRIBUTING.md
[license]: https://github.com/ScientificClubofESI/EasyHack/blob/master/LICENSE

	
