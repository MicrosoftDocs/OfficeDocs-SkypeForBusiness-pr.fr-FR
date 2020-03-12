---
title: Installer et configurer Busy options pour Skype entreprise Server
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
description: Découvrez comment installer et configurer Busy options dans Skype entreprise Server.
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604211"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installer et configurer Busy options pour Skype entreprise Server

Découvrez comment installer et configurer Busy options dans Skype entreprise Server.

Busy options est une nouvelle stratégie de voix introduite dans la mise à jour cumulative de juillet 2016 qui vous permet de configurer le mode de traitement des appels entrants lorsqu’un utilisateur est déjà dans un appel ou une conférence ou lorsqu’un appel est mis en attente. Les nouveaux appels ou les appels entrants peuvent être rejetés avec un signal occupé ou transférés vers la messagerie vocale.

Si Busy options est activée pour l’organisation, tous les utilisateurs de l’entreprise, qu’il s’agisse des utilisateurs de voix entreprise ou non, peuvent utiliser les options de configuration suivantes :

- Busy on Busy : les nouveaux appels entrants seront rejetés avec un signal occupé si l’utilisateur est occupé.

- Messagerie vocale sur occupé : dans lequel les nouveaux appels entrants seront transférés vers la messagerie vocale si l’utilisateur est occupé.

Quelle que soit la façon dont les options occupées sont configurées, les utilisateurs d’un appel ou d’une conférence, ou ceux ayant mis un appel en attente, ne sont pas autorisés à lancer de nouveaux appels ou de nouvelles conférences.

Pour plus d’informations sur la fonctionnalité Busy options, reportez-vous à la rubrique [plan for Busy options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installer

Assurez-vous que la dernière version de Skype entreprise Server est installée et que vous avez installé le correctif le plus récent. Pour ce faire, arrêtez tous les services, puis exécutez le programme d’installation de la mise à jour de Skype entreprise Server comme suit :

1. Exécutez la commande Stop-CsWindowsService.

2. Exécutez le programme d’installation d’installation skypeserverupdateinstaller. exe sur chaque serveur frontal d’un pool.

3. Exécutez le programme d’installation de installation skypeserverupdateinstaller. exe sur chaque serveur Survivable Branch Server (SBS), si vous voulez garantir la prise en charge du basculement sur SBS.

Le programme d’installation déploiera la dernière version de l’application options Busy. Toutefois, l’application n’est pas activée par défaut. Pour activer l’application, procédez comme suit :

1. Exécutez l’applet de commande [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) pour activer les options Busy de manière globale, comme illustré dans l’exemple suivant :

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Ensuite, si le site possède une stratégie de voix, vous devez activer la fonctionnalité Busy options pour la stratégie de voix comme suit :

    Tout d’abord, exécutez [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) pour récupérer le nom du site :

   ```powershell
   Get-CsSite
   ```

    Utilisez la valeur IDENTITY (par exemple : site : Redmond1) extrait de Get-CsSite pour récupérer la stratégie de voix du site comme suit :

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    S’il existe une stratégie de voix pour le site, exécutez la commande suivante :

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Ensuite, exécutez la cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) pour ajouter des options Busy à la liste des applications serveur, comme illustré dans l’exemple suivant :

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Vous devez remplacer% FQDN% par le nom de domaine complet d’un pool spécifique.

4. Ensuite, exécutez la cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) pour mettre à jour les rôles RBAC (contrôle d’accès basé sur un rôle) pour les applets de commande Busy options comme illustré dans l’exemple suivant :

   ```powershell
   Update-CsAdminRole
   ```

5. Enfin, démarrez les services Windows Skype entreprise Server sur tous les serveurs frontaux de tous les pools où Busy options a été installé et activé en exécutant la commande [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurer

Pour configurer Busy options, utilisez la cmdlet [Set-applet csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .

Par exemple, la commande suivante configure la fonctionnalité Busy options pour l’utilisateur « Ken Myer ». Dans cette configuration, tout appel à « Ken Myer » renverra un signal occupé lorsqu’il est déjà en communication :

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Dans l’exemple suivant, la commande configure la fonctionnalité Busy options pour l’utilisateur « Chrystal Velasquez ». Dans cette configuration, les nouveaux appels entrants vers « Chrystal Velasquez » seront transférés vers la messagerie vocale lorsqu’elle sera déjà en communication :

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Vous pouvez récupérer des informations de configuration sur les options occupées à l’aide de la cmdlet [Get-applet csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) . L’exemple suivant renvoie le paramètre Busy options pour « KenMyer@Contoso.com » :

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Vous pouvez supprimer les options Busy à l’aide de l’applet de commande [Remove-applet csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) . La commande suivante supprime les options Busy pour « Ken Myer » :

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Pour obtenir des informations détaillées sur les applets de commande que vous utilisez pour configurer Busy options, consultez le contenu de référence technique pour [Set-applet csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-applet csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)et [Remove-applet csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Activer la journalisation

Pour activer la journalisation des options occupées à l’aide du service de journalisation centralisée, spécifiez les éléments suivants :

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Vérifier et résoudre les problèmes

Après avoir installé Busy options, vous pouvez vérifier que l’installation a réussi à l’aide de la cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) pour récupérer la liste des applications serveur. Si Busy options est correctement installée, la sortie de l’applet de commande doit afficher la configuration Busy options comme suit :

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

Vous pouvez également utiliser l’observateur d’événements Windows pour vérifier que l’installation des options occupées a réussi et que Skype entreprise Server a correctement chargé les options occupées. Pour vérifier Busy options, ouvrez l' **Observateur d'\> événements-journaux des applications\> et des services-serveur Skype (ou Lync) Server** et recherchez l’ID d’événement = 30253.
