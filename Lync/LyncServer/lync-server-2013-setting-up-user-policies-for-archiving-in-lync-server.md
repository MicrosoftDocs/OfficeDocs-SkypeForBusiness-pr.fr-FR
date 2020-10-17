---
title: 'Lync Server 2013 : configuration des stratégies utilisateur pour l’archivage dans Lync Server'
description: 'Lync Server 2013 : configuration des stratégies utilisateur pour l’archivage dans Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e33abf6cf16c9c1367162aa8beee91874f4c725
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554080"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="36482-103">Configuration des stratégies utilisateur pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36482-103">Setting up user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36482-104">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="36482-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="36482-105">L’activation ou la désactivation de l’archivage pour des utilisateurs spécifiques hébergés sur Lync Server 2013 nécessite la création et la configuration de stratégies utilisateur, puis l’application de la stratégie appropriée à des utilisateurs ou groupes d’utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="36482-105">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="36482-106">Les stratégies utilisateur remplacent les stratégies de site et les stratégies globales, mais uniquement pour les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36482-106">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="36482-107">Les utilisateurs sont toujours hébergés dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36482-107">Users are always homed in Lync Server.</span></span> <span data-ttu-id="36482-108">Si l’intégration de Microsoft Exchange est activée, les utilisateurs dont les boîtes aux lettres sont dans Microsoft Exchange Server 2013 n’ont pas besoin de gérer les stratégies d’archivage dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36482-108">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="36482-109">Ces utilisateurs disposant d’un archivage seront gérés par Exchange In-Place conservation.</span><span class="sxs-lookup"><span data-stu-id="36482-109">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="36482-110">Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="36482-110">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36482-111">Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de blocage Exchange In-Place contrôlent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="36482-111">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="36482-112">Pour ces utilisateurs, la fonctionnalité d’archivage nécessite que leurs boîtes aux lettres soient placées dans une archive permanente.</span><span class="sxs-lookup"><span data-stu-id="36482-112">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="36482-113">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="36482-113">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="36482-114">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage.</span><span class="sxs-lookup"><span data-stu-id="36482-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="36482-115">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="36482-115">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36482-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="36482-116">In This Section</span></span>

  - [<span data-ttu-id="36482-117">Création et configuration de stratégies utilisateur pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36482-117">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="36482-118">Application d’une stratégie d’archivage Lync Server à un utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36482-118">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

