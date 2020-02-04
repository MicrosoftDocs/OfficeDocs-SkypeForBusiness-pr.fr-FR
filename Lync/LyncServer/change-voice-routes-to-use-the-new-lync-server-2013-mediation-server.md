---
title: Changer les itinéraires vocaux pour utiliser le nouveau serveur de médiation Lync Server 2013
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
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="add83-102">Changer les itinéraires vocaux pour utiliser le nouveau serveur de médiation Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="add83-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="add83-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="add83-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="add83-104">Cette procédure modifie les itinéraires vocaux pour utiliser le serveur de médiation Lync Server 2013, au lieu du serveur de médiation traditionnel d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="add83-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="add83-105">Pour modifier les itinéraires vocaux et utiliser le nouveau serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="add83-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="add83-106">Panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="add83-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="add83-107">Dans le volet de gauche, sélectionnez routage de la **voix** , puis **route**.</span><span class="sxs-lookup"><span data-stu-id="add83-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="add83-108">Cliquez sur **nouveau** pour créer un nouvel itinéraire.</span><span class="sxs-lookup"><span data-stu-id="add83-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="add83-109">Renseignez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="add83-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="add83-110">**Nom**: tapez un nom descriptif pour l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="add83-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="add83-111">Pour ce document, nous utiliserons **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="add83-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="add83-112">**Description**: tapez une brève description de l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="add83-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="add83-113">Ignorer toutes les sections restantes jusqu’à ce que vous atteigniez les **passerelles associées**.</span><span class="sxs-lookup"><span data-stu-id="add83-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="add83-114">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="add83-114">Click **Add**.</span></span> <span data-ttu-id="add83-115">Sélectionnez la nouvelle passerelle par défaut, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="add83-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="add83-116">Dans **utilisations RTC associées**, cliquez sur **Sélectionner**.</span><span class="sxs-lookup"><span data-stu-id="add83-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="add83-117">Dans la page **Sélectionner un enregistrement d’utilisation RTC** , sélectionnez un nom d’enregistrement, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="add83-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="add83-118">Dans la page **nouvelle gamme vocale** , cliquez sur **OK** pour créer l' **itinéraire vocal**.</span><span class="sxs-lookup"><span data-stu-id="add83-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="add83-119">Sur la page routage de la **voix** , sélectionnez **gamme**.</span><span class="sxs-lookup"><span data-stu-id="add83-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="add83-120">Déplacez l’itinéraire nouvellement créé vers le haut de la liste, puis sélectionnez **valider**.</span><span class="sxs-lookup"><span data-stu-id="add83-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

