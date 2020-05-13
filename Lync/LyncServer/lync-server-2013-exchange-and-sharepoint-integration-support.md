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
ms.openlocfilehash: 262e31ac6049920ca4e327f50dccaae18d69a2f5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="37ec4-102">Prise en charge de l’intégration d’Exchange et de SharePoint dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37ec4-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37ec4-103">_**Dernière modification de la rubrique :** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="37ec4-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="37ec4-104">Lync Server 2013 et Lync 2013 peuvent communiquer en toute sécurité avec d’autres applications et produits serveur, notamment Office 2013, Exchange Server 2013, Exchange Server 2016 et SharePoint, si vous intégrez ces produits.</span><span class="sxs-lookup"><span data-stu-id="37ec4-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="37ec4-105">L’intégration de Lync Server 2013 et d’Office offre aux utilisateurs un accès en contexte aux fonctionnalités de messagerie instantanée, de présence améliorée, de téléphonie et de conférence de Lync.</span><span class="sxs-lookup"><span data-stu-id="37ec4-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="37ec4-106">Les utilisateurs d’Office peuvent accéder aux fonctionnalités Lync à partir du client de messagerie et de collaboration Outlook 2013, ainsi que d’autres programmes Office ou d’une page SharePoint.</span><span class="sxs-lookup"><span data-stu-id="37ec4-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="37ec4-107">Les utilisateurs peuvent également afficher un enregistrement des conversations Lync dans le dossier historique des conversations d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="37ec4-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="37ec4-108">Lorsqu’il est intégré à Exchange 2013, Exchange 2016 ou Exchange Online, Lync Server 2013 prend également en charge les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="37ec4-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="37ec4-109">Magasin de contacts unifié, qui permet aux utilisateurs de stocker toutes les informations de contact dans Exchange ou Exchange Online afin que les informations soient disponibles globalement dans Lync 2013, Exchange, Outlook et Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="37ec4-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="37ec4-110">Historique des conversations et historique des conférences Web, qui est stocké dans les dossiers utilisateur Exchange.</span><span class="sxs-lookup"><span data-stu-id="37ec4-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="37ec4-111">Le contenu archivé de Lync, comme la messagerie instantanée et le contenu de la réunion, peut être stocké dans le stockage Exchange.</span><span class="sxs-lookup"><span data-stu-id="37ec4-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37ec4-112">Lync Server 2013 prend en charge l’intégration avec les versions précédentes de Microsoft Exchange Server et SharePoint Server, mais toutes les fonctionnalités ne sont pas prises en charge avec ces versions antérieures, telles que l’intégration du stockage d’archivage avec Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="37ec4-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="37ec4-113">Si vous migrez vos utilisateurs vers Exchange 2013 ou Exchange 2016, vous pouvez utiliser à la fois le stockage Exchange et le stockage Lync Server de façon temporaire, tout en terminant la migration.</span><span class="sxs-lookup"><span data-stu-id="37ec4-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="37ec4-114">L’utilisation permanente de Exchange et du stockage Lync Server n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="37ec4-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="37ec4-115">L’intégration de Lync Server 2013 avec Exchange Server et SharePoint Server nécessite une authentification de serveur à serveur entre des serveurs exécutant Lync Server 2013, Exchange Server et SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="37ec4-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="37ec4-116">Lync Server 2013 prend en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="37ec4-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="37ec4-117">Pour une authentification de serveur à serveur locale entre deux serveurs Microsoft, il n’est pas nécessaire d’utiliser un serveur de jetons tiers.</span><span class="sxs-lookup"><span data-stu-id="37ec4-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="37ec4-118">Lync Server 2013, Exchange Server et SharePoint Server possèdent un serveur de jetons intégré qui peut être utilisé à des fins d’authentification.</span><span class="sxs-lookup"><span data-stu-id="37ec4-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="37ec4-119">Par exemple, Lync Server 2013 peut émettre et signer un jeton de sécurité lui-même, puis utiliser ce jeton lors de la communication avec Exchange.</span><span class="sxs-lookup"><span data-stu-id="37ec4-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="37ec4-120">Le cas échéant, il n’est pas nécessaire d’utiliser un serveur de jetons tiers.</span><span class="sxs-lookup"><span data-stu-id="37ec4-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="37ec4-121">Lync Server 2013 prend en charge les deux scénarios d’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="37ec4-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="37ec4-122">Ceux-ci impliquent la configuration de l’authentification de serveur à serveur entre :</span><span class="sxs-lookup"><span data-stu-id="37ec4-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="37ec4-123">Une installation locale de Lync Server 2013 et une installation locale d’Exchange Server 2013, Exchange Server 2016 et/ou SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="37ec4-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="37ec4-124">Une paire de composants Office (par exemple, entre Microsoft Exchange 365 et Microsoft Lync Server 365, ou entre Microsoft Lync Server 365 et Microsoft SharePoint 365).</span><span class="sxs-lookup"><span data-stu-id="37ec4-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37ec4-125">L’authentification de serveur à serveur entre un serveur local et un composant Microsoft 365 ou Office 365 n’est pas prise en charge dans cette version Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37ec4-125">Server-to-server authentication between an on-premises server and a Microsoft 365 or Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="37ec4-126">Cela signifie, entre autres, que vous ne pouvez pas configurer l’authentification de serveur à serveur entre une installation locale de Lync Server 2013 et de Microsoft Exchange 365.</span><span class="sxs-lookup"><span data-stu-id="37ec4-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="37ec4-127">Pour plus d’informations sur l’authentification de serveur à serveur, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="37ec4-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>
