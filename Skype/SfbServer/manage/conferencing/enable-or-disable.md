---
title: Activation ou désactivation des conférences rendez-vous dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Résumé : Apprenez à utiliser le panneau de configuration ou Management Shell pour activer ou désactiver la numérotation conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: 6441e548ce944cdd8786178ed7b80b0af7d625f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server-2015"></a>Activation ou désactivation des conférences rendez-vous dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à utiliser le panneau de configuration ou Management Shell pour activer ou désactiver la numérotation conférence dans Skype pour Business Server 2015.
  
Vous pouvez activer la numérotation de conférence à l’aide de Skype pour le panneau de configuration de Business Server ou à l’aide de Skype pour Business Server Management Shell.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Activer ou désactiver l’appel de conférence pour le panneau de configuration de Business Server à l’aide de Skype

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
4. Dans la liste des stratégies de conférence, sélectionnez celle pour laquelle vous voulez activer la conférence rendez-vous, cliquez sur **Modifier**, puis sur **Afficher les détails**. 
    
5. Pour autoriser les utilisateurs à rejoindre une réunion en composant un numéro d’accès, activez la case à cocher **Activer la conférence rendez-vous RTC**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (RTC).
    
6. Cliquez sur **Valider**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Activer ou désactiver les conférences à distance à l’aide de Skype pour Business Server Management Shell

Pour activer ou désactiver une conférence rendez-vous, utilisez l’applet de commande **Set-CsConferencingPolicy** avec le paramètre EnableDialInConferencing, comme suit :
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Pour plus d’informations, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

