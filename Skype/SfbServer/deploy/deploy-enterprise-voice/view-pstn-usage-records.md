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
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830534"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="a13c0-103">Afficher les enregistrements d’utilisation PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a13c0-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="a13c0-104">**Résumé :** Découvrez comment afficher les enregistrements d’utilisation PSTN à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a13c0-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="a13c0-105">Un enregistrement d’utilisation du réseau téléphonique commuté (PSTN) spécifie une classe d’appel (interne, local ou longue distance) qui peut être réalisée par différents utilisateurs ou groupes d’utilisateurs dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="a13c0-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="a13c0-106">Pour plus d’informations, voir [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a13c0-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a13c0-107">Pour afficher un enregistrement d’utilisation PSTN à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a13c0-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a13c0-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a13c0-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a13c0-109">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Utilisation PSTN**.</span><span class="sxs-lookup"><span data-stu-id="a13c0-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="a13c0-110">Dans la page **Utilisation PSTN**, sélectionnez l’enregistrement d’utilisation PSTN que vous souhaitez afficher, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a13c0-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a13c0-111">Une page en lecture seule de l’enregistrement d’utilisation PSTN sélectionné affiche les itinéraires associés et les stratégies de voix associées.</span><span class="sxs-lookup"><span data-stu-id="a13c0-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="a13c0-112">Pour afficher les informations d’utilisation PSTN à l’aide des cmdlets Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a13c0-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="a13c0-113">Pour afficher des informations sur toutes vos utilisations PSTN, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="a13c0-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="a13c0-114">Cette commande renvoie des informations comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="a13c0-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="a13c0-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a13c0-115">See also</span></span>

[<span data-ttu-id="a13c0-116">Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a13c0-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

