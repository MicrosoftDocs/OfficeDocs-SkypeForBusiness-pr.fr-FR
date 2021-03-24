---
title: Afficher les paramètres de configuration de réunion dans Skype Entreprise Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Résumé : Découvrez comment afficher les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: 81f5ef1bc0ce28c7741aa99529e7ba107ff4127f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096700"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Afficher les paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment afficher les paramètres de configuration de réunion dans Skype Entreprise Server.
  
Vous pouvez afficher les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Afficher les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Configuration de **la réunion.**
    
4. Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion que vous voulez afficher.
    
5. Dans **Modifier le filtre de fichier,** cochez la case Afficher les **détails.**
    
    **Modifier la \<policy\> configuration de la réunion -** affiche les paramètres de la stratégie sélectionnée.
    
    Pour plus d’informations sur la configuration des paramètres, voir Créer des paramètres de configuration de réunion [dans Skype Entreprise Server.](create-settings.md)
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Afficher les paramètres de configuration de réunion à l’aide de Skype Entreprise Server Management Shell
<a name="BKMK_ViewJoinSettings"> </a>

Pour afficher des informations sur tous vos paramètres de configuration de réunion, utilisez l’cmdlet **Get-CsMeetingConfiguration** :
  
```
Get-CsMeetingConfiguration
```

Cette commande retourne des informations semblables à ce qui suit :
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

Pour plus d’informations, y compris une liste complète des paramètres, voir [Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
