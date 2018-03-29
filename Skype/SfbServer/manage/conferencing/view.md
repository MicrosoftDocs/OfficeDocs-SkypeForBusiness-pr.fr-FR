---
title: Affichage des stratégies de conférence dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Résumé : Apprenez à afficher les stratégies de la conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4d91a04456f7c9d877e58caed1d576edc0f80b41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="21ba1-103">Affichage des stratégies de conférence dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="21ba1-103">View conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="21ba1-104">**Résumé :** Apprenez à afficher les stratégies de la conférence dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="21ba1-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="21ba1-105">Vous pouvez afficher les stratégies de conférence à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="21ba1-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="21ba1-106">Afficher les stratégies de conférence pour le panneau de configuration de Business Server à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="21ba1-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="21ba1-107">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="21ba1-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="21ba1-108">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="21ba1-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="21ba1-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="21ba1-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="21ba1-110">Dans la page **Stratégie de conférence**, double-cliquez sur la stratégie de conférence à afficher.</span><span class="sxs-lookup"><span data-stu-id="21ba1-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="21ba1-111">Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="21ba1-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="21ba1-112">**Modifier la consigne de conférence - \<stratégie de\> ** s’ouvre et affiche les paramètres de la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="21ba1-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="21ba1-113">Pour plus d’informations sur la configuration des paramètres, reportez-vous à la section [créer des stratégies de conférence dans Skype pour Business Server 2015](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="21ba1-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server 2015](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="21ba1-114">Afficher les stratégies de conférence pour Business Server Management Shell à l’aide de Skype</span><span class="sxs-lookup"><span data-stu-id="21ba1-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="21ba1-115">Pour afficher les stratégies de conférence, utilisez l’applet de commande **Get-Cs ConferencingPolicy** :</span><span class="sxs-lookup"><span data-stu-id="21ba1-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="21ba1-116">L’applet de commande renvoie des informations, comme les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="21ba1-116">The cmdlet returns information such as the following:</span></span>
  
```
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

```

<span data-ttu-id="21ba1-117">Pour plus d’informations, y compris une description de la syntaxe complète et la liste des paramètres, consultez [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="21ba1-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

