---
title: 'Lync Server 2013: régions réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9a2fd8ce5de11f592d010615ddee9c253913c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="ac19a-102">Régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac19a-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac19a-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ac19a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ac19a-104">Les *régions réseau* sont les concentrateurs réseau ou les dorsales utilisés dans la configuration de contrôle d’admission des appels, de E9-1-1 et de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="ac19a-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="ac19a-105">Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ac19a-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="ac19a-106">Par exemple, si vous avez déjà créé des régions réseau pour une seule fonctionnalité vocale, vous n’avez pas besoin de créer de nouvelles régions réseau. d’autres fonctionnalités avancées de voix entreprise utiliseront les mêmes régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ac19a-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="ac19a-107">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ac19a-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ac19a-108">Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="ac19a-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="ac19a-109">Pour plus d’informations, voir [configurer des régions réseau pour CAC dans Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="ac19a-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ac19a-110">Les exigences spécifiques aux fonctionnalités relatives aux définitions de zones réseau sont décrites dans les rubriques de déploiement de la fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ac19a-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac19a-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ac19a-111">In This Section</span></span>

  - [<span data-ttu-id="ac19a-112">Affichage des informations de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac19a-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="ac19a-113">Création ou modification des régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac19a-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="ac19a-114">Supprimer des zones réseau existantes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac19a-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="ac19a-115">Référence</span><span class="sxs-lookup"><span data-stu-id="ac19a-115">Reference</span></span>

[<span data-ttu-id="ac19a-116">Déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac19a-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

