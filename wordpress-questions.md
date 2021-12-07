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
</details>

---
