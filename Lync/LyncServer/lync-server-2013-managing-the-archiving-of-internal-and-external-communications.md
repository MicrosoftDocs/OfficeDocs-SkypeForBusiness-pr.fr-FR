---
title: Gestion de l’archivage des communications internes et externes
description: Gestion de l’archivage des communications internes et externes.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857e4772d93ead01c3914b2ee04b71bddb1feed4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564130"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="21f38-103">Gestion de l’archivage des communications internes et externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21f38-103">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21f38-104">_**Dernière modification de la rubrique :** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="21f38-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="21f38-105">Dans Lync Server 2013, vous utilisez des stratégies d’archivage pour activer et désactiver l’archivage des communications internes et des communications externes si vous n’utilisez pas l’intégration de Microsoft Exchange ou si vous avez des utilisateurs qui ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées en conservation In-Place.</span><span class="sxs-lookup"><span data-stu-id="21f38-105">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="21f38-106">Il s’agit notamment des stratégies d’archivage suivantes :</span><span class="sxs-lookup"><span data-stu-id="21f38-106">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="21f38-107">Stratégie globale créée par défaut lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21f38-107">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="21f38-108">Stratégies facultatives au niveau site et utilisateur que vous pouvez créer et utiliser pour définir de quelle manière l’archivage est implémenté pour des sites ou utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="21f38-108">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="21f38-109">Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="21f38-109">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="21f38-110">Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page **stratégie d’archivage** du groupe **archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21f38-110">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="21f38-111">Si vous intégrez votre stockage Lync Server au stockage Exchange 2013, les stratégies d’utilisateur Exchange prévalent sur les stratégies d’archivage Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21f38-111">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="21f38-112">Pour plus d’informations sur l’implémentation des stratégies, y compris la hiérarchie des stratégies, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="21f38-112">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="21f38-113">Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options de configuration de l’archivage, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage.</span><span class="sxs-lookup"><span data-stu-id="21f38-113">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="21f38-114">Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="21f38-114">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="21f38-115">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="21f38-115">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="21f38-116">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for Your Organization, sites, and pools</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="21f38-116">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="21f38-117">Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place.</span><span class="sxs-lookup"><span data-stu-id="21f38-117">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="21f38-118">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="21f38-118">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="21f38-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="21f38-119">In This Section</span></span>

  - [<span data-ttu-id="21f38-120">Création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="21f38-120">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="21f38-121">Modification d’une stratégie d’archivage dans Lync Server 2013 afin d’activer ou de désactiver l’archivage des communications internes ou externes pour votre organisation, vos sites ou vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="21f38-121">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="21f38-122">Application d’une stratégie d’archivage aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21f38-122">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="21f38-123">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</span><span class="sxs-lookup"><span data-stu-id="21f38-123">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="21f38-124">Suppression d’une stratégie d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21f38-124">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

