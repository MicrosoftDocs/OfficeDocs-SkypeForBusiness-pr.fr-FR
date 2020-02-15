---
title: 'Lync Server 2013 : activation de la stratégie de serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f98275ee911d1abecbc60907653ad8de0a4222
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="8b7cf-102">Activer la stratégie de serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b7cf-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b7cf-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8b7cf-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8b7cf-104">Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page **stratégie de conversation permanente** du groupe de **conversation permanente** pour gérer les stratégies au niveau global, du pool, du site ou de l’utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’une ou de plusieurs stratégies d’utilisateur et de site supplémentaires pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="8b7cf-105">Si un utilisateur est activé pour le serveur de conversation permanente par stratégie, l’environnement de serveur de conversation permanente apparaît dans le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b7cf-106">Dans la topologie, les stratégies de site de serveur de conversation permanente s’appliquent globalement, par pool d’utilisateur, par site d’utilisateur ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="8b7cf-107">La stratégie globale est créée automatiquement lorsque vous déployez le serveur de conversation permanente, et elle peut être configurée, mais pas supprimée.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="8b7cf-108">La stratégie globale s’appliquant à tous les utilisateurs, il n’est pas obligatoire de la définir par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="8b7cf-109">Vous pouvez créer et configurer plusieurs stratégies de site et utilisateur qui, avec la stratégie globale, permettent aux utilisateurs de disposer d’un serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="8b7cf-110">Les stratégies de serveur de conversation permanente de pool et de site remplacent la stratégie de serveur de conversation permanente globale, mais uniquement pour les utilisateurs de ce site.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="8b7cf-111">Les stratégies utilisateur supplantent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est assignée.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b7cf-112">Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="8b7cf-113">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="8b7cf-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8b7cf-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8b7cf-114">In This Section</span></span>

  - [<span data-ttu-id="8b7cf-115">Configurer la stratégie globale pour la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b7cf-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8b7cf-116">Créer une stratégie de site pour la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b7cf-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8b7cf-117">Créer une stratégie utilisateur pour la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b7cf-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="8b7cf-118">Appliquer une stratégie de conversation permanente à un utilisateur ou un groupe d’utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b7cf-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

