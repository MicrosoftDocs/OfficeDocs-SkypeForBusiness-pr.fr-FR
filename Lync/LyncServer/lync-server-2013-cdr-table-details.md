---
title: 'Lync Server 2013 : détails de la table CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a9554be31e4ea93d7b8a0a2fc0de040d26d78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508051"
---
# <a name="cdr-table-details-in-lync-server-2013"></a>Détails de la table CDR dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Les rubriques suivantes présentent en détail les colonnes de chacune des tables de schéma de la base de données des enregistrements des détails des appels.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Table application dans Lync Server 2013](lync-server-2013-application-table.md)

  - [Table table callpriorities dans Lync Server 2013](lync-server-2013-callpriorities-table.md)

  - [Table CallType dans Lync Server 2013](lync-server-2013-calltype-table.md)

  - [Table ClientVersions dans Lync Server 2013](lync-server-2013-clientversions-table.md)

  - [Table ConferenceJoinTimeThresholds dans Lync Server 2013](lync-server-2013-conferencejointimethresholds-table.md)

  - [Table ConferenceMessageCount dans Lync Server 2013](lync-server-2013-conferencemessagecount-table.md)

  - [Tableau conférences dans Lync Server 2013](lync-server-2013-conferences-table.md)

  - [Table ConferenceSessionDetails dans Lync Server 2013](lync-server-2013-conferencesessiondetails-table.md)

  - [Table ConferenceUris dans Lync Server 2013](lync-server-2013-conferenceuris-table.md)

  - [Table ContentTypes dans Lync Server 2013](lync-server-2013-contenttypes-table.md)

  - [Table DeRegisterType dans Lync Server 2013](lync-server-2013-deregistertype-table.md)

  - [Table Devices dans Lync Server 2013](lync-server-2013-devices-table.md)

  - [Table Dialogs dans Lync Server 2013](lync-server-2013-dialogs-table.md)

  - [Table table edgeservers dans Lync Server 2013](lync-server-2013-edgeservers-table.md)

  - [Table ErrorCategory dans Lync Server 2013](lync-server-2013-errorcategory-table.md)

  - [Table table errordef dans Lync Server 2013](lync-server-2013-errordef-table.md)

  - [Table ErrorReport dans Lync Server 2013](lync-server-2013-errorreport-table.md)

  - [Table FileTransfers dans Lync Server 2013](lync-server-2013-filetransfers-table.md)

  - [Table FocusJoinsAndLeaves dans Lync Server 2013](lync-server-2013-focusjoinsandleaves-table.md)

  - [Table FrontEnd dans Lync Server 2013](lync-server-2013-frontend-table.md)

  - [Tableau des passerelles dans Lync Server 2013](lync-server-2013-gateways-table.md)

  - [Table table hardwareversions dans Lync Server 2013](lync-server-2013-hardwareversions-table.md)

  - [Table IMReportSummary dans Lync Server 2013](lync-server-2013-imreportsummary-table.md)

  - [Table locations dans Lync Server 2013](lync-server-2013-locations-table.md)

  - [Table Manufacturers dans Lync Server 2013](lync-server-2013-manufacturers-table.md)

  - [Table McuJoinsAndLeaves dans Lync Server 2013](lync-server-2013-mcujoinsandleaves-table.md)

  - [Table MCU dans Lync Server 2013](lync-server-2013-mcus-table.md)

  - [Table Media dans Lync Server 2013](lync-server-2013-media-table.md)

  - [Table médial dans Lync Server 2013](lync-server-2013-medialist-table.md)

  - [Table table mediationservers dans Lync Server 2013](lync-server-2013-mediationservers-table.md)

  - [Table table msmqprocessing dans Lync Server 2013](lync-server-2013-msmqprocessing-table.md)

  - [Table téléphones dans Lync Server 2013](lync-server-2013-phones-table.md)

  - [Table pools dans Lync Server 2013](lync-server-2013-pools-table.md)

  - [Table ProgressReport dans Lync Server 2013](lync-server-2013-progressreport-table.md)

  - [Table PurgeSettings dans Lync Server 2013](lync-server-2013-purgesettings-table.md)

  - [Table Registration dans Lync Server 2013](lync-server-2013-registration-table.md)

  - [Table Roles dans Lync Server 2013](lync-server-2013-roles-table.md)

  - [Table Servers dans Lync Server 2013](lync-server-2013-servers-table.md)

  - [Table SessionDetails dans Lync Server 2013](lync-server-2013-sessiondetails-table.md)

  - [Table SIPResponseMetaData dans Lync Server 2013](lync-server-2013-sipresponsemetadata-table.md)

  - [Table table syndicators dans Lync Server 2013](lync-server-2013-syndicators-table.md)

  - [Table table syndicatorstenantmap dans Lync Server 2013](lync-server-2013-syndicatorstenantmap-table.md)

  - [Table de tâches dans Lync Server 2013](lync-server-2013-task-table.md)

  - [Table locataires dans Lync Server 2013](lync-server-2013-tenants-table.md)

  - [Table UriTypes dans Lync Server 2013](lync-server-2013-uritypes-table.md)

  - [Table users dans Lync Server 2013](lync-server-2013-users-table.md)

  - [Table table useragentdef dans Lync Server 2013](lync-server-2013-useragentdef-table.md)

  - [Table UserStatistics dans Lync Server 2013](lync-server-2013-userstatistics-table.md)

  - [Table VoipDetails dans Lync Server 2013](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

