---
title: Afficher les paramètres de configuration de la réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Résumé: Découvrez comment afficher les paramètres de configuration de la réunion dans Skype entreprise Server.'
ms.openlocfilehash: 13d91bc4c0335d8c069e0b0d9bc41efd8714f112
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280368"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Afficher les paramètres de configuration de la réunion dans Skype entreprise Server
 
**Résumé:** Découvrez comment afficher les paramètres de configuration de la réunion dans Skype entreprise Server.
  
Vous pouvez afficher les paramètres de configuration de la réunion en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Afficher les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server
<a name="BKMK_ViewJoinSettings"> </a>

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
4. Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion à afficher.
    
5. Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails**.
    
    **Modifier la configuration de \<la\> réunion: une stratégie** s’ouvre et affiche les paramètres de la stratégie sélectionnée.
    
    Pour plus d’informations sur la configuration des paramètres, consultez la rubrique [créer des paramètres de configuration de réunion dans Skype entreprise Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Afficher les paramètres de configuration de la réunion à l’aide de Skype entreprise Server Management Shell
<a name="BKMK_ViewJoinSettings"> </a>

Pour afficher des informations sur tous vos paramètres de configuration de réunion, utilisez l’applet de commande **Get-CsMeetingConfiguration** :
  
```
Get-CsMeetingConfiguration
```

Cette commande renvoie les informations suivantes :
  
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

Pour plus d’informations, y compris une liste complète des paramètres, consultez la rubrique [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

