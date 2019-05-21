---
title: Afficher les enregistrements d’utilisation RTC dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Résumé: Découvrez comment afficher les enregistrements d’utilisation de la Conférence RTC à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell.'
ms.openlocfilehash: d00fcab8c7f5ad9b8f47d5aecb6c6169e8d43574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300922"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="45f42-103">Afficher les enregistrements d’utilisation RTC dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="45f42-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="45f42-104">**Résumé:** Découvrez comment afficher les enregistrements d’utilisation RTC à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="45f42-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="45f42-p101">Un enregistrement d’utilisation du réseau téléphonique commuté (RTC) spécifie une classe d’appel (interne, local ou longue distance) qui peut être utilisée par différents utilisateurs ou groupes d’utilisateurs dans une organisation. Pour plus d’informations, reportez-vous à la rubrique [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="45f42-p101">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization. For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="45f42-107">Pour afficher un enregistrement d’utilisation RTC en utilisant le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="45f42-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="45f42-108">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="45f42-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="45f42-109">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation RTC**.</span><span class="sxs-lookup"><span data-stu-id="45f42-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="45f42-110">Dans la page **Utilisation RTC**, sélectionnez l’enregistrement d’utilisation RTC que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="45f42-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45f42-111">Une page en lecture seule de l’enregistrement d’utilisation RTC sélectionné affiche les itinéraires associés et les stratégies de voix associées.</span><span class="sxs-lookup"><span data-stu-id="45f42-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="45f42-112">Pour afficher les informations d’utilisation RTC à l’aide des applets de commande Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="45f42-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="45f42-113">Pour afficher des informations sur l’ensemble de vos utilisations RTC, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="45f42-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="45f42-114">Cette commande renvoie le type d’informations suivant :</span><span class="sxs-lookup"><span data-stu-id="45f42-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="45f42-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45f42-115">See also</span></span>

[<span data-ttu-id="45f42-116">Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="45f42-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

