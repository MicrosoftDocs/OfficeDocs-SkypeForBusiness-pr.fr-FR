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
ms.openlocfilehash: 917ffc5103617c04a989ec91043a68fcce9f0320
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498521"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="b576c-102">Intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="b576c-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b576c-103">_**Dernière modification de la rubrique :** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="b576c-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="b576c-104">Exchange et Lync Server ont un long historique d’intégration et de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="b576c-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="b576c-105">Cette intégration se remarque le plus dans leur application cliente respective.</span><span class="sxs-lookup"><span data-stu-id="b576c-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="b576c-106">Par exemple, les informations de présence de Lync peuvent être consignées dans Microsoft Outlook ; de même, Lync peut utiliser le calendrier Outlook pour mettre à jour automatiquement les informations de présence.</span><span class="sxs-lookup"><span data-stu-id="b576c-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="b576c-107">(Par exemple, Lync peut modifier votre statut pour qu’il soit occupé chaque fois que votre calendrier indique que vous avez une réunion planifiée.) Même si vous n’avez pas besoin d’exécuter Exchange pour exécuter Lync Server (ou inversement), il n’y a pas de doute que l’utilisation conjointe des deux produits epitomizes la définition du terme « collaboration ».</span><span class="sxs-lookup"><span data-stu-id="b576c-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="b576c-108">Cela est particulièrement vrai avec la version de Microsoft Lync Server 2013 et de Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b576c-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="b576c-109">En plus des fonctionnalités, telles que la messagerie unifiée et la messagerie instantanée et la présence, qui sont disponibles dans Microsoft Exchange Server 2010 et Microsoft Lync Server 2010, les versions 2013 des produits serveur incluent un certain nombre de nouvelles fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="b576c-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="b576c-110">Ces dernières incluent notamment les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b576c-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="b576c-111">**Intégration de l’archivage Lync**.</span><span class="sxs-lookup"><span data-stu-id="b576c-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="b576c-112">Dans Lync Server 2013, les administrateurs ont toujours la possibilité d’archiver les transcriptions de messagerie instantanée et de conférence Web dans SQL Server (de la même manière que ces transcriptions ont été archivées dans Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="b576c-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="b576c-113">Toutefois, les administrateurs peuvent choisir d’archiver les transcriptions dans Exchange 2013, en les stockant dans les boîtes aux lettres des utilisateurs individuels de la même manière qu’Exchange Archive les communications.</span><span class="sxs-lookup"><span data-stu-id="b576c-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="b576c-114">Cela signifie qu’un seul référentiel pour toutes vos communications électroniques (à la fois Exchange et Lync Server), ce qui facilite grandement la recherche et la récupération de ces communications archivées en cas de besoin.</span><span class="sxs-lookup"><span data-stu-id="b576c-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="b576c-115">**Magasin de contacts unifié**.</span><span class="sxs-lookup"><span data-stu-id="b576c-115">**Unified Contact Store**.</span></span> <span data-ttu-id="b576c-116">Dans Lync Server 2010, les utilisateurs devaient gérer des listes de contacts distinctes dans Outlook et Lync ; en fait, pour vous assurer que les mêmes contacts sont disponibles dans les deux produits, vous deviez gérer les listes de contacts en double, une pour Outlook et une pour Lync.</span><span class="sxs-lookup"><span data-stu-id="b576c-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="b576c-117">Toutefois, avec Lync Server 2013, les contacts utilisateur peuvent être stockés dans Exchange 2013 et dans le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="b576c-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="b576c-118">L’utilisation d’un seul magasin de contacts permet aux utilisateurs de ne conserver qu’un seul ensemble de contacts, ce même ensemble de contacts étant disponible dans Lync 2013, Outlook 2013 et Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="b576c-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="b576c-119">**Planification de réunion Lync à partir d’OWA**.</span><span class="sxs-lookup"><span data-stu-id="b576c-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="b576c-120">Avec Lync Server 2013 et l’intégration d’Exchange 2013, les utilisateurs peuvent planifier des réunions Lync à partir d’Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="b576c-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="b576c-121">**Photos haute résolution**.</span><span class="sxs-lookup"><span data-stu-id="b576c-121">**High resolution photos**.</span></span> <span data-ttu-id="b576c-122">Lync 2010 ne peut afficher que les petites photos de vos contacts ; Cela est dû au fait que ces photos ont été stockées dans Active Directory et qu’Active Directory impose une limite de taille de 48 pixel par 48 pixels sur les photos stockées.</span><span class="sxs-lookup"><span data-stu-id="b576c-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="b576c-123">Toutefois, avec Lync Server 2013, les photos peuvent être stockées dans Microsoft Exchange ; Cela permet de créer des photos à haute résolution de 648 pixels par 648 pixels.</span><span class="sxs-lookup"><span data-stu-id="b576c-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="b576c-124">Comme vous pouvez vous y attendre, Lync 2013 a été mis à niveau pour permettre l’affichage de ces photographies à haute résolution.</span><span class="sxs-lookup"><span data-stu-id="b576c-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="b576c-125">N’oubliez pas que ces nouvelles fonctionnalités requièrent l’utilisation de Lync Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b576c-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="b576c-126">En outre, les utilisateurs qui espèrent tirer pleinement parti de ces nouvelles fonctionnalités doivent disposer de comptes sur Lync Server 2013 et Exchange 2013, et doivent utiliser les versions les plus récentes du logiciel client (par exemple, Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="b576c-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="b576c-127">Par exemple, le magasin de contacts unifié n’est pas disponible pour les utilisateurs qui ont été hébergés sur Lync Server 2010 ; de même, les photos haute résolution ne peuvent pas être affichées dans Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="b576c-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="b576c-128">Cette documentation fournit des informations sur l’intégration de Lync Server 2013 et d’Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b576c-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="b576c-129">y compris des informations détaillées sur l’activation de nouvelles fonctionnalités, telles que l’intégration de l’archivage et le magasin de contacts unifié.</span><span class="sxs-lookup"><span data-stu-id="b576c-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="b576c-130">Cette documentation ne fait pas la configuration initiale et la configuration de ces deux produits.</span><span class="sxs-lookup"><span data-stu-id="b576c-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="b576c-131">Pour plus d’informations sur le déploiement de Lync Server 2013, voir Lync Server 2013 Tech Center à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) .</span><span class="sxs-lookup"><span data-stu-id="b576c-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="b576c-132">Pour plus d’informations sur le déploiement d’Exchange 2013, consultez le site Exchange 2013 Tech Center à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .</span><span class="sxs-lookup"><span data-stu-id="b576c-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b576c-133">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b576c-133">In This Section</span></span>

[<span data-ttu-id="b576c-134">Conditions préalables à l’intégration de Microsoft Lync Server 2013 et de Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="b576c-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="b576c-135">Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="b576c-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="b576c-136">Configuration de Microsoft Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="b576c-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="b576c-137">Configuration de Microsoft SharePoint Server 2013 pour rechercher des données archivées Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b576c-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="b576c-138">Configuration de Microsoft Lync Server 2013 pour utiliser le magasin de contacts unifié</span><span class="sxs-lookup"><span data-stu-id="b576c-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="b576c-139">Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b576c-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="b576c-140">Configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour Microsoft Lync Server 2013 Voice Mail</span><span class="sxs-lookup"><span data-stu-id="b576c-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="b576c-141">Intégration de Microsoft Lync Server 2013 et de Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="b576c-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

