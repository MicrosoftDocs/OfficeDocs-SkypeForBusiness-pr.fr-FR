---
title: Supprimer les paramètres de configuration de la qualité de l’expérience dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Résumé : Découvrez comment supprimer les paramètres de qualité de l’expérience (QoE) dans Skype pour Business Server.'
ms.openlocfilehash: a0ed68fa6670f66512023e1dcf0754be5e95ed53
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21029408"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Supprimer les paramètres de configuration de la qualité de l’expérience dans Skype pour Business Server
 
**Résumé :** Découvrez comment supprimer les paramètres de qualité de l’expérience (QoE) dans Skype pour Business Server.
  
Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.
  
Lorsque vous installez Skype pour Business Server, une seule collection globale des paramètres de configuration QoE est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global. Si vous supprimez les paramètres sur l’étendue Site, la QoE sera gérée dans ce site en utilisant les paramètres globaux.
  
Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, la purge est activée par défaut dans une collection de paramètres de configuration QoE. Supposons que vous modifiez la collection globale pour que la purge soit désactivée. Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que la purge sera de nouveau activée.
  
Vous pouvez supprimer les paramètres de configuration QoE en utilisant le Skype pour le panneau de configuration serveur Business ou à l’aide de l’applet de commande [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration QoE à l’aide de Skype pour Business Server Control Panel

1.  Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir **Delegate Setup Permissions**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.
    
4. Sur la page **Données QoE**, cliquez sur la stratégie de votre choix, puis sur **Modifier**, et enfin sur **Supprimer**.
    
5. Cliquez sur **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de Configuration QoE à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration QoE à l’aide de Windows PowerShell et l’applet de commande **Remove-CsQoEConfiguration** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Pour supprimer une collection spécifiée de paramètres de configuration QoE

 Cette commande supprime les paramètres de configuration QoE appliqués au site Redmond :
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration QoE appliqués à l’étendue Site

 Cette commande supprime tous les paramètres de configuration QoE appliqués à l’étendue Site :
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Pour supprimer tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé

 Cette commande supprime tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé :
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Pour plus d’informations, voir [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Voir aussi

[Vider manuellement l’enregistrement des détails des appels et les bases de données de qualité de l’expérience dans Skype pour Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

