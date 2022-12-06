=============================================================================
<Armitage - 12/05/2022>
=============================================================================
Thanks to redcanari for the fixes and updates - I forked from his work. 

Instructions for Armitage on Kali 2022.3 with latest updates. Java 18 breaks EVERYTHING, so avoid for now. Do everything below within a root prompt!:

msfdb init

edit /etc/postgresql/15/main/pg_hba.conf

on the line 97 (IPV4 local connections)
switch “scram-sha-256” to “trust”

systemctl enable postgresql
systemctl stop postgresql
systemctl start postgresql

java -version

if it says anything other than 11, lets go way back - because why not:

apt update; apt install -y openjdk-11-jdk

update-alternatives --config java

choose the openjdk-11 as the default. then run java -version to make sure it is good to go.

cd /opt

git clone https://github.com/r00t0v3rr1d3/armitage.git

cd armitage

./package.sh

cd release/unix

./armitage

username: msf
password: msf

Leave the rest. Do you want to start blah blah for you? Answer yes. 

Observed broken functionality / issues:
- Attacks - Find Attacks doesn't seem to work

=============================================================================
</Armitage - 12/05/2022>
=============================================================================

=============================================================================
Armitage - Cyber Attack Management for Metasploit
=============================================================================
   
                 *** http://www.fastandeasyhacking.com ***

1. What is Armitage?
   -----------------
Armitage is a graphical cyber attack management tool for Metasploit that 
visualizes your targets, recommends exploits, and exposes the advanced 
capabilities of the framework.

Advanced users will find Armitage valuable for managing remote Metasploit 
instances and collaboration. Armitage's red team collaboration features allow 
your team to use the same sessions, share data, and communicate through one 
Metasploit instance.

Armitage aims to make Metasploit usable for security practitioners who 
understand hacking but don't use Metasploit every day. If you want to learn 
Metasploit and grow into the advanced features, Armitage can help you.

(c) 2010-2015 Raphael Mudge. This project is licensed under the BSD license. 
See license.txt for more information.

2. Documentation
   -------------
The documentation for Armitage is located on the Armitage website at:
http://www.fastandeasyhacking.com. Read the FAQ and the Manual for 
information on connecting Armitage to Metasploit and using it.

3. Install and Update
   ----------
To get started, see the manual at http://www.fastandeasyhacking.com

4. Source Code
   -----------
This projected is hosted on <s>Google Code</s> GitHub at:
https://github.com/rsmudge/armitage

5. Disclaimer
   ----------
Use this code for your development and don't hack systems that you don't 
have permission to hack. The existence of this software does not reflect the 
opinions or beliefs of my current employers, past employers, future 
employers, or any small animals I come into contact with. Enjoy this 
software with my blessing. I hope it helps you learn and become a better 
security professional.

6. Contact
   -------
Report bugs in the issue tracker at:
https://github.com/rsmudge/armitage/issues

E-mail contact@fastandeasyhacking.com with other questions/concerns. Make
sure you peruse the FAQ and Manual first. 

You may also visit us on irc.freenode.net in #armitage

7. Credits for Third-Party Components
   -------
Draggable Tabbed Pane - (c) Tom Martin (Creative Commons 3.0 Share-Alike [Attribution Required] License)
http://stackoverflow.com/questions/60269/how-to-implement-draggable-tab-using-java-swing

Javassist 3.15 - (c) Shigeru Chiba 1999-2015 (Apache 2.0 License)
https://github.com/jboss-javassist/javassist
        (dependency for MsgPack for Java)

JGraphX - (c) JGraph Ltd 2006-2012 (BSD License)
http://www.jgraphx.com/

Metasploit Framework - (c) Rapid7 Inc. 2012 (BSD License)
http://www.metasploit.com/

msfgui - (c) Matt Weeks 2010-2012 (BSD License)
http://www.metasploit.com/

MsgPack for Java - (c) F. Sadayuki and M. Nishizawa (Apache 2.0 License)
https://github.com/msgpack/msgpack-java

PostgreSQL JDBC Connector - (c) 1997-2010, PostgreSQL Global Development Group (BSD License)
http://jdbc.postgresql.org/

Sleep 2.1 - (c) 2002-2009, Raphael Mudge (LGPL)
http://sleep.dashnine.org/
