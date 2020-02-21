---
title: Configuration des stratégies d’archivage lors de l’utilisation de l’intégration d’Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44716284313f9b23bb0bceb8485637ed67bda5fc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="a7bb5-102">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a7bb5-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7bb5-103">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a7bb5-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a7bb5-104">Si les utilisateurs hébergés sur Exchange 2013 ont leurs boîtes aux lettres placées en conservation inaltérable, les stratégies de conservation inaltérable d’Exchange contrôlent l’archivage pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a7bb5-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="a7bb5-105">Si vous utilisez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange 2013 remplacent les stratégies d’archivage de Lync Server pour les utilisateurs hébergés sur Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a7bb5-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="a7bb5-106">Pour plus d’informations sur la configuration des stratégies d’archivage Exchange, voir la documentation Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a7bb5-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="a7bb5-107">Pour plus d’informations sur la configuration des stratégies utilisateur pour les utilisateurs hébergés sur Lync Server 2013, voir [Configuration des stratégies utilisateur pour l’archivage dans Lync server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a7bb5-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="a7bb5-108">Pour plus d’informations sur le fonctionnement des stratégies, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="a7bb5-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a7bb5-109">Si vous déployez Exchange 2013 et Lync Server 2013 dans la même forêt, vos stratégies de conservation inaltérable Exchange 2013 contrôlent l’archivage.</span><span class="sxs-lookup"><span data-stu-id="a7bb5-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="a7bb5-110">Si vous déployez Exchange 2013 et Lync Server 2013 dans des forêts distinctes, reportez-vous à la section « déploiement de Lync Server et de Microsoft Exchange dans différentes forêts » dans <A href="lync-server-2013-deployment-checklist-for-archiving.md">liste de vérification du déploiement pour l’archivage dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a7bb5-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

