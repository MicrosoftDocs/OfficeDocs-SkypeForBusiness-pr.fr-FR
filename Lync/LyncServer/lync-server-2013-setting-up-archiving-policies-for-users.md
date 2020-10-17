---
title: 'Lync Server 2013 : configuration des stratégies d’archivage pour les utilisateurs'
description: 'Lync Server 2013 : configuration des stratégies d’archivage pour les utilisateurs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c18a15c1a0611f49a6fd9a4983f3ce87104332e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559520"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="a486a-103">Configuration des stratégies d’archivage pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a486a-103">Setting up Archiving policies for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a486a-104">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a486a-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a486a-105">Vous pouvez activer ou désactiver l’archivage pour des utilisateurs spécifiques en créant et en configurant une stratégie d’archivage pour les utilisateurs, puis en appliquant la stratégie à des utilisateurs spécifiques ou à des groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a486a-105">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="a486a-106">Les stratégies utilisateur remplacent les stratégies globales ou de site.</span><span class="sxs-lookup"><span data-stu-id="a486a-106">User policies override any global policy or site policies.</span></span> <span data-ttu-id="a486a-107">Les stratégies d’archivage ne s’appliquent que si vous n’utilisez pas l’intégration de Microsoft Exchange ou, si vous utilisez l’intégration de Microsoft Exchange, mais que certains utilisateurs ne sont pas hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place.</span><span class="sxs-lookup"><span data-stu-id="a486a-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="a486a-108">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works dans Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation ou Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="a486a-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a486a-109">Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de blocage Exchange In-Place déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place.</span><span class="sxs-lookup"><span data-stu-id="a486a-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a486a-110">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a486a-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="a486a-111">Vous devez spécifier toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="a486a-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="a486a-112">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a486a-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a486a-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a486a-113">In This Section</span></span>

  - [<span data-ttu-id="a486a-114">Configuration des stratégies utilisateur pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a486a-114">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="a486a-115">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a486a-115">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

