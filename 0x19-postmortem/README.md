# Postmortem Report

Following the launch of ALX's System Engineering & DevOps project 0x19, at approximately 12:00 East African Time (EAT) in Kenya, an outage ensued on an isolated Ubuntu 14.04 container running an Apache web server. GET requests to the server resulted in `500 Internal Server Error` responses instead of the expected HTML file defining a simple Holberton WordPress site.

## Debugging Process Overview

Bug debugger Brennan (BDB, my actual initials, conveniently used on the spot) encountered the issue around 19:20 PST upon opening the project. Here's a breakdown of the debugging process:

1. Utilized `ps aux` to inspect running processes, finding two `apache2` processes (`root` and `www-data`) functioning correctly.

2. Explored the `sites-available` directory in `/etc/apache2/`, confirming the server served content from `/var/www/html/`.

3. Employed `strace` on the PID of the `root` Apache process in one terminal while testing the server with `curl` in another, yielding no useful insights initially.

4. Repeated the `strace` process with the `www-data` process, discovering an `-1 ENOENT (No such file or directory)` error trying to access `/var/www/html/wp-includes/class-wp-locale.phpp`.

5. Scanned files in `/var/www/html/`, using Vim pattern matching to identify the erroneous `.phpp` file extension, pinpointing it in `wp-settings.php` (Line 137).

6. Corrected the typo by removing the trailing `p`.

7. Confirmed resolution with another `curl` test, receiving a 200 status.

8. Automated the fix with a Puppet manifest.

## Summary

In essence, a simple typo caused the issue. Specifically, the WordPress app encountered a critical error in `wp-settings.php` while trying to load `class-wp-locale.phpp` instead of the correct `class-wp-locale.php` located in the `wp-content` directory.

The solution involved a straightforward correction of the typo by removing the extra `p`.

## Preventive Measures

This outage stemmed from an application error rather than a web server malfunction. To forestall similar incidents:

* Advocate thorough testing before deployment to catch and rectify such errors preemptively.
* Implement status monitoring tools like [UptimeRobot](https://uptimerobot.com/) for prompt outage alerts.

In response to this incident, a Puppet manifest named [0-strace_is_your_friend.pp](https://github.com/bdbaraban/holberton-system_engineering-devops/blob/master/0x17-web_stack_debugging_3/0-strace_is_your_friend.pp) was created to automate fixing identical errors in the future. The manifest replaces any `phpp` extensions in `/var/www/html/wp-settings.php` with `php`.

But let's face it, as programmers, we never make errors! 😉