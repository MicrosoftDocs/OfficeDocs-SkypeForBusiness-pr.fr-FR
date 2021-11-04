---
title: Gérer le mappage de touches pour les commandes DTMF dans Skype Entreprise Server
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
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Résumé : Découvrez comment gérer le mappage de touches des commandes DTMF (dual-tone multi-frequency) dans Skype Entreprise Server.'
ms.openlocfilehash: bd9f5b4e4560d3b89e713782ad2e8a19991a1382
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763852"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Gérer le mappage de touches pour les commandes DTMF dans Skype Entreprise Server
 
**Résumé :** Découvrez comment gérer le mappage de touches des commandes DTMF (dual-tone multi-frequency) dans Skype Entreprise Server.
  
Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF). Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur microphone ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone. 
  
Pour gérer les clés utilisées pour les commandes DTMF, utilisez l’Skype Entreprise Server Management Shell avec les cmdlets **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** et **New-CsDialinConferencingDtmfConfiguration.**
  
Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux. 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>Gérer le mappage de touches des commandes DTMF

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle Cs-ServerAdministratorr ou CsAdministrator.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Pour afficher les paramètres DTMF utilisés pour les conférences téléphoniques, exécutez la commande suivante à l’invite de commandes :
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. Pour modifier les paramètres DTMF utilisés pour les conférences téléphoniques, exécutez l’cmdlet suivante et spécifiez la touche à utiliser pour chaque option à modifier :
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (Facultatif) Si vous voulez créer des jeux de commandes DTMF supplémentaires pour des sites spécifiques, utilisez la cmdlet **New-CsDialinConferencingDtmfConfiguration** avec une identité de site.
    
L’exemple suivant permute la touche qui est activée pour activer ou désactiver les annonces et la touche qui est activée pour activer et désactiver le son de tous les participants. Étant donné qu’aucune identité n’est spécifiée, ces modifications s’appliquent aux paramètres DTMF globaux :
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

Pour plus d’informations, voir [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)et [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).
