---
title: Activer ou désactiver la Conférence rendez-vous dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Résumé: Découvrez comment utiliser le panneau de configuration ou Management Shell pour activer ou désactiver les conférences rendez-vous dans Skype entreprise Server.'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294256"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Activer ou désactiver la Conférence rendez-vous dans Skype entreprise Server
 
**Résumé:** Découvrez comment utiliser le panneau de configuration ou Management Shell pour activer ou désactiver les conférences rendez-vous dans Skype entreprise Server.
  
Vous pouvez activer le service de conférence rendez-vous à l’aide du panneau de configuration Skype entreprise Server ou de Skype entreprise Server Management Shell.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Activer ou désactiver la Conférence rendez-vous à l’aide du panneau de configuration Skype entreprise Server

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
4. Dans la liste des stratégies de conférence, sélectionnez celle pour laquelle vous voulez activer la conférence rendez-vous, cliquez sur **Modifier**, puis sur **Afficher les détails**. 
    
5. Pour autoriser les utilisateurs à rejoindre une réunion en composant un numéro d’accès, activez la case à cocher **Activer la conférence rendez-vous RTC**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (RTC).
    
6. Cliquez sur **Valider**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Activer ou désactiver la Conférence rendez-vous à l’aide de Skype entreprise Server Management Shell

Pour activer ou désactiver une conférence rendez-vous, utilisez l’applet de commande **Set-CsConferencingPolicy** avec le paramètre EnableDialInConferencing, comme suit :
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Pour plus d’informations, consultez la rubrique [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

