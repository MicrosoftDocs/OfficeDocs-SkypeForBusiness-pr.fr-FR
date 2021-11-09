---
title: Supprimer une collection existante de paramètres de configuration d’Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration de l’Skype Entreprise Server.'
ms.openlocfilehash: 8218d0b51045d3962825555bd5b248cb58262a37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854318"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Supprimer une collection existante de paramètres de configuration d’Skype Entreprise Server
 
**Résumé :** Découvrez comment supprimer les paramètres de configuration de l’Skype Entreprise Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype Entreprise Server, une collection unique et globale de paramètres de configuration d’cdr est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par défaut, les paramètres configurés au niveau du site ont priorité sur les paramètres configurés au niveau global. Si vous supprimez les paramètres au niveau du site, l’enregistrement des détails des appels sera géré dans ce site à l’aide des paramètres globaux.
  
Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, la purge par défaut est activée dans une collection de paramètres de configuration d’cdr. Supposons que vous modifiez la collection globale pour que la purge soit désactivée. Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que la purge sera de nouveau activée.
  
Vous pouvez supprimer les paramètres de configuration de l’Skype Entreprise Server à l’aide du Panneau de configuration Skype Entreprise Server ou de l’cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration d’Skype Entreprise Server cdr avec le Panneau de configuration

1. Dans Skype Entreprise Server de contrôle, cliquez **sur Surveillance et archivage.** 
    
2. Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.
    
3. Cliquez sur **Modifier**, puis sur **Supprimer**.
    
4. Dans la boîte Skype Entreprise Server de dialogue Panneau de Skype Entreprise Server, cliquez sur **OK.**
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration cdR à l’Windows PowerShell cmdlets

Vous pouvez supprimer les paramètres de configuration de l’enregistrement des détails des appels à l’aide Windows PowerShell’une cmdlet **Remove-CsCdrConfiguration.** Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Pour supprimer une collection spécifique de paramètres de configuration CDR

 Cette commande supprime les paramètres de configuration CDR appliqués au site Redmond :
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration d’cdr appliqués à l’étendue Site

 Cette commande supprime tous les paramètres de configuration CDR appliqués au niveau du site :
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Voir aussi

[Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)