---
title: 'Lync Server 2013: prise en charge de l’intégration d’Exchange et de SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4d378337643adf79557bd4bbb649a01948de27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Prise en charge de l’intégration d’Exchange et de SharePoint dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-01-18_

Lync Server 2013 et Lync 2013 peuvent communiquer en toute sécurité avec d’autres applications et produits serveur, y compris Office 2013, Exchange Server 2013, Exchange Server 2016 et SharePoint, si vous intégrez ces produits. L’intégration de Lync Server 2013 et d’Office offre aux utilisateurs un accès in-context aux fonctionnalités de messagerie instantanée, de présence et de conférence de Lync. Les utilisateurs d’Office peuvent accéder aux fonctionnalités de Lync à partir du client de messagerie et de collaboration Outlook 2013 et d’autres programmes Office ou à partir d’une page SharePoint. Les utilisateurs peuvent également afficher un enregistrement des conversations Lync dans le dossier historique des conversations Outlook. Lorsqu’il est intégré à Exchange 2013, Exchange 2016 ou Exchange Online, Lync Server 2013 prend également en charge les éléments suivants:

  - Magasin de contacts unifié, qui permet aux utilisateurs de stocker toutes les informations de contact dans Exchange ou Exchange Online de sorte que les informations soient disponibles dans le monde entier via Lync 2013, Exchange, Outlook et Outlook Web App.

  - Historique des conversations et historique des conférences Web, qui est stocké dans les dossiers utilisateurs Exchange.

  - Le contenu archivé de Lync, tel que la messagerie instantanée et le contenu de la réunion, peut être stocké dans le stockage Exchange.

<div>


> [!NOTE]  
> Lync Server 2013 prend en charge l’intégration avec les versions précédentes de Microsoft Exchange Server et SharePoint Server, mais toutes les fonctionnalités ne sont pas prises en charge avec ces versions précédentes, telles que l’intégration de stockage de stockage avec Microsoft Exchange.<BR>Si vous migrez vos utilisateurs vers Exchange 2013 ou Exchange 2016, vous pouvez utiliser à la fois le stockage Exchange et le stockage du serveur Lync de manière temporaire, lors de la migration. L’utilisation permanente de Exchange et du stockage serveur Lync n’est pas prise en charge.



</div>

L’intégration de Lync Server 2013 à Exchange Server et SharePoint Server nécessite une authentification de serveur à serveur entre les serveurs exécutant Lync Server 2013, Exchange Server et SharePoint Server. Lync Server 2013 prend en charge le protocole OAuth (autorisation d’ouverture) pour l’authentification et l’autorisation de serveur à serveur. Dans le cas d’une authentification serveur à serveur locale entre deux serveurs Microsoft, il est inutile d’utiliser un serveur Token tiers. Lync Server 2013, Exchange Server et SharePoint Server disposent d’un serveur à jetons intégré qui peut être utilisé à des fins d’authentification. Par exemple, Lync Server 2013 peut émettre et signer un jeton de sécurité en soi et utiliser ce jeton lors de la communication avec Exchange. Dans le cas présent, il est inutile d’utiliser un serveur jeton tiers.

Lync Server 2013 prend en charge les deux scénarios d’authentification de serveur à serveur. Il s’agit notamment de la configuration de l’authentification de serveur à serveur entre les éléments suivants:

  - Une installation locale de Lync Server 2013 et une installation locale d’Exchange Server 2013, Exchange Server 2016 et/ou SharePoint Server.

  - Deux composants Office (par exemple, entre Microsoft Exchange 365 et Microsoft Lync Server 365 ou entre Microsoft Lync Server 365 et Microsoft SharePoint 365).

<div>


> [!NOTE]  
> L’authentification de serveur à serveur entre un serveur local et un composant Office 365 n’est pas prise en charge dans cette version de Lync Server 2013. Entre autres choses, cela signifie que vous ne pouvez pas configurer l’authentification de serveur à serveur entre une installation locale de Lync Server 2013 et Microsoft Exchange 365.



</div>

Pour plus d’informations sur l’authentification de serveur à serveur, voir [gestion des applications d’authentification de serveur à serveur (OAuth) et partenaires dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou les opérations.

</div>

<span> </span>

</div>

</div>

</div>

