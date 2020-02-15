---
title: 'Lync Server 2013 : configuration de la prise d’appel de groupe'
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
ms.openlocfilehash: cbd4c7fc1d0e2c052910b6ddcc9027b9c3db4f72
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="4fcad-102">Configuration de la prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fcad-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fcad-103">_**Dernière modification de la rubrique :** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="4fcad-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="4fcad-104">Mise à jour cumulative pour Lync Server 2013 : février 2013 introduit la prise d’appel de groupe en tant que nouvelle fonctionnalité voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="4fcad-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="4fcad-105">La prise d’appel de groupe permet aux utilisateurs de sélectionner des appels qui sonnent pour un autre utilisateur en composant un numéro de groupe de prise d’appel.</span><span class="sxs-lookup"><span data-stu-id="4fcad-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="4fcad-106">Les composants utilisés par le groupe de prise d’appel sont automatiquement installés et activés sur le serveur frontal ou le serveur Standard Edition lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="4fcad-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="4fcad-107">Toutefois, vous devez configurer la prise d’appel de groupe avant qu’elle ne soit disponible pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4fcad-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="4fcad-108">Cette section vous guide tout au long de la configuration de la prise d’appel de groupe.</span><span class="sxs-lookup"><span data-stu-id="4fcad-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4fcad-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4fcad-109">In This Section</span></span>

[<span data-ttu-id="4fcad-110">Conditions préalables à la configuration de la prise d’appel de groupe et droits de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fcad-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="4fcad-111">Processus de déploiement de la prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fcad-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="4fcad-112">Déployer l’outil SEFAUtil dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fcad-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="4fcad-113">Configurer les numéros de groupe de prise d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fcad-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="4fcad-114">Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe</span><span class="sxs-lookup"><span data-stu-id="4fcad-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="4fcad-115">Communiquer des attributions de prise d’appel de groupe aux utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fcad-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="4fcad-116">Module Vérifier le déploiement de la prise d’appel de groupe dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fcad-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

