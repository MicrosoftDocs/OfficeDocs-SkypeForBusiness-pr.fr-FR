---
title: Supprimer les paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Résumé : Découvrez comment supprimer les paramètres de qualité de l’expérience (QoE) dans Skype Entreprise Server.'
ms.openlocfilehash: 48936c21a4d50297bd5ba6e0546648148a16eb8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402018"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Supprimer les paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server
 
**Résumé :** Découvrez comment supprimer les paramètres de qualité de l’expérience (QoE) dans Skype Entreprise Server.
  
Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.
  
Lorsque vous installez Skype Entreprise Server, une collection unique et globale de paramètres de configuration QoE est créée pour vous. Les administrateurs peuvent également créer des collections de paramètres personnalisés pouvant être appliquées aux sites individuels. Par conception, les paramètres configurés sur l’étendue Site sont prioritaires sur les paramètres configurés sur l’étendue Global. Si vous supprimez les paramètres sur l’étendue Site, la QoE sera gérée dans ce site en utilisant les paramètres globaux.
  
Notez que vous pouvez également « supprimer » les paramètres globaux. Cependant, les paramètres globaux ne seront pas réellement supprimés. Toutes les propriétés de la collection seront en revanche réinitialisées à leurs valeurs par défaut. Par exemple, la purge est activée par défaut dans une collection de paramètres de configuration QoE. Supposons que vous modifiez la collection globale pour que la purge soit désactivée. Si vous supprimez ultérieurement les paramètres globaux, toutes les propriétés seront réinitialisées à leurs valeurs par défaut. Dans ce cas, cela signifie que la purge sera de nouveau activée.
  
Vous pouvez supprimer les paramètres de configuration QoE à l’aide du Panneau de configuration Skype Entreprise Server ou de l’cmdlet [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour supprimer les paramètres de configuration QoE à l’aide Skype Entreprise Server Panneau de configuration

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.
    
4. Sur la page **Données QoE**, cliquez sur la stratégie de votre choix, puis sur **Modifier**, et enfin sur **Supprimer**.
    
5. Cliquez sur **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration QoE Paramètres l’aide Windows PowerShell cmdlets

Vous pouvez supprimer les paramètres de configuration QoE à l’aide **Windows PowerShell’une cmdlet Remove-CsQoEConfiguration**. Vous pouvez exécuter cette cmdlet à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distants pour vous connecter à Skype Entreprise Server, voir [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Pour supprimer une collection spécifiée de paramètres de configuration QoE

 Cette commande supprime les paramètres de configuration QoE appliqués au site Redmond :
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration QoE appliqués à l’étendue Site

 Cette commande supprime tous les paramètres de configuration QoE appliqués à l’étendue Site :
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Pour supprimer tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé

 Cette commande supprime tous les paramètres de configuration QoE lorsque le suivi QoE est désactivé :
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Pour plus d’informations, [voir Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Voir aussi

[Vider manuellement les bases de données d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)