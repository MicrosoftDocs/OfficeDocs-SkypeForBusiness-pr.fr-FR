---
title: Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Résumé : Découvrez comment afficher les enregistrements d’utilisation PSTN à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109830"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="65f7f-103">Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="65f7f-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="65f7f-104">**Résumé :** Découvrez comment afficher les enregistrements d’utilisation PSTN à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="65f7f-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="65f7f-105">Un enregistrement d’utilisation du réseau téléphonique commuté (PSTN) spécifie une classe d’appel (interne, local ou longue distance) qui peut être réalisée par différents utilisateurs ou groupes d’utilisateurs dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="65f7f-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="65f7f-106">Pour plus d’informations, voir [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="65f7f-106">For details, see [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="65f7f-107">Pour afficher un enregistrement d’utilisation PSTN à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="65f7f-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="65f7f-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="65f7f-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="65f7f-109">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation PSTN**.</span><span class="sxs-lookup"><span data-stu-id="65f7f-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="65f7f-110">Dans la page **Utilisation PSTN**, sélectionnez l’enregistrement d’utilisation PSTN que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="65f7f-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65f7f-111">Une page en lecture seule de l’enregistrement d’utilisation PSTN sélectionné affiche les itinéraires associés et les stratégies de voix associées.</span><span class="sxs-lookup"><span data-stu-id="65f7f-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="65f7f-112">Pour afficher les informations d’utilisation PSTN à l’aide des cmdlets Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="65f7f-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="65f7f-113">Pour afficher des informations sur toutes vos utilisations PSTN, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="65f7f-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="65f7f-114">Cette commande renvoie des informations comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="65f7f-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="65f7f-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65f7f-115">See also</span></span>

[<span data-ttu-id="65f7f-116">Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="65f7f-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)