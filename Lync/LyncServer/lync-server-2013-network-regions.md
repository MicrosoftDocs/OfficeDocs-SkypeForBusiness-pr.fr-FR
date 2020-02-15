---
title: 'Lync Server 2013 : régions réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd0a41aae0244eb6f0212c6c620d23f1bbf6400
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="3c810-102">Régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c810-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c810-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3c810-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3c810-104">Les *régions réseau* sont les concentrateurs de réseau ou les dorsales principales utilisés dans la configuration du contrôle d’admission d’appels, E9-1-1, et la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="3c810-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="3c810-105">Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="3c810-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="3c810-106">Par exemple, si vous avez déjà créé des régions réseau pour une fonction vocale, vous n’avez pas besoin de créer de nouvelles régions réseau ; les autres fonctions Enterprise Voice avancées utiliseront ces mêmes régions réseau.</span><span class="sxs-lookup"><span data-stu-id="3c810-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="3c810-107">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="3c810-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="3c810-108">Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis déployez ensuite le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="3c810-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="3c810-109">Pour plus d’informations, reportez-vous à la rubrique [configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="3c810-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c810-110">Toutes les exigences ayant trait à des fonctionnalités pour les définitions des régions réseau sont documentées dans les rubriques de déploiement des fonctionnalités concernées.</span><span class="sxs-lookup"><span data-stu-id="3c810-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c810-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3c810-111">In This Section</span></span>

  - [<span data-ttu-id="3c810-112">Affichage des informations de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c810-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="3c810-113">Création ou modification de régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c810-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="3c810-114">Suppression des régions réseau existantes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c810-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="3c810-115">Référence</span><span class="sxs-lookup"><span data-stu-id="3c810-115">Reference</span></span>

[<span data-ttu-id="3c810-116">Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c810-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

