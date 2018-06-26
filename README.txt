== Voraussetzungen

1. Git installieren        (https://git-scm.com/)
2. Vagrant installieren    (https://www.vagrantup.com/downloads.html)  - 2.0.2
3. VirtualBox installieren (https://www.virtualbox.org/wiki/Downloads) - 5.1.32
4. "git-bash" starten
5. Projekt clonen: git clone https://github.com/cecom/bmDoneRight.git
6. In Ordner wechseln: cd bmDoneRight
7. Damit das sharen des Ordners in die VM funktioniert, folgendes ausführen:
     vagrant plugin install vagrant-vbguest 
8. Ordner downloads anlegen: mkdir downloads
9. Eclipse runterladen und in den downloads Ordner legen. Es wird nach eclipse-jee-oxygen-2-linux-gtk-x86_64.tar.gz gesucht: 
     z.B. http://www.eclipse.org/downloads/download.php?file=/technology/epp/downloads/release/oxygen/2/eclipse-jee-oxygen-2-linux-gtk-x86_64.tar.gz&mirror_id=96
10. Wenn Host Betriebsystem Windows ist, brauch man noch einen XServer. Wie z.B. XMING oder MobaXTERM, damit man Eclipse etc. starten kann. Anschließend in der VM: export DISPLAY=<ip>:0.0 ausführen
	 
== VM das erste mal starten
1. Im Ordner bmDoneRight: vagrant up
2. Beim ersten mal dauert es ca. 15-30 Minuten. Er installiert jetzt die komplette VM mit all seinen Tools.
3. Wenn es das erste mal ist:
    - Nachdem er fertig ist, die Datei "Vagrantfile" editieren und die Zeile: 
		config.vm.synced_folder ".", "/vagrant"
	  suchen
	- Das Kommentar Zeichen "#" davor machen
	- Die nachfolgende Zeile das "#" entfernen. Es sollte dann so aussehen:
		 #config.vm.synced_folder ".", "/vagrant"
         config.vm.synced_folder ".", "/vagrant", type: "virtualbox"
4. Nun folgendes eingeben: vagrant reload

== VM anhalten
1. Im Ordner bmDoneRight: vagrant halt

== VM erneut starten
1. Im Ordner bmDoneRight: vagrant up


== Vagrant Befehle
Connecten in die VM    : vagrant ssh

Passwort für root      : vagrant

Anhalten der VM        : vagrant halt
Zerstörten der VM      : vagrant destroy
Konfiguration neu laden: vagrant reload
Neu versorgen          : vagrant provision

== Via SSH in vagrant connecten ohne vagrant ssh
1. vagrant ssh-config > vagrant-ssh
2. ssh -F vagrant-ssh default

== Via SCP etwas rauskopieren (ohne shared lib)
1. vagrant ssh-config > vagrant-ssh
2. scp -F vagrant-ssh default:~/.bashrc .


== Installierte Software
1. notepadqq
2. gedit																	
3. eclipse
4. ansible
5. gerrit
6. jenkins
7. git
8. jdk
9. maven
10. mysql
11. p4merge
12. liquibase
13. pacify
14. mariadb
15. derby
16. sonarqube

