---
title: Salles Microsoft Teams maintenance et opérations
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Lisez cette rubrique pour en savoir plus sur la gestion des Salles Microsoft Teams.
ms.openlocfilehash: be5f183e593ca1723383b6834c9ff5cad387b42f
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62298989"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Salles Microsoft Teams maintenance et opérations
 
Lisez cette rubrique pour en savoir plus sur la gestion des Salles Microsoft Teams.
  
Salles Microsoft Teams solution de conférence de Microsoft est conçue pour transformer votre salle de réunion en une expérience de collaboration enrichie et collaborative. Les utilisateurs apprécieront son interface utilisateur familière Microsoft Teams ou Skype Entreprise et les administrateurs informatiques apprécieront une application de gestion et de déploiement Windows 10 salles Teams facile. Salles Microsoft Teams est conçu pour tirer parti d’équipements existants afin de faciliter l’installation pour Microsoft Teams des Skype Entreprise dans votre salle de réunion.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Collecte des journaux sur Salles Microsoft Teams
<a name="Logs"> </a>

Pour collecter les journaux dans Teams centre d’administration, voir Teams **appareils connectés > salles Teams sur Windows**. Sélectionnez le nom d’affichage de l’appareil pour qui vous voulez ouvrir les journaux. Dans le panneau supérieur, sélectionnez « Télécharger les journaux de l’appareil ». Une fois que vous avez confirmé, les journaux seront prêts à être téléchargés dans l’onglet Historique après quelques minutes.

Vous pouvez également utiliser PowerShell pour recueillir des journaux. Vous devez appeler le script de collection journal qui est intégré à l Salles Microsoft Teams applédit. En [mode d’administration](rooms-operations.md), démarrez une invite de commandes avec élévation de privilèges, puis lancez la commande suivante :
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Les journaux seront produits sous forme de fichier ZIP dans c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Paramètres de l’écran d’affichage
<a name="Display"> </a>

Configurez les paramètres de votre ou vos écrans avant de salle pour prendre en charge le contrôle électronique du consommateur ou activer le mode PC.
  
Si vous souhaitez qu’un écran avant de la salle bascule automatiquement en mode salles Teams à la fin du mode veille, certaines conditions doivent être remplies. Cette fonctionnalité est facultative mais prise en charge Salles Microsoft Teams logiciel, à condition que le matériel sous-jacent la prend en charge. Un téléviseur grand public utilisé comme avant d’affichage doit prendre en charge la fonctionnalité CEC (Consumer Electronics Control) de HDMI.  En fonction de la station d’accueil ou de la console sélectionnée (qui ne peut pas prendre en charge la cec, consultez la documentation du support technique du fabricant), un contrôleur tel qu’un [contrôleur HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) d’Extron peut être nécessaire pour activer le comportement souhaité.

### <a name="change-scale-and-resolution"></a>Modifier l’échelle et la résolution

Si la taille de police sur l’écran avant de la salle est trop grande ou trop petite, vous devez ajuster la résolution de l’écran. 

