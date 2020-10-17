---
title: 'Lync Server 2013 : configuration et affectation de stratégies d’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af6a253de4d35b3505b5ffa8be42fae297221641
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517571"
---
# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="dd34d-102">Configuration et affectation de stratégies d’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd34d-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd34d-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dd34d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dd34d-104">Dans Lync Server 2013, vous utilisez des stratégies pour activer et désactiver l’archivage pour les communications internes et les communications externes pour les utilisateurs hébergés sur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd34d-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="dd34d-105">Il s’agit notamment des stratégies d’archivage suivantes :</span><span class="sxs-lookup"><span data-stu-id="dd34d-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="dd34d-106">Stratégie globale créée par défaut lorsque vous déployez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd34d-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="dd34d-107">Stratégies facultatives au niveau site et utilisateur que vous pouvez créer et utiliser pour définir de quelle manière l’archivage est implémenté pour des sites ou utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="dd34d-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="dd34d-108">Vous définissez les stratégies d’archivage lors du déploiement initial de l’archivage, mais vous pouvez modifier et supprimer des stratégies existantes, ou en ajouter de nouvelles, à tout moment après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="dd34d-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="dd34d-109">Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page **stratégie d’archivage** du groupe **archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd34d-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd34d-110">Pour contrôler l’implémentation de l’archivage, vous devez définir certaines options de configuration de l’archivage, notamment spécifier si les messages instantanés ou les conférences doivent être archivés, si le mode critique est utilisé et les options de vidage.</span><span class="sxs-lookup"><span data-stu-id="dd34d-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="dd34d-111">Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans la configuration de l’archivage de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="dd34d-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="dd34d-112">Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage des communications internes ou externes dans les stratégies d’archivage.</span><span class="sxs-lookup"><span data-stu-id="dd34d-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="dd34d-113">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for Your Organization, sites, and pools</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="dd34d-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="dd34d-114">Si vous intégrez votre stockage Lync Server au stockage Exchange 2013, les stratégies d’utilisateur Exchange prévalent sur les stratégies d’archivage Lync Server 2013, mais uniquement pour les utilisateurs hébergés sur Exchange 2013 dont les boîtes aux lettres ont été placées en conservation In-Place.</span><span class="sxs-lookup"><span data-stu-id="dd34d-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="dd34d-115">Pour plus d’informations sur l’implémentation des stratégies, y compris la hiérarchie des stratégies, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="dd34d-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="dd34d-116">Pour plus d’informations sur la gestion des stratégies après le déploiement, voir [Managing the Archiving of Internal and External Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="dd34d-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd34d-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="dd34d-117">In This Section</span></span>

  - [<span data-ttu-id="dd34d-118">Configuration de la stratégie globale pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd34d-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="dd34d-119">Configuration des stratégies de site pour l’archivage dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd34d-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="dd34d-120">Configuration des stratégies d’archivage pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd34d-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

