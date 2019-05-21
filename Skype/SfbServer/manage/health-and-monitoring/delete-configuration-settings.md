---
title: Suppression d’une collection de paramètres de configuration de CDR dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Résumé: Découvrez comment supprimer des paramètres de configuration de CDR dans Skype entreprise Server.'
ms.openlocfilehash: 91ee9676b3087c5b125c6cfe935f706bbfb22812
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305831"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Suppression d’une collection de paramètres de configuration de CDR dans Skype entreprise Server
 
**Résumé:** Découvrez comment supprimer des paramètres de configuration de CDR dans Skype entreprise Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype entreprise Server, une collection globale unique de paramètres de configuration de CDR est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global. Si vous supprimez les paramètres sur l’étendue Site, les enregistrements des détails des appels seront gérés dans ce site en utilisant les paramètres globaux.
  
Notez que vous pouvez également «supprimer» les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, la suppression par défaut est activée dans une collection de paramètres de configuration CDR. Supposons que vous modifiez la collection globale pour que la purge soit désactivée. Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que la purge sera de nouveau activée.
  
Vous pouvez supprimer des paramètres de configuration de CDR en utilisant le panneau de configuration Skype entreprise Server ou l’applet de commande [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration de CDR dans le panneau de configuration Skype entreprise Server

1. Dans le panneau de configuration Skype entreprise Server, cliquez sur **surveillance et archivage**. 
    
2. Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.
    
3. Cliquez sur **Modifier**, puis sur **Supprimer**.
    
4. Dans la boîte de dialogue panneau de configuration Skype entreprise Server, cliquez sur **OK**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de CDR à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez supprimer des paramètres de configuration de l’enregistrement des détails des appels à l’aide de Windows PowerShell et de l’applet de contrôle **Remove-CsCdrConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [«démarrage rapide: gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.
  
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

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi

[Effacement manuel des bases de données de l’enregistrement des détails des appels et de la qualité de l’activité dans Skype entreprise Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

