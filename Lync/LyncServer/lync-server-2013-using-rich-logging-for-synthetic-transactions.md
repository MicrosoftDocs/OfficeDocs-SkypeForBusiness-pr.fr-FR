---
title: 'Lync Server 2013: utilisation de la journalisation détaillée pour les transactions synthétiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455d7bcdc14dd4d701d749407759cead0834906f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>Utilisation de la journalisation détaillée pour les transactions synthétiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Les transactions synthétiques (introduites dans Microsoft Lync Server 2010) permettent aux administrateurs de vérifier que l’utilisateur est en mesure d’effectuer des tâches courantes telles que la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone sur le réseau téléphonique public commuté (RTC). Ces tests (qui sont empaquetés sous la forme d’un ensemble de cmdlets Windows PowerShell Lync Server) peuvent être dirigés manuellement par un administrateur, ou s’ils peuvent être exécutés automatiquement par une application telle que System Center Operations Manager.

Dans Lync Server 2010, les transactions synthétiques ont été particulièrement utiles pour aider les administrateurs à identifier les problèmes du système. Par exemple, l’applet de **contrôle test-CsRegistration** peut signaler aux administrateurs que certains utilisateurs éprouvent des difficultés à s’inscrire auprès de Lync Server. Toutefois, les transactions synthétiques étaient légèrement moins utiles pour permettre aux administrateurs de déterminer pourquoi ces utilisateurs éprouvent des difficultés à s’inscrire auprès de Lync Server. Ce problème est dû au fait que les transactions synthétiques n’ont pas fourni d’informations de journalisation détaillées susceptibles d’aider les administrateurs à résoudre les problèmes avec Lync Server. Dans la mesure du possible, la sortie détaillée d’une transaction synthétique vous a fourni des informations détaillées qui pourraient permettre à un administrateur de découvrir à quel point un problème est susceptible de se produire.

Dans Microsoft Lync Server 2013, les transactions synthétiques ont été repensées pour fournir une journalisation enrichie. «La journalisation enrichie» signifie qu’à chaque activité qu’une transaction synthétique s’engage, des informations telles que celles-ci seront enregistrées:

  - Heure de début de l’activité

  - Heure de fin de l’activité

  - Action exécutée (par exemple, création, participation ou départ d’une conférence; connexion à Lync Server; envoi d’un message instantané; etc.)

  - Les messages informatifs, détaillés, d’avertissement ou d’erreur générés pendant l’exécution de l’activité.

  - Messages d’enregistrement SIP

  - Enregistrements d’exceptions ou codes de diagnostic générés lors de l’exécution de l’activité

  - Résultat net de l’exécution de l’activité

Ces informations sont générées automatiquement chaque fois qu’une transaction synthétique est exécutée. Toutefois, les informations ne sont pas affichées ou enregistrées automatiquement dans un fichier journal. À la place, les administrateurs exécutant une transaction synthétique manuellement peuvent utiliser le paramètre OutLoggerVariable pour spécifier une variable Windows PowerShell dans laquelle les informations seront stockées. À partir de là, les administrateurs peuvent utiliser une paire de méthodes qui leur permettent d’enregistrer et/ou d’afficher le journal enrichi au format XML ou HTML.

Par exemple, les administrateurs de Lync Server 2010 peuvent exécuter l’applet de commande **test-CsRegistration** à l’aide d’une commande similaire à ce qui suit:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

Les administrateurs ont la possibilité d’inclure le paramètre OutLoggerVariable, suivi du nom de la variable de leur choix:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> Ne faites pas précéder le nom de la variable du caractère $. Utilisez un nom de variable tel que RegistrationTest et non $RegistrationTest.

La commande précédente génère du contenu similaire à ce qui suit:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

Toutefois, des informations plus détaillées sont disponibles pour cet échec que le message d’erreur ci-dessus. Pour accéder à ces informations au format HTML, utilisez une commande similaire à celle-ci afin d’enregistrer les informations stockées dans la variable RegistrationTest dans un fichier HTML:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

Vous pouvez aussi utiliser la méthode ToXML() pour enregistrer les données dans un fichier XML :

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

Ces fichiers peuvent être affichés à l’aide d’Internet Explorer, Visual Studio ou de toute autre application capable d’ouvrir des fichiers HTML/XML.

Les transactions synthétiques exécutées à partir de System Center Operations Manager génèrent automatiquement ces fichiers journaux pour les échecs. Toutefois, ces journaux ne seront pas générés en cas d’échec de l’exécution avant que Windows PowerShell puisse charger et exécuter la transaction synthétique.

> [!IMPORTANT]  
> Par défaut, Lync Server 2013 enregistre les fichiers journaux dans un dossier qui n’est pas partagé. Pour rendre ces journaux facilement accessibles, vous devez partager ce dossier (par exemple, \\ \\ATL-Watcher-001. litwareinc. com\WatcherNode.


</div>

</div>

</div>

</div>

