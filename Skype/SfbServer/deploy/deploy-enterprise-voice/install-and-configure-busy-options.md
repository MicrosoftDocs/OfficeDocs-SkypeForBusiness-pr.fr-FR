---
title: Installer et configurer les options Occupé pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Découvrez comment installer et configurer les options occupées dans Skype entreprise Server.
ms.openlocfilehash: dd22d07bcabc86b0d16f3ad1029087b659a3e4a5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767217"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installer et configurer les options Occupé pour Skype Entreprise Server

Découvrez comment installer et configurer les options occupées dans Skype entreprise Server.

Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016, qui vous permet de configurer la manière dont les appels entrants sont gérés lorsqu'un utilisateur participe déjà à un appel ou à une conférence, ou lorsqu'il a mis un appel en attente. Les nouveaux appels ou les appels entrants peuvent être rejetés avec une tonalité d’occupation ou sont transférés vers la messagerie vocale.

Si Busy Options est activée pour l'organisation, l'ensemble des utilisateurs de l'entreprise, qu'il s'agisse des utilisateurs de Voix Entreprise ou non, peuvent utiliser les options de configuration suivantes :

- Busy on Busy : les nouveaux appels entrants seront rejetés avec une tonalité d’occupation si l'utilisateur est occupé.

- Voicemail on Busy : les nouveaux appels entrants seront transférés vers la messagerie si l'utilisateur est occupé.

Quelle que soit la manière dont ils ont configuré Busy Option, les utilisateurs participant à un appel ou une conférence, ou ceux ayant mis un appel en absence, peuvent toujours lancer de nouveaux appels ou de nouvelles conférences.  

Pour plus d'informations sur la fonctionnalité Busy Options, reportez-vous à la rubrique [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installation 

Vérifiez que vous avez installé la dernière version de Skype entreprise Server et que vous avez installé le correctif le plus récent. Pour ce faire, commencez par arrêter tous les services, puis exécutez le programme d’installation de la mise à jour de Skype entreprise Server comme suit :

1. Exécutez la commande Stop-CsWindowsService.

2. Exécutez le programme d'installation SkypeServerUpdateInstaller.exe sur chaque serveur frontal d’un pool.

3. Exécutez le programme d'installation SkypeServerUpdateInstaller.exe sur chaque serveur Survivable Branch Server si vous souhaitez prendre en charge le basculement sur SBS.

Le programme d’installation déploiera la version la plus récente de l’application Busy Options mais l’application n’est pas activée par défaut. Pour l'activer, procédez de la manière suivante :

1. Exécutez l’applet de commande [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) pour activer globalement les options Busy comme le montre l’exemple suivant :

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Si une stratégie de voix est en place sur le site, activez ensuite Busy Options pour la stratégie de voix de la manière suivante :

    Tout d’abord, exécutez [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) pour récupérer le nom du site :

   ```powershell
   Get-CsSite
   ```

    Utilisez la valeur d’identité (par exemple : site : Redmond1) récupérée à partir de Get-CsSite pour récupérer la stratégie de voix du site comme suit :

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Si une stratégie de voix existe pour le site, exécutez la commande suivante :

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Ensuite, exécutez l’applet de commande [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) pour ajouter des options occupées à la liste des applications serveur, comme le montre l’exemple suivant :

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Vous devez remplacer% FQDN% par le nom de domaine complet d’un pool spécifique.

4. Ensuite, exécutez l’applet de commande [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) pour mettre à jour les rôles de contrôle d’accès basés sur les rôles (RBAC) pour les applets de commande d’options occupées comme illustré dans l’exemple suivant :

   ```powershell
   Update-CsAdminRole
   ```

5. Pour finir, démarrez les services Windows de Skype entreprise Server sur tous les serveurs frontaux de tous les pools pour lesquels les options occupées ont été installées et activées en exécutant la commande [Démarrer-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configuration

Pour configurer la fonctionnalité Busy Options, utilisez l'applet de commande [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  

Par exemple, la commande suivante configure la fonctionnalité Busy Options pour l'utilisateur « Ken Myer ». Dans cette configuration, les appels vers « Ken Myer » seront retournés avec une tonalité d’occupation lorsqu'il sera déjà en communication :

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Dans l'exemple suivant, la commande configure la fonctionnalité Busy Options pour l'utilisateur « Chrystal Velasquez ». Dans cette configuration, les nouveaux appels entrants vers « Chrystal Velasquez » seront transférés vers la messagerie vocale lorsqu'elle sera déjà en communication :

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Vous pouvez récupérer les informations relatives à la configuration de Busy Options à l'aide de l'applet de commande [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx). L’exemple suivant retourne le paramètre d’options Busy pour « KenMyer@Contoso.com » :

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Vous pouvez supprimer Busy Options à l'aide de l'applet de commande [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx). La commande suivante supprime la fonctionnalité Busy Options pour « Ken Myer » :

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Pour plus d’informations sur les applets de passe que vous utilisez pour configurer les options occupées, consultez le contenu de référence technique pour [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)et [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Activation de la journalisation

Pour activer la journalisation pour la fonctionnalité Busy Options à l'aide de Centralized Logging Service, indiquez ce qui suit :

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Vérification et dépannage

Après avoir installé les options occupées, vous pouvez vérifier que l’installation a réussi à l’aide de l’applet de contrôle [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) pour récupérer la liste des applications serveur. Si Busy Options est correctement installée, le résultat de l'applet de commande devrait afficher la configuration de Busy Options comme suit :

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

Vous pouvez également utiliser l’observateur d’événements Windows pour vérifier que l’installation des options occupées a réussi et que Skype entreprise Server a correctement chargé les options occupées. Pour vérifier les options occupées, ouvrez **Observateur\> d’événements-journaux d'\> application et de services-Skype (ou Lync) Server** et recherchez l’ID d’événement = 30253.
