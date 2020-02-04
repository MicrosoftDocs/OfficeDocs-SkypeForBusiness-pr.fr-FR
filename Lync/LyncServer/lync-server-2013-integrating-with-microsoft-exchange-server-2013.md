---
title: 'Lync Server 2013 : intégration avec Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-09_

Exchange et Lync Server présentent un historique d’intégration et de compatibilité longs. Cette intégration est plus notable dans l’application cliente correspondante. Par exemple, les informations de présence Lync peuvent être rapportées dans Microsoft Outlook. de même, Lync peut utiliser le calendrier Outlook pour mettre automatiquement à jour les informations de présence. (Par exemple, Lync peut définir votre statut sur occupé chaque fois que votre calendrier indique qu’une réunion est planifiée.) Même si vous n’avez pas besoin d’exécuter Exchange pour pouvoir exécuter Lync Server (ou inversement), il n’y a pas de doute que l’utilisation conjointe de deux produits a pour but epitomizes de définir le terme « meilleures ».

Ceci est particulièrement vrai avec la version de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013. Outre les fonctionnalités telles que la messagerie unifiée et la messagerie instantanée et la présence, qui se trouvent dans Microsoft Exchange Server 2010 et Microsoft Lync Server 2010, les publications 2013 des produits serveur incluent un certain nombre de nouvelles fonctionnalités. Ces fonctionnalités incluent les éléments suivants :

  - **Intégration de l’archivage Lync**. Dans les administrateurs de Lync Server 2013, vous avez toujours la possibilité d’archiver les transcriptions de messagerie instantanée et de conférence Web sur SQL Server (de la même façon que ces transcriptions ont été archivées dans Lync Server 2010). En revanche, les administrateurs peuvent choisir d’archiver les transcriptions dans Exchange 2013, en stockant ces transcriptions dans les boîtes aux lettres individuelles de l’utilisateur de la même manière qu’Exchange Archive les communications. Il s’agit d’un référentiel unique pour toutes vos communications électroniques (Exchange et Lync Server), ce qui facilite la recherche et la récupération des communications archivées en cas de besoin.

  - **Magasin de contacts unifié** Dans Lync Server 2010, les utilisateurs doivent tenir à jour des listes de contacts distinctes dans Outlook et Lync. pour vous assurer que les mêmes contacts étaient disponibles dans les deux produits, vous devez tenir à jour des listes de contacts en double, une pour Outlook et une pour Lync. Toutefois, avec Lync Server 2013, les contacts des utilisateurs peuvent être stockés dans Exchange 2013 et dans le magasin de contacts unifié. L’utilisation d’un seul magasin de contacts permet aux utilisateurs de conserver un seul ensemble de contacts, avec ce même ensemble de contacts disponible dans Lync 2013, Outlook 2013 et Outlook Web Access 2013.

  - **Planification de réunions Lync à partir d’OWA**. Grâce à l’intégration de Lync Server 2013 et Exchange 2013, les utilisateurs peuvent planifier des réunions Lync à partir d’Outlook Web Access 2013.

  - **Photos haute résolution**. Lync 2010 ne peut pas afficher de petites photos de vos contacts. Cela est dû au fait que ces photos étaient stockées dans Active Directory et qu’Active Directory impose une limitation de 48 pixels par 48 en taille de pixel sur les photos stockées. Toutefois, avec Lync Server 2013, les photos peuvent être stockées dans Microsoft Exchange. Cela permet de disposer de photos haute résolution de plus de 648 pixels par 648 pixels. Comme vous pouvez le constater, Lync 2013 a été mis à jour de manière à autoriser l’affichage de ces photographies haute résolution.

Gardez à l’esprit que ces nouvelles fonctionnalités nécessitent l’utilisation de Lync Server 2013 et Exchange 2013. De plus, les utilisateurs qui espèrent tirer pleinement parti de ces nouvelles fonctionnalités doivent disposer de comptes sur Lync Server 2013 et Exchange 2013 et utiliser les versions les plus récentes du logiciel client (par exemple, Lync 2013). Par exemple, le magasin de contacts unifié n’est pas disponible pour les utilisateurs qui ont été hébergés sur Lync Server 2010. de même, les photos de haute résolution ne peuvent pas être affichées dans Lync 2010.

Cette documentation fournit des informations sur l’intégration de Lync Server 2013 et Exchange 2013. incluant des informations détaillées sur l’activation de nouvelles fonctionnalités telles que l’intégration de l’archivage et le magasin de contacts unifié. Ce document ne décrit pas la configuration initiale et la configuration de ces deux produits. Pour plus d’informations sur le déploiement de Lync Server 2013, voir le centre de [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)technologie de lync Server 2013. Pour plus d’informations sur le déploiement d’Exchange 2013, consultez le centre [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)de technologie Exchange 2013 à l’adresse.

<div>

## <a name="in-this-section"></a>Dans cette section

[Conditions préalables à l’intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configuration de Microsoft Lync Server 2013 pour l’utilisation de l’archivage Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configuration de Microsoft SharePoint Server 2013 pour rechercher des données Microsoft Lync Server 2013 archivées](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configuration de Microsoft Lync Server 2013 pour utiliser le magasin de contacts unifié](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour Microsoft Lync Server 2013 la messagerie vocale](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Intégration de Microsoft Lync Server 2013 et Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