1. Basculer en [mode d’administration](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Sélectionnez l’icône de démarrage. Puis, **Paramètres > affichage > système**

3. Allez à **l’échelle** et la disposition, puis **modifiez** la taille du texte, des applications et d’autres éléments, et définissez la mise à l’échelle sur 100 %.

4. Définissez la résolution d’affichage sur 1080p. Si vous avez deux moniteurs, définissez l’échelle et la résolution pour les deux écrans.

5. Sélectionnez ensuite l’icône Démarrer, puis entrez **Invite de commandes**. Sélectionnez **Exécuter en tant qu’administrateur**.

6. Exécutez la commande suivante :

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Salles Microsoft Teams (Restauration d’usine)
<a name="Reset"> </a>

Si Salles Microsoft Teams fonctionne pas bien, la réinitialisation aux usine peut vous aider. Pour ce faire, utilisez l’outil [Microsoft Teams récupération](recovery-tool.md) de salle et suivez les instructions de restauration d’usine.

> [!NOTE]
> Il existe un problème connu où le Salles Microsoft Teams peut devenir inutilisable si l’option Conserver mes fichiers - Supprime les applications et les **paramètres,** mais conserve vos fichiers personnels est sélectionnée pendant le Windows réinitialiser. *N’utilisez* pas cette option.
  
## <a name="supported-remote-options"></a>Options distantes prises en charge
<a name="RemoteOptions"> </a>

Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.
  

|Groupe de travail |Aucun domaine joint|Domaine joint|
|:-----|:-----|:-----|
|Redémarrer  <br/> |Teams d’administration  <br/> Bureau distant  <br/> Remote PowerShell  <br/> | <br/>Bureau à distance (nécessite une configuration plus particulière)  <br/> Remote PowerShell (nécessite une configuration plus particulière)  <br/> Configuration Manager  <br/> |
|Mise à jour du SE  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Mise à jour de l';application  <br/> |	Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Account Config  <br/> |Teams d’administration  <br/> |Teams d’administration  <br/> |
|Accès aux journaux  <br/> |Teams d’administration  <br/> PowerShell  <br/> |Teams d’administration <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuration d’une stratégie de groupe pour Salles Microsoft Teams
<a name="GroupPolicy"> </a>

Cette section couvre les paramètres système dont Salles Microsoft Teams dépend pour fonctionner correctement. 

La participation salles Teams à un domaine Active Directory offre les avantages suivants :

- Le fait de rejoindre un salles Teams vous permet d’accorder aux utilisateurs de domaine et aux groupes des droits d’administration. En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.

- Vous pouvez déployer Windows configuration de la qualité de service sur salles Teams.

- Si vous utilisez Skype Entreprise, le fait de rejoindre le salles Teams automatise l’importation de la chaîne de certificats racine privée de votre organisation.

Lorsque vous rejoignez salles Teams à un domaine, vous devez créer une unité organisationnelle distincte, afin de pouvoir fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où se trouvent tous les objets salles Teams. Désactivez tout l’héritage des stratégies de groupe de sorte que les paramètres de stratégie de groupe non pris en salles Teams. Créez des objets machine dans l’ou avant de salles Teams au domaine pour vous assurer que les stratégies de groupe appliquées aux ordinateurs par défaut ne sont pas appliquées.

> [!NOTE]
> Même si vous créez une ou plusieurs stratégies de groupe distinctes et bloquez l’héritage, certaines stratégies de groupe peuvent entraîner des problèmes si elles n’ont pas de jeu de remplacement. Une stratégie de groupe sans remplacement remplace une stratégie d’ou ou avec un ensemble d’héritage de stratégie de blocage.

De nombreuses organisations ont les stratégies de groupe suivantes, qui affectent salles Teams fonctionnalités. Veillez à annuler ou bloquer l’héritage des éléments ci-après :

  - Délai d’ouverture de sessions (verrouillage automatique)
  - Stratégies connexes de gestion de l’alimentation
  - Besoin d’étapes d’authentification supplémentaires
  - Accès aux lecteurs locaux refusé
  - Inviter les utilisateurs à des connexions réseau lentes
  - Démarrer un programme donné à l’ouverture
  - Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.
  - Push Windows Update to salles Teams

Lorsque vous rejoignez Salles Microsoft Teams à un domaine, assurez-vous que vos stratégies de groupe ne remplacent pas les paramètres du tableau suivant.

|Paramètres|Autorise|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permet Salles Microsoft Teams démarrage  <br/> |
|Gestion de l’alimentation -\> Sur AC, désactiver l’écran après 10 minutes  <br/> Power Management - Sur\> AC, ne mettez jamais le système en veille  <br/> |Permet Salles Microsoft Teams désactiver les écrans joints et de faire son réveil automatiquement  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.   <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |

> [!NOTE]
> Lorsque Salles Microsoft Teams est compatible avec la prochaine version de Windows 10 système d’exploitation, salles Teams mise à jour automatique vers la version suivante via Windows Update. Salles Microsoft Teams ne doit pas être mis à niveau vers la prochaine version de Windows 10 manuellement ou via l’activation des stratégies de groupe Windows Update for Business (WUFB) « Sélectionnez le niveau de préparation Windows pour les mises à jour que vous voulez recevoir » et « Sélectionnez quand les builds d’aperçu et les mises à jour de fonctionnalités sont reçues » via un groupe de stratégies de groupe. salles Teams ces stratégies de groupe activées sont connus pour être mises à jour du système Windows 10 système d’exploitation.

## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Vous pouvez effectuer les opérations de gestion suivantes à distance à l’aide de PowerShell (voir le tableau ci-dessous pour obtenir des exemples de script) :
  
- Obtenir les périphériques raccordés
- Obtenir l';état de l';application
- Obtenir les informations système
- Redémarrer le système
- Récupérer les journaux
- Transférer des fichiers (nécessite un enregistrement Salles Microsoft Teams)
    
> [!NOTE]
> Cette fonctionnalité est désactivée par défaut. Vous devez activer PowerShell distant pour votre environnement sur le Salles Microsoft Teams pour effectuer les opérations ci-dessous. Consultez la documentation sur **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** pour plus d’informations sur l’enable remote PowerShell.
  
Par exemple, vous pouvez activer PowerShell à distance comme suit :
  
1. Connectez-vous en tant qu’administrateur sur Salles Microsoft Teams appareil.
2. Ouvrez une invite de commandes PowerShell avec élévation de élévation de niveau.
3. Entrez la commande suivante : `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Ouvrez la stratégie de sécurité locale et ajoutez le groupe de sécurité *Administrateurs*  >  à l’Paramètres **Local PoliciesUser** >  **Rights** **AssignmentAccess** >  cet ordinateur à partir du réseau.

Pour effectuer une opération de gestion :
  
1. Connectez-vous à un PC avec des informations d’identification de compte qui sont autorisées à exécuter les commandes PowerShell sur un Salles Microsoft Teams appareil.
2. Ouvrez une invite de commandes PowerShell normale sur le PC.
3. Copiez le texte de la commande dans le tableau ci-dessous et collez-le à l’invite.
4. Remplacez  `<Device fqdn>` les champs par les valeurs de nom de domaine (FQDN) appropriées à votre environnement.
5. Remplacez-le  *\<path\>*  par le nom du fichier et le chemin d’accès local du SkypeSettings.xml de configuration (ou l’image thème).
    
Pour obtenir des appareils connectés
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Obtenir l’état de l’application
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Obtenir les informations système
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Redémarrer le système
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Récupérer les journaux
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Push an XML configuration file (or theme graphic)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Mises à jour logicielles
<a name="SWupdate"> </a>

Par défaut, Salles Microsoft Teams tente de se connecter au Windows Store pour obtenir la dernière version Salles Microsoft Teams logiciels. Par conséquent, salles Teams nécessite un accès internet normal. Avant de contacter Microsoft pour des problèmes de support, assurez-vous Salles Microsoft Teams charge avec la dernière version de l’application.
  
Salles Microsoft Teams se connecte à Windows mise à jour pour récupérer les mises à jour du système d’exploitation et du microprogramme de l’appareil périphérique. Teams salle est configurée pour les installer à partir de 02:00 heure locale.
  
Si vous devez gérer les mises à jour manuellement en raison de limitations dans l’accès au magasin Windows et ne pouvez donc pas suivre la procédure normale de [Microsoft Store pour Entreprises](https://businessstore.microsoft.com/store) pour distribuer les applications hors [connexion, vous](/microsoft-store/distribute-offline-apps) pouvez acheter le fichier APPX approprié et les dépendances à partir du [kit](https://go.microsoft.com/fwlink/?linkid=851168) de déploiement (dans les instructions de configuration d’une [ Salles Microsoft Teams console de travail](console.md)) qui peuvent être utilisées avec Configuration Manager. La publication du kit de déploiement est en retard par rapport à la version du Store, aussi ne correspond-elle peut-être pas toujours à la dernière build disponible.
  
### <a name="to-update-using-powershell"></a>Pour mettre à jour à l’aide de PowerShell

1. Extrayez le package de [l’installation MSI](https://go.microsoft.com/fwlink/?linkid=851168) sur un partage accessible à l’appareil.
2. Exécutez le script suivant ciblant les Salles Microsoft Teams, en \<share\> modifiant le partage d’appareil selon le cas :
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Mode Administrateur et gestion des appareils
<a name="AdminMode"> </a>

Certaines fonctions de gestion, telles que l’installation manuelle d’un certificat d’autorisation d’accès rapide privé, salles Teams place en mode d’administration. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passer en mode d’administration et revenir en arrière Salles Microsoft Teams’application en cours d’exécution

1. Raccrocher les appels en cours et revenir à l’écran d’accueil.
2. Sélectionnez l’icône Engrenages et faites s’ouvrir le menu (les options **sont Paramètres**, **Accessibilité** et **Redémarrer l’appareil**).
3. Sélectionnez **Paramètres**.
4. Entrez le mot de passe administrateur. L’écran d’installation s’affiche.  Si l’appareil n’est pas joint au domaine, le compte d’administration local (nom d’utilisateur « Administrateur ») est utilisé par défaut. Le mot de passe par défaut pour ce compte est « sfb ». Modifiez ce mot de passe dès que possible. Si l’ordinateur est joint au domaine, vous pouvez vous connectez avec un compte de domaine correctement privilégié.
5. **Sélectionnez Windows Paramètres** dans la colonne de gauche.
6. Connectez-vous au bureau avec vos informations d’identification administrateur. Vous aurez les privilèges nécessaires pour gérer l’appareil.
7. Exécutez les tâches administratives requises.
8.  Redémarrez l’ordinateur lorsque vous avez terminé.
    
La console revient à présent à son mode de fonctionnement normal. La procédure suivante nécessite le raccordement d’un clavier à l’appareil si ce n’est pas déjà fait.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Basculement en mode d’administration et retour en cas Salles Microsoft Teams’application se  crashe

1. Appuyez rapidement cinq fois sur la touche Windows. L’écran de connexion de Windows apparaît.  
2. Connectez-vous au bureau avec vos informations d’identification administrateur.
3. Exécutez les tâches administratives requises.
4. Redémarrez l’ordinateur lorsque vous avez terminé.

    > [!NOTE]
    > Cette méthode n’a pas pour effet de déconnecter l’Skype ou de mettre fin gratuitement à l’application, mais vous l’utiliseriez si l’application ne répondait pas et que l’autre méthode n’était pas disponible. 

   La console redémarre en mode d’utilisation normal, exécutant l’Salles Microsoft Teams automatique. Vous pouvez supprimer le clavier si vous en avez connecté un pour effectuer cette procédure.
   ## <a name="troubleshooting-tips"></a>Astuces de dépannage
   <a name="TS"> </a>

- Il est possible que les invitations aux réunions n’apparaissent pas lorsqu’elles sont envoyées au-delà des limites de domaine (par exemple, entre deux entreprises). Dans ce cas, les administrateurs informatiques doivent décider d’autoriser ou non les utilisateurs externes à planifier une réunion. Consultez l’article Exchange’let de cmdlet PowerShell [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), plus précisément le paramètre « ProcessExternalMeetingMessages ».
- Salles Microsoft Teams ne prend pas en charge les Exchange de découverte automatique via Exchange 2010.
- En règle générale, il est pratique pour les administrateurs informatiques de désactiver les points de terminaison audio qu’ils n’ont pas l’intention d’utiliser.
- Si une image miroir s’affiche dans l’aperçu de la salle, l’administrateur informatique peut corriger la mise en marche de l’appareil photo ou le retournement de l’orientation de l’image à l’aide des paramètres de la caméra.
- La perte de l’accès à l’écran tactile de la console est connue. Dans de tels cas, le problème est parfois résolu en redémarrage salles Teams.
- La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue. Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.
