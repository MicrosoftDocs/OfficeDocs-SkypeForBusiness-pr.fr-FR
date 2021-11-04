---
title: 'Skype Entreprise Server : supprimer une collection existante de paramètres de configuration de la trunk SIP'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Résumé : Découvrez comment supprimer une collection de paramètres de configuration de Skype Entreprise Server panneau de configuration.'
ms.openlocfilehash: 19de05f2b31bc7a083aca7a04d71c32f17d0ea85
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771539"
---
# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype Entreprise Server : supprimer une collection existante de paramètres de configuration de la trunk SIP 
 
**Résumé :** Découvrez comment supprimer une collection de paramètres de configuration de Skype Entreprise Server panneau de configuration.
  
Les paramètres de configuration de la trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un PBX (IP-Public Branch eXchange) ou un contrôleur SBC (Session Border Controller) chez le fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :
  
- Si le contournement de média doit être activé sur les trunks
    
- Conditions dans lesquelles les paquets RTCP (Realtime Transport Control Protocol) sont envoyés
    
- Si le chiffrement SRTP (Secure Realtime Transport Protocol) est requis sur chaque trunk
    
Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. Cette collection globale de paramètres ne peut pas être supprimée. Toutefois, vous pouvez utiliser le Panneau de configuration Skype Entreprise Server ou l’cmdlet [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) pour « réinitialiser » les valeurs par défaut des propriétés de la collection globale. Par exemple, si vous avez définie la propriété Enable3pccRefer sur True, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer rétablit sa valeur par défaut false.
  
Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle PSTN individuelle) ; ces paramètres personnalisés peuvent être supprimés. Lorsque vous supprimez ces paramètres personnalisés, gardez les éléments suivants à l’esprit :
  
- Si vous supprimez des paramètres étendus à un service, la jonction SIP gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.
    
- Si vous supprimez des paramètres d’étendue site, toutes les trunks SIP gérées par ces paramètres sont désormais gérées par la collection globale de paramètres de configuration de la trunk.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration de la Skype Entreprise Server panneau de configuration

1. Dans Skype Entreprise Server panneau de configuration, cliquez sur **Routage** des voix, puis sur **Configuration de la trunk .**
    
2. Sous **l’onglet Configuration** de la trunk, sélectionnez la collection de paramètres de configuration de la trunk SIP à supprimer, cliquez sur **Modifier,** puis cliquez sur **Supprimer**. Pour supprimer plusieurs collections dans la même opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl plus bas, puis cliquez sur les autres collections à supprimer.
    
3. La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.
    
4. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.
    
5. Dans la **boîte Skype Entreprise Server panneau de bord,** cliquez sur **OK.**
    
6. Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **Valider**, puis sur **Annuler toutes les modifications non validées**. Lorsque la **boîte Skype Entreprise Server panneau de Skype Entreprise Server** s’affiche, cliquez sur **OK.**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Suppression des paramètres de configuration de Paramètres à l’aide des cmdlets Skype Entreprise Server Management Shell

Vous pouvez supprimer les paramètres de configuration de la Skype Entreprise Server Management Shell et l’cmdlet **Remove-CsTrunkConfiguration.** Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Skype Entreprise Server Management Shell.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Pour supprimer une collection spécifiée de paramètres

- La commande suivante supprime les paramètres de configuration de jonction appliqués au site Redmond :
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Pour supprimer toutes les collections appliquées à l’étendue Site

- Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Pour supprimer toutes les collections où le contournement de média est activé

- La commande suivante supprime tous les paramètres de configuration de jonction dès lors que le contournement de média est activé :
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsTrunkConfiguration.](/powershell/module/skype/remove-cstrunkconfiguration)
