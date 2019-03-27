---
title: Afficher les paramètres de configuration dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Résumé : Découvrez comment afficher les paramètres de configuration dans Skype pour Business Server.'
ms.openlocfilehash: d7ef617050b31bd85732ee4a30d0faaed41f50d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899397"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Afficher les paramètres de configuration dans Skype pour Business Server
 
**Résumé :** Découvrez comment afficher les paramètres de configuration dans Skype pour Business Server.
  
Vous pouvez afficher les paramètres de configuration de réunion à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Afficher les paramètres de configuration de réunion à l’aide de Skype pour Business Server Control Panel
<a name="BKMK_ViewJoinSettings"> </a>

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
4. Dans la page **Configuration de la réunion**, cliquez sur la configuration de réunion à afficher.
    
5. Dans **Modifier le filtre de fichier**, sélectionnez la case à cocher **Afficher les détails**.
    
    **Modifier la Configuration de réunion - \<stratégie\> ** s’ouvre et affiche les paramètres de la stratégie sélectionnée.
    
    Pour plus d’informations sur la configuration des paramètres, voir [Create dans Skype pour Business Server, les paramètres de configuration de la réunion](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Afficher les paramètres de configuration de réunion à l’aide de Skype pour Business Server Management Shell
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

Pour plus d’informations, notamment une liste complète des paramètres, voir [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

