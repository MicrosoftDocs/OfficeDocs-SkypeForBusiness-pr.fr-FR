---
title: 'Lync Server 2013 : configuration de la cueillette des appels de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3096c468b478da365bcfa0e38fa287a5c2ab57a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="79268-102">Configuration de la collecte d’appels de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79268-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79268-103">_**Dernière modification de la rubrique :** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="79268-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="79268-104">Mise à jour cumulative pour Lync Server 2013 : février 2013 présente la capture d’appel de groupe comme nouvelle fonctionnalité voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="79268-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="79268-105">La cueillette de groupe permet aux utilisateurs de décrocher les appels qui sonnent pour un autre utilisateur en composant un numéro de groupe de capture d’appel.</span><span class="sxs-lookup"><span data-stu-id="79268-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="79268-106">Les composants utilisés par le biais du groupe de collecte d’appels sont automatiquement installés et activés sur le serveur frontal ou le serveur Standard Edition lors du déploiement d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="79268-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="79268-107">Toutefois, vous devez configurer la cueillette d’appel de groupe avant qu’elle ne soit disponible pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="79268-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="79268-108">Cette section vous guide dans la configuration de la sélection d’appels de groupe.</span><span class="sxs-lookup"><span data-stu-id="79268-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="79268-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="79268-109">In This Section</span></span>

[<span data-ttu-id="79268-110">Configuration requise pour les appels de groupe et droits d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79268-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="79268-111">Processus de déploiement pour l’enlèvement de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79268-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="79268-112">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79268-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="79268-113">Configurer des numéros de groupe de capture d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79268-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="79268-114">Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe</span><span class="sxs-lookup"><span data-stu-id="79268-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="79268-115">Communiquer des attributions d’appels de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79268-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="79268-116">Facultatif Vérifier le déploiement d’un appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79268-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

