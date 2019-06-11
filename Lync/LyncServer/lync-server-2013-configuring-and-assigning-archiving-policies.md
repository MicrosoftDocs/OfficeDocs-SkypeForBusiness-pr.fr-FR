---
title: 'Lync Server 2013: configuration et affectation de stratégies d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8b3b4f1f9465684d7c9139b8cd548caacf91c41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="a44f3-102">Configuration et affectation de stratégies d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a44f3-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a44f3-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a44f3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a44f3-104">Dans Lync Server 2013, vous utilisez des stratégies pour activer et désactiver l’archivage des communications internes et des communications externes pour les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a44f3-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="a44f3-105">Cela inclut les stratégies d’archivage suivantes:</span><span class="sxs-lookup"><span data-stu-id="a44f3-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="a44f3-106">Stratégie globale créée par défaut lors du déploiement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a44f3-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="a44f3-107">Stratégies de niveau de site et de niveau utilisateur facultatives que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a44f3-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="a44f3-108">Vous définissez initialement des stratégies d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des stratégies après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a44f3-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="a44f3-109">Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la page de **stratégie** d’archivage du groupe **archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a44f3-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a44f3-110">Pour contrôler l’implémentation de l’archivage, vous devez spécifier les options de configuration de l’archivage, par exemple pour archiver les messages instantanés ou les conférences, utiliser le mode Critical et les options de purge.</span><span class="sxs-lookup"><span data-stu-id="a44f3-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="a44f3-111">Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans toute configuration d’archivage de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="a44f3-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="a44f3-112">Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage des communications internes ou externes dans les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="a44f3-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="a44f3-113">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">la section gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="a44f3-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="a44f3-114">Si vous intégrez le stockage de votre serveur Lync au stockage 2013 Exchange, les stratégies d’utilisateur Exchange ont la priorité sur les stratégies d’archivage de Lync Server 2013, mais uniquement pour les utilisateurs hébergés sur Exchange 2013 qui ont reçu leurs boîtes aux lettres dans la conservation inaltérable.</span><span class="sxs-lookup"><span data-stu-id="a44f3-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="a44f3-115">Pour plus d’informations sur l’implémentation de stratégies, y compris la hiérarchie des stratégies, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.</span><span class="sxs-lookup"><span data-stu-id="a44f3-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="a44f3-116">Pour plus d’informations sur la gestion des stratégies après le déploiement, reportez-vous à [la rubrique gestion de l’archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="a44f3-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a44f3-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a44f3-117">In This Section</span></span>

  - [<span data-ttu-id="a44f3-118">Configuration de la stratégie globale d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a44f3-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="a44f3-119">Configuration de stratégies de site pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a44f3-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="a44f3-120">Configuration de stratégies d’archivage pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a44f3-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

