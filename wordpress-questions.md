# Wordpress Interview Questions
###### Q. What are mu-plugins?


<details><summary><b>Answer</b></summary>
<p>

A must-use plugin (also called a ‘mu-plugin’) is a plugin that will always be activated by default, without you needing to do it yourself. To activate a mu-plugin, you just have to upload it in the right directory, and WordPress will automatically know that this plugin must be used. Moreover, a mu-plugin cannot be deactivated: it will always be executed, unless it is uninstalled.

Originally, mu-plugins were only available for WPMU, for those sites which used multiple (multisite) blogs. Back then, a mu-plugin was just a plugin activated for all blogs.

Now, since the version 2.8, this feature is in the main branch of WordPress and the ‘MU’ part in mu-plugins has a new meaning: from ‘multi-user’, it became ‘must-use’ and the use of this feature has been changed.
  
  Origin : https://www.sitepoint.com/wordpress-mu-plugins/
</p>
</details>

---

###### Q. How to install WP-CLI on Windows?


<details><summary><b>Answer</b></summary>
<p>

  WP-CLI is the official command line tool for interacting with and managing your WordPress sites.
  <ol>
    <li>Download wp-cli.phar</li>
    <li>Create a folder c:\wp-cli</li>
    <li>Copy and Paste downloaded wp-cli.phar file in c:\wp-cli</li>
    <li>Create a named wp.bat in c:\wp-cli folder</li>
    <li>Paste the following code in wp.bat file and save wp.bat file in c:\wp-cli</li>
        @ECHO OFF
        php "c:/wp-cli/wp-cli.phar" %*
    <li>Set c:\wp-cli to your system PATH</li>
    From Windows Menu, open Environment Variables and select Path and click EDIT and ADD new environment variable and hit ok, ok, and ok.
    <li>Relaunch CMD, Go to path C:>wp-cli & Type wp help</li>

  </ol>
  Then, You will get all the options available through WP command and in that you will find <b>wp cli</b> option as well.
</p>

2

WP-CLI is just the ticket. I've used if for so many things, I've lost count!

wp plugin list --status=active
If you want, you can run these commands on your local machine with aliases...

You would then use the @site function

wp @all plugin list --status=active
or

wp @multisite list --status=active
wp @blog list --status=active
</details>

---

###### Q. What is WAF or Azure Web Application Firewall on Azure Application Gateway?


<details><summary><b>Answer</b></summary>
<p>

Azure Web Application Firewall (WAF) on Azure Application Gateway provides centralized protection of your web applications from common exploits and vulnerabilities.
  <ul>
    <li>Protect your web applications from web vulnerabilities and attacks without modification to back-end code</li>
    <li>Protect multiple web applications at the same time. An instance of Application Gateway can host up to 40 websites that are protected by a web application firewall</li>
    <li>Create custom WAF policies for different sites behind the same WAF</li>
    <li>Protect your web applications from malicious bots with the IP Reputation ruleset</li>
  </ul>
  Origin : https://docs.microsoft.com/en-us/azure/web-application-firewall/ag/ag-overview</br>
           https://docs.microsoft.com/en-us/azure/web-application-firewall/ag/create-waf-policy-ag
</p>
</details>

---

###### Q. How to set multiple virtual host?



###### Q. How to set multiple virtual host for wordpress multisite?

<b>If you are created new projects</b>
Download two wordpress e.g. WordPress 5.9 Beta 2
Give proper name to them e.g. beta
Create new db with same name as beta in phpMyadmin or in any other DB admin

<b>If there are existing projects, one with name baap and the new project with name beta</b>


<b>Below steps are common for both the cases</b>
Open C:\xampp\apache\conf\extra  and add virtual host entry in file named httpd-vhosts.conf
```
<VirtualHost *:80>

    ServerAdmin postmaster@beta.local

    DocumentRoot "C:\xampp\htdocs\beta"

    ServerName beta.local

    ServerAlias www.beta.local

    ErrorLog "logs/beta.local-error.log"

    CustomLog "logs/beta.local-access.log" combined

</VirtualHost>
```
Open C:\Windows\System32\drivers\etc and add host entry in file named hosts
127.0.0.1   beta.local

Save both the files
Restart the xampp<br>
If xampp shows error Error: Apache shutdown unexpectedly.
<details><summary><b>Solution</b></summary>
<p>

In XAMPP Control Panel V3.2.1, click on "NetStat" button on top right. Make sure port 80 is not used by any other program. Then click on "Shell" Right below it. Issue this command in the shell prompt;

```Apache_Start.bat```

or type "ap" then tab the TAB key two times which will similarly generate the above command. You will actually see the exact error why Apache failed. It will be mostly likely virtual host configuration issue or may be something else. It will display the line number on which the error is occurring. Just fix that error. Note that in RootDocument a trailing \ can be a source of error as well. Remove any trailing "".

</p>
</details>

Go to browser and type http://beta.local
If the site is new then do wp configuration step by step
If the site is old then<br>
Go into your MySQL database (thru phpmyadmin or whatever) and look for the following fields

In the wp_options table, change value for entry
```
siteurl
home
To http://beta.local instead of localhost or any previous url```

This will update all your links in wordpress.
---
