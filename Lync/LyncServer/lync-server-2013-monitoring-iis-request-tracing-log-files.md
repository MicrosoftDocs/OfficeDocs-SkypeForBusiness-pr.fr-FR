---
title: 'Lync Server 2013 : surveillance des fichiers journaux de suivi des demandes IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1eb64fe83eb6f80c6470ba4173bcc968d44fb54a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Surveillance des fichiers journaux de suivi des demandes IIS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Lorsque vous activez le suivi des demandes IIS (Internet Information Services) pour le service Lync Server Mobility (MCX), les fichiers journaux générés peuvent consommer jusqu’à trois gigaoctets d’espace disque par jour. La journalisation du suivi IIS est activée par défaut. Vous devez analyser les serveurs frontaux pour vous assurer qu’ils ne manquent pas d’espace disque.

Par défaut, les services Internet (IIS) stockent les\\fichiers\\journaux\\dans% SystemDrive% Inetpub logs journaux.

Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Pour plus d’informations **** sur la commande httpLogging [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927), reportez-vous à la rubrique.

</div>

<span> </span>

</div>

</div>

</div>

