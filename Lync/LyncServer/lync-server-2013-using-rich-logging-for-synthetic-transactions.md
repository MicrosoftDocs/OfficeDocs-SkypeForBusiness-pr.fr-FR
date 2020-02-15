---
title: 'Lync Server 2013 : utilisation d’une journalisation enrichie pour les transactions synthétiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 421b691bd282b858eca64c9756e92dd24aac8b7b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Utilisation d’une journalisation enrichie pour les transactions synthétiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Les transactions synthétiques (introduites dans Microsoft Lync Server 2010) permettent aux administrateurs de vérifier que les utilisateurs peuvent effectuer correctement des tâches courantes telles qu’une ouverture de session sur le système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le réseau téléphonique commuté (RTC). Ces tests (qui sont empaquetés sous la forme d’un ensemble d’applets de commande Windows PowerShell de Lync Server) peuvent être effectués manuellement par un administrateur ou être exécutés automatiquement par une application telle que System Center Operations Manager.

Dans Lync Server 2010, les transactions synthétiques se sont révélées extrêmement utiles pour aider les administrateurs à identifier les problèmes liés au système. Par exemple, l’applet de commande **test-CsRegistration** pourrait alerter les administrateurs du fait que certains utilisateurs ont des difficultés à s’inscrire auprès de Lync Server. Toutefois, les transactions synthétiques étaient quelque peu moins utiles pour aider les administrateurs à déterminer pourquoi ces utilisateurs ont des difficultés à s’inscrire auprès de Lync Server. Cela est dû au fait que les transactions synthétiques n’ont pas fourni d’informations de journalisation détaillées pouvant aider les administrateurs à résoudre les problèmes liés à Lync Server. Au mieux, la sortie détaillée d’une transaction synthétique fournissait des informations pas à pas susceptibles de permettre à un administrateur d’émettre des hypothèses éclairées sur l’origine du problème.

Dans Microsoft Lync Server 2013, les transactions synthétiques ont été remaniées afin de fournir une journalisation enrichie. « Journalisation enrichie » signifie que, pour chaque activité qu’une transaction synthétique s’exécute, des informations telles que celles-ci seront enregistrées :

  - L’heure de début de l’activité

  - L’heure de fin de l’activité

  - Action effectuée (par exemple, la création, la participation ou la fermeture d’une conférence ; connexion à Lync Server ; envoi d’un message instantané, etc.)

  - Les messages informatifs, détaillés, d’avertissement ou d’erreur générés pendant l’exécution de l’activité

  - Les messages d’inscription SIP

  - Les enregistrements d’exception ou codes de diagnostic générés pendant l’exécution de l’activité

  - Le résultat net suite à l’exécution de l’activité

Ces informations sont automatiquement générées à chaque exécution d’une transaction synthétique. Toutefois, elles ne sont pas automatiquement affichées ou enregistrées dans un fichier journal. Au lieu de cela, les administrateurs qui exécutent manuellement une transaction synthétique peuvent utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle les informations seront stockées. À partir de là, les administrateurs peuvent utiliser deux méthodes pour enregistrer et/ou afficher le journal enrichi au format XML ou HTML.

Par exemple, les administrateurs de Lync Server 2010 peuvent exécuter l’applet de commande **test-CsRegistration** à l’aide d’une commande semblable à la suivante :

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

Ces fichiers peuvent ensuite être affichés à l’aide d’Internet Explorer, de Visual Studio ou de toute autre application capable d’ouvrir des fichiers HTML/XML.

Les transactions synthétiques exécutées à l’intérieur de System Center Operations Manager génèrent automatiquement ces fichiers journaux pour les échecs. Toutefois, ces journaux ne seront pas générés si l’exécution échoue avant que Windows PowerShell ne puisse charger et exécuter la transaction synthétique.

> [!IMPORTANT]  
> Par défaut, Lync Server 2013 enregistre les fichiers journaux dans un dossier qui n’est pas partagé. Pour faciliter l’accès à ces journaux, vous devez partager ce dossier (par exemple \\ \\, ATL-Watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

