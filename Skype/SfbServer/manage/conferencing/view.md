---
title: Afficher les stratégies de conférence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Résumé: Découvrez comment afficher les stratégies de conférence dans Skype entreprise Server.'
ms.openlocfilehash: 1f1545761838cf176abd88fa12abd9ef5a1d8136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280319"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="9aaaa-103">Afficher les stratégies de conférence dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9aaaa-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="9aaaa-104">**Résumé:** Découvrez comment afficher les stratégies de conférence dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="9aaaa-105">Vous pouvez afficher les stratégies de conférence en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9aaaa-106">Afficher les stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9aaaa-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9aaaa-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9aaaa-108">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9aaaa-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="9aaaa-110">Dans la page **Stratégie de conférence**, double-cliquez sur la stratégie de conférence à afficher.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="9aaaa-111">Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="9aaaa-112">**Modifier une stratégie de \<Conférence\> :** ouvre l’affichage des paramètres pour la stratégie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9aaaa-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="9aaaa-113">Pour plus d’informations sur la configuration des paramètres, consultez la rubrique [créer des stratégies de conférence dans Skype entreprise Server](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9aaaa-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9aaaa-114">Afficher les stratégies de conférence à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9aaaa-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9aaaa-115">Pour afficher les stratégies de conférence, utilisez l’applet de commande **Get-Cs ConferencingPolicy** :</span><span class="sxs-lookup"><span data-stu-id="9aaaa-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="9aaaa-116">L’applet de commande renvoie des informations, comme les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9aaaa-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="9aaaa-117">Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, consultez la rubrique [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9aaaa-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

