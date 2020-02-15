---
title: 'Lync Server 2013 : configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 339eba57121b475732794b15c2c5d16dced303ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="e4894-102">Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4894-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4894-103">_**Dernière modification de la rubrique :** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="e4894-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="e4894-104">Une *stratégie de voix* active un ensemble de fonctionnalités d’appel et associe un ou plusieurs enregistrements d’utilisation PSTN, afin de définir les fonctionnalités d’appel et les autorisations des utilisateurs qui sont affectés à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="e4894-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="e4894-p101">L’étendue de la stratégie de voix peut être *Site* (qui définit les fonctionnalités et autorisations par défaut pour un site réseau) ou *Utilisateur* (qui définit les fonctionnalités et autorisations à affecter pour un utilisateur ou un groupe spécifique). Les utilisateurs non affectés à une stratégie de voix seront automatiquement affectés à la stratégie globale, qui est la stratégie de voix par défaut installée avec le produit.</span><span class="sxs-lookup"><span data-stu-id="e4894-p101">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis). Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4894-107">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-voice-policies.md">stratégies de voix dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="e4894-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4894-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e4894-108">In This Section</span></span>

  - [<span data-ttu-id="e4894-109">Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4894-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="e4894-110">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4894-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="e4894-111">Configuration de l’échappement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4894-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

