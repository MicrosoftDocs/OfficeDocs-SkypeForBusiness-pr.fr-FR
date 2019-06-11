---
title: Configuration de Lync Server pour utiliser System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6f26d4701cf1ed48f0069bcf7994e20ef0b2af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Configuration de Lync Server 2013 pour fonctionner avec System Center Operations Manager

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Pour configurer votre infrastructure Microsoft Lync Server 2013 de manière à utiliser System Center Operations Manager, vous devez effectuer les trois opérations suivantes:

  - Identifiez et configurez votre serveur de gestion Operations Manager principal. La configuration du serveur de gestion inclut l’installation de System Center Operations Manager 2012 ou System Center Operations Manager 2007 R2, ainsi que la configuration d’une base de données principale à l’aide de SQL Server. La version réelle de SQL Server que vous devez utiliser dépend de la version de System Center Operations Manager que vous utilisez. Pour plus d’informations, reportez-vous à [configuration du serveur de gestion principal dans Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifiez et configurez les ordinateurs serveur Lync que vous souhaitez surveiller. Pour surveiller un ordinateur Lync Server à l’aide de System Center Operations Manager, vous devez installer les fichiers de l’agent System Center Operations Manager et configurer chaque serveur pour qu’il serve de proxy.

  - Identifiez et configurez les ordinateurs que vous voulez utiliser en tant que nœuds d' *Observateur*Lync Server. Les nœuds d’observation sont des ordinateurs qui exécutent périodiquement les transactions synthétiques de Lync Server, qui sont des cmdlets Windows PowerShell qui vérifient que les composants clés de Lync Server, tels que la possibilité de se connecter au système ou la possibilité d’échanger des messages instantanés, sont travail attendu.

Les rubriques de cette section contiennent des instructions pour exécuter chacune de ces tâches.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration du serveur de gestion principal dans Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Installation des packs d’administration de Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Configuration des ordinateurs serveur Lync qui seront surveillés dans Lync Server 2013](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Installation et configuration des nœuds d’observation dans Lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

