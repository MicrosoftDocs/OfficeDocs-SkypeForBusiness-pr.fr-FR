---
title: Configurer des règles de code confidentiel (PIN) de conférence rendez-vous
description: Configurez des règles de code confidentiel (PIN) de conférence rendez-vous.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 799092ba57e9a85cd196840fc81c1f46b96e9900
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565050"
---
# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="3b2d0-103">Configurer des règles de code confidentiel (PIN) de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b2d0-103">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b2d0-104">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="3b2d0-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="3b2d0-105">Les utilisateurs de Lync Server 2013 qui disposent d’informations d’identification des services de domaine Active Directory (AD DS) dans votre organisation peuvent participer à des conférences rendez-vous en tant qu’utilisateurs authentifiés à l’aide d’un code confidentiel (PIN).</span><span class="sxs-lookup"><span data-stu-id="3b2d0-105">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="3b2d0-106">La stratégie de code confidentiel définit les règles de fonctionnement des codes confidentiels de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="3b2d0-107">Vous pouvez créer une nouvelle stratégie de code confidentiel si vous souhaitez qu’une stratégie spécifique s’applique à un site ou à un certain groupe d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-107">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="3b2d0-108">Si vous souhaitez utiliser la même stratégie de code confidentiel pour l’ensemble de votre organisation, vous pouvez utiliser la stratégie de code confidentiel globale et la modifier si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-108">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="3b2d0-109">Les stratégies de code confidentiel s’appliquent aux utilisateurs de l’étendue la plus étroite à l’étendue la plus large.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-109">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="3b2d0-110">Si vous affectez une stratégie de code confidentiel au niveau utilisateur à un utilisateur, ces paramètres prévalent.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-110">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="3b2d0-111">Si vous n’affectez pas de stratégie utilisateur, la stratégie de code confidentiel au niveau du site s’applique, si elle existe.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-111">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="3b2d0-112">Si aucune stratégie d’utilisateur ou de site ne s’applique, la stratégie de code confidentiel globale fournit les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="3b2d0-112">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b2d0-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3b2d0-113">In This Section</span></span>

  - [<span data-ttu-id="3b2d0-114">Modifier les paramètres de code confidentiel de conférence rendez-vous par défaut dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b2d0-114">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="3b2d0-115">Création ou modification des paramètres de code confidentiel des conférences rendez-vous dans Lync Server 2013 pour un site ou un groupe d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3b2d0-115">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="3b2d0-116">Supprimer les paramètres de code confidentiel de conférence rendez-vous pour un site ou un groupe d’utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b2d0-116">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

