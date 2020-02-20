---
title: 'Lync Server 2013 : prise en charge de l’intégration d’Exchange et de SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdfaffa12d84b57f0ae0203ebc14491bb6d8d4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Prise en charge de l’intégration d’Exchange et de SharePoint dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-01-18_

Lync Server 2013 et Lync 2013 peuvent communiquer en toute sécurité avec d’autres applications et produits serveur, notamment Office 2013, Exchange Server 2013, Exchange Server 2016 et SharePoint, si vous intégrez ces produits. L’intégration de Lync Server 2013 et d’Office offre aux utilisateurs un accès en contexte aux fonctionnalités de messagerie instantanée, de présence améliorée, de téléphonie et de conférence de Lync. Les utilisateurs d’Office peuvent accéder aux fonctionnalités Lync à partir du client de messagerie et de collaboration Outlook 2013, ainsi que d’autres programmes Office ou d’une page SharePoint. Les utilisateurs peuvent également afficher un enregistrement des conversations Lync dans le dossier historique des conversations d’Outlook. Lorsqu’il est intégré à Exchange 2013, Exchange 2016 ou Exchange Online, Lync Server 2013 prend également en charge les éléments suivants :

  - Magasin de contacts unifié, qui permet aux utilisateurs de stocker toutes les informations de contact dans Exchange ou Exchange Online afin que les informations soient disponibles globalement dans Lync 2013, Exchange, Outlook et Outlook Web App.

  - Historique des conversations et historique des conférences Web, qui est stocké dans les dossiers utilisateur Exchange.

  - Le contenu archivé de Lync, comme la messagerie instantanée et le contenu de la réunion, peut être stocké dans le stockage Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 prend en charge l’intégration avec les versions précédentes de Microsoft Exchange Server et SharePoint Server, mais toutes les fonctionnalités ne sont pas prises en charge avec ces versions antérieures, telles que l’intégration du stockage d’archivage avec Microsoft Exchange.<BR>Si vous migrez vos utilisateurs vers Exchange 2013 ou Exchange 2016, vous pouvez utiliser à la fois le stockage Exchange et le stockage Lync Server de façon temporaire, tout en terminant la migration. L’utilisation permanente de Exchange et du stockage Lync Server n’est pas prise en charge.



</div>

L’intégration de Lync Server 2013 avec Exchange Server et SharePoint Server nécessite une authentification de serveur à serveur entre des serveurs exécutant Lync Server 2013, Exchange Server et SharePoint Server. Lync Server 2013 prend en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Pour une authentification de serveur à serveur locale entre deux serveurs Microsoft, il n’est pas nécessaire d’utiliser un serveur de jetons tiers. Lync Server 2013, Exchange Server et SharePoint Server possèdent un serveur de jetons intégré qui peut être utilisé à des fins d’authentification. Par exemple, Lync Server 2013 peut émettre et signer un jeton de sécurité lui-même, puis utiliser ce jeton lors de la communication avec Exchange. Le cas échéant, il n’est pas nécessaire d’utiliser un serveur de jetons tiers.

Lync Server 2013 prend en charge les deux scénarios d’authentification de serveur à serveur. Ceux-ci impliquent la configuration de l’authentification de serveur à serveur entre :

  - Une installation locale de Lync Server 2013 et une installation locale d’Exchange Server 2013, Exchange Server 2016 et/ou SharePoint Server.

  - Une paire de composants Office (par exemple, entre Microsoft Exchange 365 et Microsoft Lync Server 365, ou entre Microsoft Lync Server 365 et Microsoft SharePoint 365).

<div>


> [!NOTE]  
> L’authentification de serveur à serveur entre un serveur local et un composant Office 365 n’est pas prise en charge dans cette version de Lync Server 2013. Cela signifie, entre autres, que vous ne pouvez pas configurer l’authentification de serveur à serveur entre une installation locale de Lync Server 2013 et de Microsoft Exchange 365.



</div>

Pour plus d’informations sur l’authentification de serveur à serveur, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou dans la documentation des opérations.

</div>

<span> </span>

</div>

</div>

</div>

