---
title: Modifier les itinéraires de communications vocales pour utiliser le nouveau serveur de médiation Lync Server 2013
description: Modifiez les itinéraires des communications vocales pour utiliser le nouveau serveur de médiation Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545740"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="6a898-103">Modifier les itinéraires de communications vocales pour utiliser le nouveau serveur de médiation Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a898-103">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a898-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6a898-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6a898-105">Cette procédure modifie les itinéraires des communications vocales de façon à utiliser le serveur de médiation Lync Server 2013, au lieu du serveur de médiation Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="6a898-105">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="6a898-106">Pour changer les itinéraires des communications vocales de façon à utiliser le nouveau serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="6a898-106">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="6a898-107">Panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a898-107">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="6a898-108">Dans le volet gauche, sélectionnez **Routage des communications vocales**, puis cliquez sur **Itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="6a898-108">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="6a898-109">Cliquez sur **Nouveau** pour créer un itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="6a898-109">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="6a898-110">Remplissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="6a898-110">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="6a898-p101">**Nom** : tapez un nom descriptif de l’itinéraire des communications vocales. Pour ce document, nous allons utiliser **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="6a898-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="6a898-113">**Description** : tapez une brève description de l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="6a898-113">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="6a898-p102">Ignorez toutes les autres sections jusqu’à atteindre **Passerelles associées**. Cliquez sur **Ajouter**. Sélectionnez la nouvelle passerelle par défaut et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a898-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="6a898-117">Sous **Utilisations PSTN associées**, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="6a898-117">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="6a898-118">Dans la page **Sélectionner un enregistrement d’utilisation PSTN**, sélectionnez un nom d’enregistrement, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a898-118">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="6a898-119">Dans la page **Nouvel itinéraire des communications vocales**, cliquez sur **OK** pour créer l’**Itinéraire des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="6a898-119">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="6a898-120">Dans la page **Routage des communications vocales**, sélectionnez **Itinéraire**.</span><span class="sxs-lookup"><span data-stu-id="6a898-120">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="6a898-121">Déplacez l’itinéraire que vous venez de créer en haut de la liste, puis sélectionnez **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6a898-121">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

