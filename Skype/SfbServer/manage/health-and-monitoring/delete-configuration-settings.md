---
title: Supprimer une collection existante de paramètres de configuration CDR dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration CDR dans Skype pour Business Server.'
ms.openlocfilehash: 470aade77fce211ba771c628b913efa4376a4a6f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873076"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Supprimer une collection existante de paramètres de configuration CDR dans Skype pour Business Server
 
**Résumé :** Découvrez comment supprimer les paramètres de configuration CDR dans Skype pour Business Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype pour Business Server, une seule collection globale des paramètres de configuration CDR est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global. Si vous supprimez les paramètres sur l’étendue Site, les enregistrements des détails des appels seront gérés dans ce site en utilisant les paramètres globaux.
  
Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, par défaut le vidage est activé dans une collection de paramètres de configuration CDR. Supposons que vous modifiez la collection globale pour que la purge soit désactivée. Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que la purge sera de nouveau activée.
  
Vous pouvez supprimer les paramètres de configuration des détails des appels à l’aide de la Skype pour le panneau de configuration serveur Business ou l’applet de commande [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration CDR avec Skype pour Business Server Control Panel

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **surveillance et archivage**. 
    
2. Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.
    
3. Cliquez sur **Modifier**, puis sur **Supprimer**.
    
4. Dans Skype pour la boîte de dialogue Panneau de configuration de Business Server, cliquez sur **OK**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration CDR à l’aide d’applets de commande Windows PowerShell

Vous pouvez supprimer des détails des appels d’enregistrement des paramètres de configuration à l’aide de Windows PowerShell et l’applet de commande **Remove-CsCdrConfiguration** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Pour supprimer une collection spécifique de paramètres de configuration CDR

 Cette commande supprime les paramètres de configuration CDR appliqués au site Redmond :
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration CDR appliqués au niveau du site

 Cette commande supprime tous les paramètres de configuration CDR appliqués au niveau du site :
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Pour supprimer tous les paramètres de configuration CDR qui désactivent l’enregistrement des détails des appels

 Cette commande supprime tous les paramètres de configuration CDR pour lesquels l’enregistrement des détails des appels a été désactivé :
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi

[Vider manuellement l’enregistrement des détails des appels et les bases de données de qualité de l’expérience dans Skype pour Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

