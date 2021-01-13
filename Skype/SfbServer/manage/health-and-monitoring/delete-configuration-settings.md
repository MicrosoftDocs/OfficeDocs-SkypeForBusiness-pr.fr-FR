---
title: Supprimer une collection existante de paramètres de configuration cdR dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration de l’cdr dans Skype Entreprise Server.'
ms.openlocfilehash: ca6691d6a1a19e0d9219a256986b683b719da885
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816964"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Supprimer une collection existante de paramètres de configuration cdR dans Skype Entreprise Server
 
**Résumé :** Découvrez comment supprimer les paramètres de configuration de l’cdr dans Skype Entreprise Server.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype Entreprise Server, une collection unique et globale de paramètres de configuration d’cdr est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par défaut, les paramètres configurés au niveau du site ont priorité sur les paramètres configurés au niveau global. Si vous supprimez les paramètres au niveau du site, l’enregistrement des détails des appels sera géré dans ce site à l’aide des paramètres globaux.
  
Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, la purge par défaut est activée dans une collection de paramètres de configuration d’cdr. Supposons que vous modifiez la collection globale pour que la purge soit désactivée. Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que la purge sera de nouveau activée.
  
Vous pouvez supprimer les paramètres de configuration de l’cdr à l’aide du Panneau de configuration skype entreprise server ou de l';cmdlet [Remove-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration de l’cdr avec le Panneau de configuration de Skype Entreprise Server

1. Dans le Panneau de contrôle Skype Entreprise Server, cliquez **sur Surveillance et archivage.** 
    
2. Sous l’onglet **Enregistrement des détails des appels**, sélectionnez la collection (ou les collections) de paramètres CDR à supprimer. Pour sélectionner plusieurs collections, cliquez sur la première collection, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres.
    
3. Cliquez sur **Modifier**, puis sur **Supprimer**.
    
4. Dans la boîte de dialogue Panneau de contrôle Skype Entreprise Server, cliquez sur **OK.**
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration d’un cdr à l’Windows PowerShell cmdlets

Vous pouvez supprimer les paramètres de configuration de l’enregistrement des détails des appels à l’Windows PowerShell et à l’aide de **l';remove-cscdrconfiguration.aspx.** Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.
  
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

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Voir aussi

[Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

