---
title: Afficher les stratégies de conférence dans Skype Entreprise Server
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Résumé : Découvrez comment afficher les stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 39b37a1335f8b257f9dec1fff28bea90ac7a6db9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817504"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="1e95f-103">Afficher les stratégies de conférence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1e95f-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="1e95f-104">**Résumé :** Découvrez comment afficher les stratégies de conférence dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1e95f-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="1e95f-105">Vous pouvez afficher les stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1e95f-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1e95f-106">Afficher les stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1e95f-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1e95f-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1e95f-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="1e95f-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1e95f-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1e95f-109">Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur Stratégie **de conférence.**</span><span class="sxs-lookup"><span data-stu-id="1e95f-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="1e95f-110">Sur la page **Stratégie de conférence**, double-cliquez sur la stratégie de conférence que vous voulez voir.</span><span class="sxs-lookup"><span data-stu-id="1e95f-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="1e95f-111">Dans **Modifier le filtre de fichier,** cochez la case Afficher les **détails.**</span><span class="sxs-lookup"><span data-stu-id="1e95f-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="1e95f-112">**Modifier la stratégie de \<policy\> conférence -** affiche les paramètres de la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e95f-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="1e95f-113">Pour plus d’informations sur la configuration des paramètres, voir Créer des stratégies de conférence [dans Skype Entreprise Server.](create-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1e95f-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1e95f-114">Afficher les stratégies de conférence à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1e95f-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1e95f-115">Pour afficher les stratégies de conférence, utilisez l’cmdlet **Get-CsConferencingPolicy** :</span><span class="sxs-lookup"><span data-stu-id="1e95f-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="1e95f-116">La cmdlet renvoie des informations telles que les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1e95f-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

<span data-ttu-id="1e95f-117">Pour plus d’informations, notamment une description complète de la syntaxe et la liste des paramètres, voir [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1e95f-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

