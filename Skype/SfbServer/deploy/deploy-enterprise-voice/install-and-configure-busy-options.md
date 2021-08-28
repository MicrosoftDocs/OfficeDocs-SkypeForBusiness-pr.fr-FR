---
title: Installer et configurer Busy Options pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Découvrez comment installer et configurer Busy Options dans Skype Entreprise Server.
ms.openlocfilehash: 58c70360a9e25ccefcd62181ab5a1a5b222ae9a5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600679"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>Installer et configurer Busy Options pour Skype Entreprise Server

Découvrez comment installer et configurer Busy Options dans Skype Entreprise Server.

Busy Options est une nouvelle stratégie de voix introduite dans la mise à jour cumulative de juillet 2016 qui vous permet de configurer la façon dont les appels entrants sont gérés lorsqu’un utilisateur est déjà en cours d’appel ou de conférence ou qu’un appel est mis en attente. Les appels nouveaux ou entrants peuvent être rejetés avec une signal occupé ou transmis à la messagerie vocale.

Si Busy Options est activée pour l’organisation, tous les utilisateurs du Enterprise, les utilisateurs Voix Entreprise et non Voix Entreprise, peuvent utiliser les options de configuration suivantes :

- Occupé (occupé) : les nouveaux appels entrants sont rejetés avec une signal occupé si l’utilisateur est occupé.

- Messagerie vocale sur Busy : dans laquelle les nouveaux appels entrants sont transmis à la messagerie vocale si l’utilisateur est occupé.

Quelle que soit la manière dont les options de occupé(s) sont configurées, les utilisateurs d’un appel ou d’une conférence, ou ceux qui ont un appel en attente, ne sont pas empêchés de lancer de nouveaux appels ou conférences.

Pour plus d’informations sur la fonctionnalité Busy Options, voir [Plan for Busy Options for Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).

## <a name="install"></a>Installer

Assurez-vous que vous avez installé la dernière version de Skype Entreprise Server et que vous avez installé le correctif le plus récent. Pour ce faire, arrêtez d’abord tous les services, puis exécutez le programme d’installation Skype Entreprise Server mise à jour comme suit :

1. Exécutez la Stop-CsWindowsService commande.

2. Exécutez le programme SkypeServerUpdateInstaller.exe installer sur chaque serveur frontal d’un pool.

3. Exécutez le programme SkypeServerUpdateInstaller.exe sur chaque serveur Survivable Branch Server (SBS), si vous souhaitez assurer la prise en charge du failover sur SBS.

Le programme d’installation déploie la dernière version de l’application Busy Options. Toutefois, l’application n’est pas activée par défaut. Pour activer l’application, effectuez les étapes suivantes :

1. Exécutez [l’cmdlet Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) pour activer globalement Busy Options, comme illustré dans l’exemple suivant :

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. Ensuite, si une stratégie de voix est activée sur le site, vous devez activer Busy Options pour la stratégie de voix comme suit :

    Tout [d’abord, exécutez Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps) pour récupérer le nom du site :

   ```powershell
   Get-CsSite
   ```

    Utilisez la valeur Identity (par exemple : Site:Redmond1) extraite de Get-CsSite pour récupérer la stratégie de voix du site comme suit :

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    Si une stratégie de voix existe pour le site, exécutez la commande suivante :

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. Ensuite, exécutez l’cmdlet [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) pour ajouter Busy Options à la liste des applications serveur, comme illustré dans l’exemple suivant :

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > Vous devez remplacer %FQDN% par le nom de domaine complet d’un pool spécifique.

4. Ensuite, exécutez l’cmdlet [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) pour mettre à jour les rôles de contrôle d’accès basé sur un rôle (RBAC) pour les cmdlets Busy Options, comme illustré dans l’exemple suivant :

   ```powershell
   Update-CsAdminRole
   ```

5. Enfin, démarrez les services Skype Entreprise Server Windows sur tous les serveurs frontaux dans tous les pools où Busy Options a été installé et activé en exécutant la commande [Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps) :

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>Configurer

Pour configurer Busy Options, utilisez l’cmdlet [Set-CsBusyOptions.](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)

Par exemple, la commande suivante configure les options busy pour l’utilisateur « Ken Myer ». Dans cette configuration, tout appel à « Ken Myer » retourne une signal occupé lorsqu’il est déjà en appel :

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

Dans l’exemple suivant, la commande configure les options occupé pour l’utilisateur « Contrôletal Velasquez ». Dans cette configuration, les nouveaux appels entrants vers « Contrôletal Velasquez » sont transmis à la messagerie vocale lorsqu’elle est déjà en appel :

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

Vous pouvez récupérer des informations de configuration sur Busy Options à l’aide de l';cmdlet [Get-CsBusyOptions.](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) L’exemple suivant renvoie le paramètre Busy Options pour « KenMyer@Contoso.com » :

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

Vous pouvez supprimer Busy Options à l’aide de l’cmdlet [Remove-CsBusyOptions.](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) La commande suivante supprime Busy Options pour « Ken Myer » :

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

Pour plus d’informations sur les cmdlets que vous utilisez pour configurer Busy Options, voir le contenu de référence technique pour [Set-CsBusyOptions,](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)et [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).

## <a name="enable-logging"></a>Activer la journalisation

Pour activer la journalisation des options Busy à l’aide du service de journalisation centralisée, spécifiez les options suivantes :

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>Vérifier et résoudre les problèmes

Après avoir installé Busy Options, vous pouvez vérifier que l’installation a réussi à l’aide de l’cmdlet [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) pour récupérer la liste des applications serveur. Si Busy Options est correctement installée, la sortie de la cmdlet doit afficher la configuration Busy Options comme suit :

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

Vous pouvez également utiliser Windows’observateur d’événements pour vérifier que l’installation de Busy Options a réussi et Skype Entreprise Server options Busy correctement chargées. Pour vérifier Busy Options, ouvrez l’Observateur d’événements - Journaux des applications et des **\> services Skype \> (ou Lync) Server** et recherchez l’ID d’événement = 30253.