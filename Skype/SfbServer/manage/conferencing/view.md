---
title: Afficher les stratégies de conférence dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Résumé : Découvrez comment afficher les stratégies de conférence dans Skype pour Business Server.'
ms.openlocfilehash: 034de4e8d1a5d1a4a89589d3f6361d22e5a783be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197869"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Afficher les stratégies de conférence dans Skype pour Business Server
 
**Résumé :** Découvrez comment afficher les stratégies de conférence dans Skype pour Business Server.
  
Vous pouvez afficher les stratégies de conférence à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Afficher les stratégies de conférence à l’aide de Skype pour Business Server Control Panel

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
4. Dans la page **Stratégie de conférence**, double-cliquez sur la stratégie de conférence à afficher.
    
5. Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails**.
    
    **Modifier la stratégie de conférence - \<stratégie\> ** s’ouvre et affiche les paramètres de la stratégie sélectionnée.
    
    Pour plus d’informations sur la configuration des paramètres, consultez la rubrique [créer des stratégies de conférence de Skype pour Business Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Afficher les stratégies de conférence à l’aide de Skype pour Business Server Management Shell

Pour afficher les stratégies de conférence, utilisez l’applet de commande **Get-Cs ConferencingPolicy** :
  
```
Get-CsConferencingPolicy
```

L’applet de commande renvoie des informations, comme les opérations suivantes :
  
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

Pour plus d’informations, y compris une description de la syntaxe complète et une liste des paramètres, voir [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

