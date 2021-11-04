---
title: Afficher les stratégies de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Résumé : Découvrez comment afficher les stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: cb401abbf6fec1a280099ca30c570338d419c55e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762472"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Afficher les stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment afficher les stratégies de conférence dans Skype Entreprise Server.
  
Vous pouvez afficher les stratégies de conférence à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Afficher les stratégies de conférence à l’aide Skype Entreprise Server panneau de bord

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Stratégie **de conférence.**
    
4. Sur la page **Stratégie de conférence**, double-cliquez sur la stratégie de conférence que vous voulez voir.
    
5. Dans **Modifier le filtre de fichier,** cochez la case Afficher les **détails.**
    
    **Modifier la stratégie de \<policy\> conférence -** affiche les paramètres de la stratégie sélectionnée.
    
    Pour plus d’informations sur la configuration des paramètres, voir Créer des stratégies de conférence [dans Skype Entreprise Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Afficher les stratégies de conférence à l’aide Skype Entreprise Server Management Shell

Pour afficher les stratégies de conférence, utilisez l’cmdlet **Get-CsConferencingPolicy** :
  
```PowerShell
Get-CsConferencingPolicy
```

La cmdlet renvoie des informations telles que les suivantes :
  
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

Pour plus d’informations, notamment une description complète de la syntaxe et la liste des paramètres, voir [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
