---
title: Gérer le mappage des clés pour les commandes DTMF dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Résumé : Découvrez comment gérer le mappage des clés des commandes dual-tone multi-frequency (DTMF) dans Skype pour Business Server.'
ms.openlocfilehash: e90e51bfb3c7c66524e10f7e4428c5bfe36fdcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919476"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gérer le mappage des clés pour les commandes DTMF dans Skype pour Business Server
 
**Résumé :** Découvrez comment gérer le mappage des clés des commandes dual-tone multi-frequency (DTMF) dans Skype pour Business Server.
  
Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF). Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur micro ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone. 
  
Pour gérer les clés utilisées pour les commandes DTMF, utilisez le Skype pour Business Server Management Shell **, **Set-CsDialinConferencingDtmfConfiguration**et **Get-CsDialinConferencingDtmfConfiguration** Nouvelle-CsDialinConferencingDtmfConfiguration** applets de commande.
  
Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gestion du mappage des touches des commandes DTMF

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
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

Pour plus d’informations, voir [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)et [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
  

