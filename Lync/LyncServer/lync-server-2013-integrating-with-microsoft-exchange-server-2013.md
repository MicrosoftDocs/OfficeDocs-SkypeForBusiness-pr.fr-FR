---
title: 'Lync Server 2013 : intégration à Microsoft Exchange Server 2013'
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
ms.openlocfilehash: c1c60768311f4fbf832f3dbe2ac4a0c2e8e55298
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-09_

Exchange et Lync Server ont un long historique d’intégration et de compatibilité. Cette intégration se remarque le plus dans leur application cliente respective. Par exemple, les informations de présence de Lync peuvent être consignées dans Microsoft Outlook ; de même, Lync peut utiliser le calendrier Outlook pour mettre à jour automatiquement les informations de présence. (Par exemple, Lync peut modifier votre statut pour qu’il soit occupé chaque fois que votre calendrier indique que vous avez une réunion planifiée.) Même si vous n’avez pas besoin d’exécuter Exchange pour exécuter Lync Server (ou inversement), il n’y a pas de doute que l’utilisation conjointe des deux produits epitomizes la définition du terme « collaboration ».

Cela est particulièrement vrai avec la version de Microsoft Lync Server 2013 et de Microsoft Exchange Server 2013. En plus des fonctionnalités, telles que la messagerie unifiée et la messagerie instantanée et la présence, qui sont disponibles dans Microsoft Exchange Server 2010 et Microsoft Lync Server 2010, les versions 2013 des produits serveur incluent un certain nombre de nouvelles fonctionnalités. Ces dernières incluent notamment les suivantes :

  - **Intégration de l’archivage Lync**. Dans Lync Server 2013, les administrateurs ont toujours la possibilité d’archiver les transcriptions de messagerie instantanée et de conférence Web dans SQL Server (de la même manière que ces transcriptions ont été archivées dans Lync Server 2010). Toutefois, les administrateurs peuvent choisir d’archiver les transcriptions dans Exchange 2013, en les stockant dans les boîtes aux lettres des utilisateurs individuels de la même manière qu’Exchange Archive les communications. Cela signifie qu’un seul référentiel pour toutes vos communications électroniques (à la fois Exchange et Lync Server), ce qui facilite grandement la recherche et la récupération de ces communications archivées en cas de besoin.

  - **Magasin de contacts unifié**. Dans Lync Server 2010, les utilisateurs devaient gérer des listes de contacts distinctes dans Outlook et Lync ; en fait, pour vous assurer que les mêmes contacts sont disponibles dans les deux produits, vous deviez gérer les listes de contacts en double, une pour Outlook et une pour Lync. Toutefois, avec Lync Server 2013, les contacts utilisateur peuvent être stockés dans Exchange 2013 et dans le magasin de contacts unifié. L’utilisation d’un seul magasin de contacts permet aux utilisateurs de ne conserver qu’un seul ensemble de contacts, ce même ensemble de contacts étant disponible dans Lync 2013, Outlook 2013 et Outlook Web Access 2013.

  - **Planification de réunion Lync à partir d’OWA**. Avec Lync Server 2013 et l’intégration d’Exchange 2013, les utilisateurs peuvent planifier des réunions Lync à partir d’Outlook Web Access 2013.

  - **Photos haute résolution**. Lync 2010 ne peut afficher que les petites photos de vos contacts ; Cela est dû au fait que ces photos ont été stockées dans Active Directory et qu’Active Directory impose une limite de taille de 48 pixel par 48 pixels sur les photos stockées. Toutefois, avec Lync Server 2013, les photos peuvent être stockées dans Microsoft Exchange ; Cela permet de créer des photos à haute résolution de 648 pixels par 648 pixels. Comme vous pouvez vous y attendre, Lync 2013 a été mis à niveau pour permettre l’affichage de ces photographies à haute résolution.

N’oubliez pas que ces nouvelles fonctionnalités requièrent l’utilisation de Lync Server 2013 et Exchange 2013. En outre, les utilisateurs qui espèrent tirer pleinement parti de ces nouvelles fonctionnalités doivent disposer de comptes sur Lync Server 2013 et Exchange 2013, et doivent utiliser les versions les plus récentes du logiciel client (par exemple, Lync 2013). Par exemple, le magasin de contacts unifié n’est pas disponible pour les utilisateurs qui ont été hébergés sur Lync Server 2010 ; de même, les photos haute résolution ne peuvent pas être affichées dans Lync 2010.

Cette documentation fournit des informations sur l’intégration de Lync Server 2013 et d’Exchange 2013. y compris des informations détaillées sur l’activation de nouvelles fonctionnalités, telles que l’intégration de l’archivage et le magasin de contacts unifié. Cette documentation ne fait pas la configuration initiale et la configuration de ces deux produits. Pour plus d’informations sur le déploiement de Lync Server 2013, voir Lync Server 2013 [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)Tech Center à l’adresse. Pour plus d’informations sur le déploiement d’Exchange 2013, consultez le site [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)Exchange 2013 Tech Center à l’adresse.

<div>

## <a name="in-this-section"></a>Dans cette section

[Conditions préalables à l’intégration de Microsoft Lync Server 2013 et de Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configuration de Microsoft Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configuration de Microsoft SharePoint Server 2013 pour rechercher des données archivées Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configuration de Microsoft Lync Server 2013 pour utiliser le magasin de contacts unifié](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour Microsoft Lync Server 2013 Voice Mail](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Intégration de Microsoft Lync Server 2013 et de Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

