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
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827924"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Afficher les paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment afficher les paramètres de configuration de réunion dans Skype Entreprise Server.
  
Vous pouvez afficher les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Afficher les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur **Configuration de la réunion.**
    
4. Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion que vous voulez afficher.
    
5. Dans **Modifier le filtre de fichier,** cochez la case Afficher les **détails.**
    
    **Modifier la \<policy\> configuration de la réunion -** affiche les paramètres de la stratégie sélectionnée.
    
    Pour plus d’informations sur la configuration des paramètres, voir Créer des paramètres de configuration de [réunion dans Skype Entreprise Server.](create-settings.md)
    
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

Pour plus d’informations, y compris une liste complète des paramètres, voir [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

