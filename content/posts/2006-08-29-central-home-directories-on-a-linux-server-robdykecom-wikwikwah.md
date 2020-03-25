---
authors: ["robdyke"]
date: "2006-08-29T22:20:08Z"
guid: http://www.robdyke.com/noc/?p=210
categories:
  - No Overall Control
id: 210
tags:
- technology
- wiki
title: Central home directories on a linux server - robdyke.com wikwikwah
url: /2006/08/29/central-home-directories-on-a-linux-server-robdykecom-wikwikwah/
---
I have been working with [Jon](http://www.catburglary.net) solving some file and print puzzles for the network that he manages. The network has Windows XP and Apple OS X clients and provides services from a Suse server running OpenLDAP for authentication and Samba for file and print.

The little puzzle we have been working on has been incorporating the Apple OS X machines into the authenticated file and print network. Connecting the eMacs to the wider network would provide more services to the users of the machines and give Jon less management and security headaches over the current local users / afp-island that the machines currently live in.

Here's a link [I have been working with [Jon](http://www.catburglary.net) solving some file and print puzzles for the network that he manages. The network has Windows XP and Apple OS X clients and provides services from a Suse server running OpenLDAP for authentication and Samba for file and print.

The little puzzle we have been working on has been incorporating the Apple OS X machines into the authenticated file and print network. Connecting the eMacs to the wider network would provide more services to the users of the machines and give Jon less management and security headaches over the current local users / afp-island that the machines currently live in.

Here's a link](http://www.robdyke.com/wikwikwah/index.php/Central_home_directories_on_a_linux_server) 

The instructions so far...

\# Peel the otter...

Seriously though... getting the X clients to authenticate against the existing LDAP servers was easy. It is well documented and searchable thanks to the big G.

\# Stew 6 hours in a server room / back office

NFS and automounts have eaten a day our time in research and testing. We don't think that NFS is the best method of providing network home directories in this environment. If the SMB client on the OS X client wasn't so mangled a connection via Samba would have been prefered as Samba is already serving up /home and /other/dirs to the network of Windows XP workstations.

\# The pan is now ready. Discard contents and begin again with the prepared pan.

Looking again at a page from early in the day and now that we've been investigating LDAP, automount and NetInfo Manager the information on it makes more sense. I think we discarded the information earlier as we didn't want to install AFP on the file server. Thinking about it now, using AFP makes the most sense: Samba is installed to speak SMB to Windows clients, why not AFP?

[del.icio.us](http://del.icio.us/robd/osx%2Bafp)