---
title: Gestion de l’archivage des communications internes et externes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a9e3c0a0708075eecc28282021f98724325ff6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="85ee4-102">Gestion de l’archivage des communications internes et externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ee4-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ee4-103">_**Dernière modification de la rubrique:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="85ee4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="85ee4-104">Dans Lync Server 2013, vous utilisez les stratégies d’archivage pour activer et désactiver l’archivage des communications internes et des communications externes si vous n’utilisez pas l’intégration de Microsoft Exchange ou si vous avez des utilisateurs qui ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées sur Blocage sur place.</span><span class="sxs-lookup"><span data-stu-id="85ee4-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="85ee4-105">Cela inclut les stratégies d’archivage suivantes:</span><span class="sxs-lookup"><span data-stu-id="85ee4-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="85ee4-106">Stratégie globale créée par défaut lors du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85ee4-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="85ee4-107">Stratégies de niveau de site et de niveau utilisateur facultatives que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="85ee4-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="85ee4-108">Vous définissez initialement des stratégies d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des stratégies après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="85ee4-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="85ee4-109">Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la page de **stratégie** d’archivage du groupe **archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="85ee4-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="85ee4-110">Si vous intégrez le stockage de votre serveur Lync au stockage 2013 Exchange, les stratégies d’utilisateur Exchange sont prioritaires sur les stratégies d’archivage de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85ee4-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="85ee4-111">Pour plus d’informations sur l’implémentation de stratégies, y compris la hiérarchie des stratégies, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.</span><span class="sxs-lookup"><span data-stu-id="85ee4-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="85ee4-112">Pour contrôler l’implémentation de l’archivage, vous devez spécifier les options de configuration de l’archivage, par exemple pour archiver les messages instantanés ou les conférences, utiliser le mode Critical et les options de purge.</span><span class="sxs-lookup"><span data-stu-id="85ee4-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="85ee4-113">Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans toute configuration d’archivage de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="85ee4-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="85ee4-114">Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage des communications internes ou externes dans les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="85ee4-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="85ee4-115">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">la section gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="85ee4-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="85ee4-116">Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange contrôlent la configuration de l’archivage pour les utilisateurs qui sont hébergés sur Exchange 2013 et ont leurs boîtes aux lettres placées sur place.</span><span class="sxs-lookup"><span data-stu-id="85ee4-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="85ee4-117">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="85ee4-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85ee4-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="85ee4-118">In This Section</span></span>

  - [<span data-ttu-id="85ee4-119">Création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="85ee4-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [<span data-ttu-id="85ee4-120">Modification d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour votre organisation, certains sites ou des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="85ee4-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [<span data-ttu-id="85ee4-121">Appliquer une stratégie d’archivage aux utilisateurs de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ee4-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="85ee4-122">Configuration de stratégies d’archivage dans Lync Server 2013 lors de l’utilisation d’une intégration Exchange Server</span><span class="sxs-lookup"><span data-stu-id="85ee4-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="85ee4-123">Suppression d’une stratégie d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85ee4-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

