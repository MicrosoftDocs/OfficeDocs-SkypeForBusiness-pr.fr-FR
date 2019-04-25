---
title: Activer ou désactiver la conférence rendez-vous dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Résumé : Découvrez comment utiliser le panneau de configuration ou Management Shell pour activer ou désactiver la conférence rendez-vous dans Skype pour Business Server.'
ms.openlocfilehash: 216973e8d3a887dcae308fc5efa6d67b2415493b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222827"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="16d23-103">Activer ou désactiver la conférence rendez-vous dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="16d23-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="16d23-104">**Résumé :** Découvrez comment utiliser le panneau de configuration ou Management Shell pour activer ou désactiver la conférence rendez-vous dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="16d23-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="16d23-105">Vous pouvez activer la conférence rendez-vous à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="16d23-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="16d23-106">Activer ou désactiver la conférence rendez-vous à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="16d23-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="16d23-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="16d23-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="16d23-108">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="16d23-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="16d23-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="16d23-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="16d23-110">Dans la liste des stratégies de conférence, sélectionnez celle pour laquelle vous voulez activer la conférence rendez-vous, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="16d23-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="16d23-p101">Pour autoriser les utilisateurs à rejoindre une réunion en composant un numéro d’accès, activez la case à cocher **Activer la conférence rendez-vous RTC**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="16d23-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="16d23-113">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="16d23-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="16d23-114">Activer ou désactiver la conférence rendez-vous à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="16d23-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="16d23-115">Pour activer ou désactiver une conférence rendez-vous, utilisez l’applet de commande **Set-CsConferencingPolicy** avec le paramètre EnableDialInConferencing, comme suit :</span><span class="sxs-lookup"><span data-stu-id="16d23-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="16d23-116">Pour plus d’informations, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="16d23-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

