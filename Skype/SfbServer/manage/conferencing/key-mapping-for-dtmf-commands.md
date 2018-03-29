---
title: Gestion du mappage des clés des commandes DTMF dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Résumé : Apprenez à gérer le mappage des touches de commandes-dual-tone multifréquence bitonale (DTMF) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 0dca7143b59b7cf4ded0302f763053e71be3bb2b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server-2015"></a>Gestion du mappage des clés des commandes DTMF dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à gérer le mappage des touches de commandes-dual-tone multifréquence bitonale (DTMF) dans Skype pour Business Server 2015.
  
Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF). Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur micro ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone. 
  
Pour gérer les clés utilisées pour les commandes DTMF, utiliser le Skype pour Business Server Management Shell avec **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**et ** Nouvelle-CsDialinConferencingDtmfConfiguration** applets de commande.
  
Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gestion du mappage des touches des commandes DTMF

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Pour afficher les paramètres DTMF utilisés pour la conférence rendez-vous, exécutez la commande ci-dessous dans l’invite de commandes :
    
  ```
  Get-CsDialinConferencingDtmfConfiguration
  ```

4. Pour modifier les paramètres DTMF utilisés pour la conférence rendez-vous, exécutez l’applet de commande ci-dessous et spécifiez la touche sur laquelle appuyer pour chaque option à modifier :
    
  ```
  Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
[-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
[-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
[-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
[-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
  ```

5. (Facultatif) Si vous voulez créer des jeux de commandes DTMF supplémentaires pour des sites spécifiques, utilisez l’applet de commande **New-CsDialinConferencingDtmfConfiguration** avec une identité de site.
    
Dans cet exemple, la touche enfoncée pour activer ou désactiver les annonces est permutée avec la touche enfoncée pour activer ou désactiver le micro de tous les participants. Comme aucune identité n’est spécifiée, ces modifications s’appliquent aux paramètres DTMF globaux :
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Pour plus d’informations, consultez [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)et [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

