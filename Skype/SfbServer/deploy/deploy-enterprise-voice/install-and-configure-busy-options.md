---
title: Installer et configurer les options Occupé pour Skype Entreprise Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/6/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Découvrez comment installer et configurer les Options de disponibilité dans Skype pour Business Server 2015.
ms.openlocfilehash: d4f8bc0dc26798371b8de70b8caa97abe116dc88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installer et configurer les options Occupé pour Skype Entreprise Server
 
Découvrez comment installer et configurer les Options de disponibilité dans Skype pour Business Server 2015.
  
Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016, qui vous permet de configurer la manière dont les appels entrants sont gérés lorsqu'un utilisateur participe déjà à un appel ou à une conférence, ou lorsqu'il a mis un appel en attente. Les nouveaux appels ou les appels entrants peuvent être rejetés avec une tonalité d’occupation ou sont transférés vers la messagerie vocale. 
  
Si Busy Options est activée pour l'organisation, l'ensemble des utilisateurs de l'entreprise, qu'il s'agisse des utilisateurs de Voix Entreprise ou non, peuvent utiliser les options de configuration suivantes :
  
- Busy on Busy : les nouveaux appels entrants seront rejetés avec une tonalité d’occupation si l'utilisateur est occupé.
    
- Voicemail on Busy : les nouveaux appels entrants seront transférés vers la messagerie si l'utilisateur est occupé.
    
Quelle que soit la manière dont ils ont configuré Busy Option, les utilisateurs participant à un appel ou une conférence, ou ceux ayant mis un appel en absence, peuvent toujours lancer de nouveaux appels ou de nouvelles conférences.   
  
Pour plus d’informations sur la fonctionnalité de disponibilité, voir [planifier des Options occupé pour Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).
  
## <a name="install"></a>Installation 

Vérifiez que vous avez la dernière version de Skype pour Business Server est installé et que vous avez installé le correctif le plus récent. Pour ce faire, tout d’abord arrêter tous les services et exécutez le Skype pour le programme d’installation de la mise à jour de Business Server comme suit :
  
1. Exécutez la commande Stop-CsWindowsService.
    
2. Exécutez le programme d'installation SkypeServerUpdateInstaller.exe sur chaque serveur frontal d’un pool.
    
3. Exécutez le programme d'installation SkypeServerUpdateInstaller.exe sur chaque serveur Survivable Branch Server si vous souhaitez prendre en charge le basculement sur SBS.
    
Le programme d’installation déploiera la version la plus récente de l’application Busy Options mais l’application n’est pas activée par défaut. Pour l'activer, procédez de la manière suivante :
  
1. Exécutez l’applet de commande [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) pour activer globalement les Options occupé comme indiqué dans l’exemple suivant :
    
  ```
  Set-CsVoicePolicy -EnableBusyOptions $true
  ```

2. Si une stratégie de voix est en place sur le site, activez ensuite Busy Options pour la stratégie de voix de la manière suivante :
    
    Tout d’abord, exécutez [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) pour récupérer le nom du site :
    
   ```
   Get-CsSite
   ```

    Utilisez la valeur d’identité (par exemple : Site : Redmond1) récupérées à partir de Get-CsSite pour récupérer la stratégie voice du site comme suit :
    
   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Si une stratégie de voix existe pour le site, exécutez la commande suivante :
    
   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Ensuite, exécutez l’applet de commande [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) pour ajouter des Options de disponibilité à la liste des applications de serveur comme indiqué dans l’exemple suivant :
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Vous devez remplacer le nom de domaine complet % avec le nom de domaine complet d’un pool spécifique. 
  
4. Ensuite, exécutez l’applet de commande [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) pour mettre à jour les rôles accès basé sur le rôle de contrôle (RBAC) pour les applets de commande Options occupé, comme illustré dans l’exemple suivant :
    
   ```
   Update-CsAdminRole
   ```

5. Enfin, démarrez le Skype pour les services métier serveur Windows sur tous les serveurs frontaux dans tous les pools où Options occupé a été installée et activée par l’exécution de la commande [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :
    
   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configuration

Pour configurer les Options de disponibilité, utilisez l’applet de commande [Set-CsBusyOptions](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .
  
Par exemple, la commande suivante configure la fonctionnalité Busy Options pour l'utilisateur « Ken Myer ». Dans cette configuration, les appels vers « Ken Myer » seront retournés avec une tonalité d’occupation lorsqu'il sera déjà en communication :
  
```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy

```

Dans l'exemple suivant, la commande configure la fonctionnalité Busy Options pour l'utilisateur « Chrystal Velasquez ». Dans cette configuration, les nouveaux appels entrants vers « Chrystal Velasquez » seront transférés vers la messagerie vocale lorsqu'elle sera déjà en communication :
  
```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy 

```

Vous pouvez récupérer les informations de configuration des Options de disponibilité à l’aide de l’applet de commande [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . L’exemple suivant renvoie le paramètre Options occupé pour « KenMyer@Contoso.com » :
  
```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Vous pouvez supprimer des Options de disponibilité à l’aide de l’applet de commande [Remove-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . La commande suivante supprime la fonctionnalité Busy Options pour « Ken Myer » :
  
```
Remove-CsBusyOptions -Identity "Ken Myer"

```

Pour obtenir des informations détaillées sur les applets de commande vous permet de configurer les Options de disponibilité, consultez le contenu du Guide de référence technique pour [Supprimer-CsBusyOptions](http://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx), [Get-CsBusyOptions](http://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)et [CsBusyOptions de l’ensemble](http://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).
  
## <a name="enable-logging"></a>Activation de la journalisation

Pour activer la journalisation pour la fonctionnalité Busy Options à l'aide de Centralized Logging Service, indiquez ce qui suit :
  
```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3} 

```

## <a name="verify-and-troubleshoot"></a>Vérification et dépannage

Après avoir installé les Options occupé, vous pouvez vérifier que l’installation a réussi à l’aide de l’applet de commande [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) pour récupérer la liste des applications de serveur. Si Busy Options est correctement installée, le résultat de l'applet de commande devrait afficher la configuration de Busy Options comme suit :
  
|||
|:-----|:-----|
|Identity   <br/> |  : Service:Registrar:pool0.vdomain.com/BusyOptions <br/> |
|Priority  <br/> | : 5 <br/> |
|Uri   <br/> |: http://www.microsoft.com/LCS/BusyOptions  <br/> |
|Nom  <br/> |  : BusyOptions <br/> |
|Activé  <br/> |: True  <br/> |
|Critique  <br/> |: False  <br/> |
|Nom_script  <br/> | : <br/> |
|Script   <br/> | : <br/> |
   
Vous pouvez également utiliser l’Observateur d’événements Windows pour vérifier que l’installation Options occupé a réussi et que Skype pour Business Server chargé avec succès les Options occupé. Pour vérifier la disponibilité des Options, ouvrez **l’Observateur d’événements -\> journaux des applications et Services -\> Skype (ou Lync) Server** et recherchez l’ID d’événement = 30253.
  

