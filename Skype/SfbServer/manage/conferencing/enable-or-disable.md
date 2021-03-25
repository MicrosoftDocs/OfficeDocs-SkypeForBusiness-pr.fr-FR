---
title: Activer ou désactiver la conférence téléphonique dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Résumé : Découvrez comment utiliser le Panneau de contrôle ou Management Shell pour activer ou désactiver la conférence téléphonique dans Skype Entreprise Server.'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119463"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="e6f6b-103">Activer ou désactiver la conférence téléphonique dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e6f6b-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="e6f6b-104">**Résumé :** Découvrez comment utiliser le Panneau de contrôle ou Management Shell pour activer ou désactiver la conférence téléphonique dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="e6f6b-105">Vous pouvez activer la conférence téléphonique à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e6f6b-106">Activer ou désactiver la conférence téléphonique à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e6f6b-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e6f6b-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e6f6b-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e6f6b-109">Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Stratégie **de conférence.**</span><span class="sxs-lookup"><span data-stu-id="e6f6b-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="e6f6b-110">Dans la liste des stratégies de conférence, sélectionnez celle pour laquelle vous voulez activer la conférence rendez-vous, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="e6f6b-p101">Pour autoriser les utilisateurs à rejoindre une réunion en composant un numéro d’accès, activez la case à cocher **Activer la conférence rendez-vous PSTN**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="e6f6b-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="e6f6b-113">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e6f6b-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e6f6b-114">Activer ou désactiver la conférence téléphonique à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e6f6b-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e6f6b-115">Pour activer ou désactiver la conférence téléphonique, utilisez l’cmdlet **Set-CsConferencingPolicy** avec le paramètre EnableDialInConferencing comme suit :</span><span class="sxs-lookup"><span data-stu-id="e6f6b-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="e6f6b-116">Pour plus d’informations, [voir Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e6f6b-116">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
