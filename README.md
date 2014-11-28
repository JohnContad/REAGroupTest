Test Submission
===========

This contains a listing of files to be used as an Ansible Playbook. This aims to:

 - create an RHEL7 t2.micro instance in AWS
 - login to aforementioned instance, assigning it to a specific security group.
 - Install Apache
 - Install Ruby, RubyGems, and ModPassenger
 - Setup a zzz.conf file to do Apache LoadModules. Thanks Phusion, for not including the directive that *loads the module in Apache* in the installation script. :D
 - Pull down the sinatra app from the git repo.
 - Serve, hopefully.

I've been able to successfully run this multiple times - however, CDS from inside AWS are failing. None of the yum directives are working, all of a sudden - so I'm waiting the downtime out, as of time of writing. Not really the most ideal, if you're pulling down dependencies.

Local modifications include:

 - installation of Python-Boto
 - Usage of EC2.py
 - EPEL Repo installation

Possible improvements include:
 - creating a standardized image, so we don't have to mess around with Ruby installations.
 - throwing this (and a copy) behind an ELB, just for kicks.
 - more blink tags.

A few other notes:

 - I did not specify a security component, as those have been specified in the frontend firewall rules. I don't feel comfortable putting a specialized ruleset on each machine - it just makes more sense logistically, if it was consolidated to the frontend.
 - I apologize for any Ruby-ish problems. For the purposes of full disclosure, I have worked with Ruby very, very few times.
