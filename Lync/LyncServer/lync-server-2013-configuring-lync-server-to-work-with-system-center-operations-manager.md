---
title: Configuration de Lync Server pour qu’il fonctionne avec System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150b240fe0c2be769e407cacecd8440bd4596ae5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506231"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Configuration de Lync Server 2013 pour qu’il fonctionne avec System Center Operations Manager

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Pour configurer votre infrastructure Microsoft Lync Server 2013 afin qu’elle fonctionne avec System Center Operations Manager, vous devez effectuer les trois opérations suivantes :

  - Identifiez et configurez votre serveur d’administration principal de System Center Operations Manager. La configuration du serveur de gestion inclut l’installation de System Center Operations Manager 2012 ou System Center Operations Manager 2007 R2, ainsi que la configuration d’une base de données principale à l’aide de SQL Server. La version réelle de SQL Server que vous devez utiliser dépend de la version de System Center Operations Manager que vous utilisez. Pour plus d’informations, reportez-vous à [la rubrique Configuration du serveur de gestion principal dans Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifiez et configurez les ordinateurs Lync Server que vous souhaitez surveiller. Pour surveiller un ordinateur Lync Server à l’aide de System Center Operations Manager, vous devez installer les fichiers de l’agent System Center Operations Manager et configurer chaque serveur comme proxy.

  - Identifiez et configurez les ordinateurs que vous souhaitez utiliser comme *nœuds*de Lync Server Watcher. Les nœuds observateurs sont des ordinateurs qui exécutent régulièrement des transactions synthétiques de Lync Server, qui sont des applets de commande Windows PowerShell qui vérifient que les principaux composants de Lync Server, tels que la possibilité de se connecter au système ou la possibilité d’échanger des messages instantanés fonctionnent comme prévu.

Les rubriques de cette section contiennent des instructions pour l’exécution de chacune de ces tâches.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration du serveur d’administration principal dans Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Installation des packs d’administration Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Configuration des ordinateurs Lync Server qui seront surveillés dans Lync Server 2013](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Installation et configuration des nœuds observateur dans Lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

