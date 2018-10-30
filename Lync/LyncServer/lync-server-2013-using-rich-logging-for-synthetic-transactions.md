---
title: Utilisation de la journalisation enrichie pour les transactions synthétiques
TOCTitle: Utilisation de la journalisation enrichie pour les transactions synthétiques
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204798(v=OCS.15)
ms:contentKeyID: 49296807
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de la journalisation enrichie pour les transactions synthétiques

 

_**Dernière rubrique modifiée :** 2012-10-22_

Les transactions synthétiques (une nouveauté de Microsoft Lync Server 2010) offrent la possibilité aux administrateurs de vérifier que les utilisateurs peuvent exécuter les tâches courantes, notamment se connecter au système, échanger des messages instantanés ou appeler un numéro de téléphone sur le réseau téléphonique commuté (PSTN). Ces tests (packagés sous la forme d’un ensemble d’applets de commande Windows PowerShellLync Server) peuvent être effectués manuellement par un administrateur ou exécutés automatiquement par une application telle que System Center Operations Manager.

Dans Lync Server 2010, les transactions synthétiques se sont révélées extrêmement utiles pour aider les administrateurs à identifier les problèmes du système. Par exemple, l’applet de commande **Test-CsRegistration** pouvait alerter les administrateurs quand certains utilisateurs rencontraient des problèmes pour s’inscrire à Lync Server. Toutefois, les transactions synthétiques se sont avérées moins utiles pour déterminer les causes des problèmes rencontrés par ces utilisateurs pour l’inscription à Lync Server. La raison en est que les transactions synthétiques ne fournissaient pas d’informations de journalisation détaillées qui auraient pu aider les administrateurs à corriger les problèmes liés à Lync Server. Au mieux, la sortie détaillée d’une transaction synthétique fournissait des informations pas à pas susceptibles de permettre à un administrateur d’émettre des hypothèses éclairées sur l’origine du problème.

Dans Microsoft Lync Server 2013, les transactions synthétiques ont été restructurées pour fournir une « journalisation enrichie », c’est-à-dire que, pour chaque activité entreprise par une transaction synthétique, des informations telles que celles qui suivent seront enregistrées :

  - L’heure de début de l’activité

  - L’heure de fin de l’activité

  - L’action effectuée (par exemple, la création, participation ou fin de participation à une conférence, la connexion à Lync Server, l’envoi d’un message instantané, etc.)

  - Les messages informatifs, détaillés, d’avertissement ou d’erreur générés pendant l’exécution de l’activité

  - Les messages d’inscription SIP

  - Les enregistrements d’exception ou codes de diagnostic générés pendant l’exécution de l’activité

  - Le résultat net suite à l’exécution de l’activité

Ces informations sont automatiquement générées à chaque exécution d’une transaction synthétique. Toutefois, elles ne sont pas automatiquement affichées ou enregistrées dans un fichier journal. En revanche, les administrateurs qui exécutent manuellement une transaction synthétique peuvent utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle seront stockées les informations. À partir de là, les administrateurs peuvent utiliser deux méthodes pour enregistrer et/ou afficher le journal enrichi au format XML ou HTML.

Par exemple, les administrateurs Lync Server 2010 peuvent exécuter l’applet de commande **Test-CsRegistration** à l’aide d’une commande de type :

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Ils ont la possibilité d’inclure le paramètre OutLoggerVariable suivi d’un nom de variable de leur choix :

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Ne faites pas précéder le nom de variable du caractère $. Utilisez un nom de variable comme RegistrationTest et non $RegistrationTest.

La commande précédente permet d’obtenir du contenu de type :

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Toutefois, il est possible d’obtenir des informations bien plus détaillées pour cette panne que le simple message d’erreur indiqué plus haut. Utilisez une commande de ce type pour enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML et pouvoir y accéder :

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Ces fichiers peuvent ensuite être affichés dans Internet Explorer, Visual Studio ou toute autre application capable d’ouvrir des fichiers HTML/XML.

Les transactions synthétiques exécutées à partir du System Center Operations Manager génèrent automatiquement ces fichiers journaux en cas de panne. Toutefois, ces journaux ne sont pas générés si l’exécution échoue avant que Windows PowerShell n’ait pu charger et exécuter la transaction synthétique.

> [!IMPORTANT]  
> Par défaut, Lync Server 2013 enregistre des fichiers journaux dans un dossier non partagé. Pour les rendre facilement accessibles, vous devez partager ce dossier (par exemple, \\atl-watcher-001.litwareinc.com\WatcherNode.
