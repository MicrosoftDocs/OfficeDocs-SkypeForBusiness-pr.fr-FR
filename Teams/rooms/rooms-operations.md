---
title: Maintenance et opérations dans salles Microsoft Teams
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
localization_priority: Normal
description: Lisez cette rubrique pour en savoir plus sur la gestion des salles Microsoft Teams, la nouvelle génération de systèmes de salle Skype.
ms.openlocfilehash: a6ab68200002035632314ac976cd45a2ee4ff714
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662459"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Maintenance et opérations dans salles Microsoft Teams 
 
Lisez cette rubrique pour en savoir plus sur la gestion des salles Microsoft Teams, la nouvelle génération de systèmes de salle Skype.
  
Salles Microsoft Teams est la dernière solution de conférence conçue pour transformer votre salle de réunion en une expérience de collaboration enrichie et collaborative. Les utilisateurs apprécieront l’interface familière de Microsoft Teams ou de Skype Entreprise, et les administrateurs informatiques apprécieront une application réunion Skype Windows 10 facilement déployée et gérée. Les salles Microsoft Teams sont conçues pour tirer parti d’équipements existants tels que des panneaux SOUHAITEZ-VOUS installer facilement Microsoft Teams ou Skype Entreprise dans votre salle de réunion.
  
Avec une configuration supplémentaire, la gestion à distance est possible à l’aide de Microsoft Azure Monitor comme décrit dans la gestion de salles Microsoft Teams avec [Azure Monitor,](azure-monitor-plan.md)déployer la gestion des salles Microsoft Teams avec Azure [Monitor,](azure-monitor-deploy.md)gérer les appareils [Salles Microsoft Teams](azure-monitor-deploy.md)avec Azure Monitor. Vous pouvez également gérer les paramètres de la console des salles Microsoft Teams à distance avec un fichier [de configuration XML,](xml-config-file.md)qui inclut l’application d’un thème d’affichage personnalisé. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Collecte de journaux dans des salles Microsoft Teams
<a name="Logs"> </a>

Pour collecter des journaux, vous devez appeler le script de collection de journaux qui est intégré à l’application Salles Microsoft Teams. En mode d’administration, démarrez une invite de commandes avec élévation de privilèges, puis lancez la commande suivante :
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Les journaux seront produits sous forme de fichier ZIP dans c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Paramètres de l’écran d’affichage
<a name="Display"> </a>

Configurez l’écran d’affichage en mode étendu. Cette faisant, vous vous assurerez que l’interface utilisateur de la console n’est pas dupliquée sur cet écran lorsque vous dont la puissance est affichée.
  
> [!NOTE]
> Si vous souhaitez qu’un écran avant de la salle bascule automatiquement vers une source vidéo active (par exemple, une console MTR) lorsque la source extraite du mode veille, certaines conditions doivent être remplies. Cette fonctionnalité est facultative mais prise en charge par le logiciel Salles Microsoft Teams, à condition que le matériel sous-jacent la prend en charge. Un téléviseur grand public utilisé comme avant d’affichage doit prendre en charge la fonctionnalité CEC (Consumer Electronics Control) de HDMI.  En fonction de la station d’accueil ou de la console sélectionnée (qui ne peut pas prendre en charge la cec, consultez la documentation du support technique du fabricant), un contrôleur tel qu’un [contrôleur HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) d’Extron peut être nécessaire pour activer le comportement souhaité. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Réinitialisation des salles Microsoft Teams (restauration aux usine)
<a name="Reset"> </a>

Si les salles Microsoft Teams ne fonctionnent pas bien, la réinitialisation aux usine peut vous aider. Pour ce faire, utilisez l’outil de récupération [de salle Microsoft Teams](recovery-tool.md) et suivez les instructions de restauration d’usine.

> [!NOTE]
> Il existe un problème connu dans lequel les salles Microsoft Teams peuvent devenir inutilisables si l’option Conserver mes fichiers - Supprime les applications et les **paramètres,** mais conserve vos fichiers personnels est sélectionnée pendant le processus de réinitialisation de Windows. *N’utilisez* pas cette option.
  
## <a name="supported-remote-options"></a>Options distantes prises en charge
<a name="RemoteOptions"> </a>

Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.
  

|Groupe de travail |Aucun domaine joint|Domaine joint|
|:-----|:-----|:-----|
|Redémarrer  <br/> |Bureau distant  <br/> Powershell distant  <br/> |Bureau à distance (nécessite une configuration plus particulière)  <br/> Remote PowerShell (nécessite une configuration plus particulière)  <br/> Configuration Manager  <br/> |
|Mise à jour du SE  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Mise à jour de l';application  <br/> |	Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configuration du compte Skype  <br/> |	Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
|Accès aux journaux  <br/> |	Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuration d’une stratégie de groupe pour les salles Microsoft Teams
<a name="GroupPolicy"> </a>

Cette section couvre les paramètres système dont dépendent les salles Microsoft Teams pour fonctionner correctement. Lorsque vous rejoignez Salles Microsoft Teams sur un domaine, assurez-vous que votre stratégie de groupe ne remplace pas les paramètres du tableau suivant.
  

|Paramètres|Autorise|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permet au démarrage de Salles Microsoft Teams  <br/> |
|Gestion de l’alimentation - \> Sur AC, désactiver l’écran après 10 minutes  <br/> Power Management - \> Sur AC, ne mettez jamais le système en veille  <br/> |Permet aux salles Microsoft Teams de désactiver les écrans joints et de faire son réveil automatiquement  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.  <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |
   
Le transfert de fichiers à l’aide de stratégies de groupe est évoqué [dans la rubrique Configurer un élément de fichier.](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

> [!NOTE]
> Lorsque l’appareil Salles Microsoft Teams est compatible avec la prochaine version du système d’exploitation Windows 10, l’appareil est automatiquement mis à jour vers la version suivante via Windows Update. Les appareils Salles Microsoft Teams ne doivent pas être mis à niveau vers la prochaine version de Windows 10 manuellement ou via l’activation des stratégies de groupe Windows Update for Business (WUFB) « Sélectionnez le niveau de préparation Windows pour les mises à jour que vous voulez recevoir » et « Sélectionnez quand les builds d’aperçu et les mises à jour de fonctionnalités sont reçues » via GPO. Un appareil avec ces stratégies de groupe activées est connu pour être en situation de problème avec la mise à jour du système d’exploitation Windows 10 par l’application Salles Microsoft Teams.

## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Vous pouvez effectuer les opérations de gestion suivantes à distance à l’aide de PowerShell (voir le tableau ci-dessous pour obtenir des exemples de script) :
  
- Obtenir les périphériques raccordés
- Obtenir l';état de l';application
- Obtenir les informations système
- Redémarrer le système
- Récupérer les journaux
- Transférer des fichiers (nécessite une salle Microsoft Teams jointe à un domaine)
    
> [!NOTE]
> Cette fonctionnalité est désactivée par défaut. Vous devez activer Remote PowerShell pour votre environnement sur le système Salles Microsoft Teams pour effectuer les opérations ci-dessous. Consultez la documentation sur **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** pour plus d’informations sur l’enable remote PowerShell.
  
Par exemple, vous pouvez activer PowerShell à distance comme suit :
  
1. Connectez-vous en tant qu’administrateur sur un appareil Salles Microsoft Teams.
2. Ouvrez une invite de commandes PowerShell avec élévation de élévation de niveau.
3. Entrez la commande suivante : `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Ouvrez la stratégie de sécurité locale et ajoutez le groupe de sécurité Administrateurs à l’accès à l’attribution de droits utilisateur des *stratégies locales* aux **stratégies locales** sur cet ordinateur à partir  >    >    >  **du réseau.**

Pour effectuer une opération de gestion :
  
1. Connectez-vous à un PC avec des informations d’identification de compte qui sont autorisées à exécuter les commandes PowerShell sur un appareil Salles Microsoft Teams.
2. Ouvrez une invite de commandes PowerShell normale sur le PC.
3. Copiez le texte de la commande dans le tableau ci-dessous et collez-le à l’invite.
4. Remplacez les champs par des valeurs de nom de domaine  `<Device fqdn>` (FQDN) appropriées pour votre environnement.
5. *\<path\>* Remplacez-le par le nom du fichier et le chemin d’accès local du SkypeSettings.xml de configuration (ou l’image thème).
    
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

Par défaut, Salles Microsoft Teams tente de se connecter au Windows Store pour obtenir la dernière version du logiciel Salles Microsoft Teams, afin que l’appareil nécessite un accès internet normal. Avant de contacter Microsoft pour des problèmes de support, assurez-vous que l’appareil Salles Microsoft Teams est chargé avec la dernière version de l’application.
  
Par défaut, les salles Microsoft Teams se connectent à Windows Update pour récupérer les mises à jour du système d’exploitation et du microprogramme du périphérique USB et les installent en dehors des heures d’ouverture configurées. Vous pouvez configurer les heures d’ouverture en vous connectant au compte administrateur et en exécutant l’application Paramètres.
  
Si vous voulez gérer les mises à jour manuellement et que vous ne pouvez pas suivre la procédure normale de [Microsoft Store](https://businessstore.microsoft.com/store) pour Entreprises afin de distribuer les applications hors [connexion,](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)vous pouvez acheter le fichier APPX approprié et les dépendances à partir du [kit](https://go.microsoft.com/fwlink/?linkid=851168) de déploiement (dans les instructions de configuration d’une [console salles Microsoft Teams)](console.md)qui peuvent être utilisées avec Configuration Manager. La publication du kit de déploiement est en retard par rapport à la version du Store, de sorte qu’elle ne correspond peut-être pas toujours à la dernière build disponible.
  
### <a name="to-update-using-powershell"></a>Pour mettre à jour à l’aide de PowerShell

1. Extrayez le package de [l’installation MSI](https://go.microsoft.com/fwlink/?linkid=851168) sur un partage accessible à l’appareil.
2. Exécutez le script suivant ciblant les appareils salles Microsoft Teams, en modifiant \<share\> le partage d’appareil selon le cas :
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>Mode Administrateur et gestion des appareils
<a name="AdminMode"> </a>

Certaines fonctions de gestion, telles que l’installation manuelle d’un certificat d’autorisation d’accès rapide privé, nécessitent le placement de l’appareil Surface Pro en mode d’administration. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passer en mode d’administration et revenir en arrière lorsque l’application Salles Microsoft Teams est en cours d’exécution

1. Raccrocher les appels en cours et revenir à l’écran d’accueil.
2. Sélectionnez l’icône Engrenages et faites s’ouvrir le menu (les options **sont Paramètres,** **Accessibilité** et **Redémarrer l’appareil).**
3. Sélectionnez **Paramètres**.
4. Entrez le mot de passe de l’administrateur. L’écran d’installation s’affiche.  Si l’appareil n’est pas joint au domaine, le compte d’administration local (nom d’utilisateur « Administrateur ») est utilisé par défaut. Le mot de passe par défaut de ce compte est « sfb ». Modifiez-le dès que possible. Si l’ordinateur est joint au domaine, vous pouvez vous connectez avec un compte de domaine correctement privilégié. 
5. Sélectionnez **Paramètres Windows** dans la colonne de gauche.
6. Sélectionnez **Atteindre connexion d’administration**.
7. Entrez le mot de passe de l’administrateur. Vous serez déconnecté de l’application et reviendrez à l’écran de connexion de Windows. 
8. Connectez-vous au bureau avec vos informations d’identification administrateur. Vous aurez les privilèges nécessaires pour gérer l’appareil.
9. Exécutez les tâches administratives requises.
10. Déconnectez-vous du compte Administrateur.
11. Retournez dans Salles Microsoft Teams en sélectionnant l’icône de compte d’utilisateur sur le côté gauche de l’écran, puis en sélectionnant **Skype.**
    
    Si **l’utilisateur Skype** n’est pas  répertorié, vous de devez peut-être sélectionner un autre utilisateur, entrer **.\skype** comme nom d’utilisateur, puis vous connectez-vous.
    
La console est maintenant en mode d’utilisation normale. La procédure suivante nécessite que vous attachiez un clavier à l’appareil s’il n’en a pas déjà un. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Basculement en mode d’administration et retour en cas de panne de l’application Salles Microsoft Teams

1. Appuyez rapidement cinq fois sur la touche Windows. L’écran de connexion de Windows apparaît. 
2. Connectez-vous au bureau avec vos informations d’identification administrateur.
3. Exécutez les tâches administratives requises.
4. Redémarrez l’ordinateur lorsque vous avez terminé.

    > [!NOTE]
    > Cette méthode n’a pas pour effet de déconnecter l’utilisateur de Skype ou de mettre fin gratuitement à l’application, mais vous l’utiliseriez si l’application ne répondait pas et que l’autre méthode n’était pas disponible. 

   La console redémarre en mode d’utilisation normal, exécutant l’application Salles Microsoft Teams. Vous pouvez supprimer le clavier, s’il était connecté pour vous permettre d’effectuer cette procédure.
   ## <a name="troubleshooting-tips"></a>Astuces de dépannage
   <a name="TS"> </a>

- Il est possible que les invitations aux réunions n’apparaissent pas lorsqu’elles sont envoyées au-delà des limites de domaine (par exemple, entre deux entreprises). Dans ce cas, les administrateurs informatiques doivent décider d’autoriser ou non les utilisateurs externes à planifier une réunion.
- Les salles Microsoft Teams ne prend pas en charge les redirections de découverte automatique Exchange via Exchange 2010.
- En règle générale, il est pratique pour les administrateurs informatiques de désactiver les points de terminaison audio qu’ils n’ont pas l’intention d’utiliser.
- Dans le cas où une image miroir est affichée dans la prévisualisation de la salle, l’administrateur informatique peut corriger en mettant sous tension la caméra ou en retournant l’orientation de l’image à l’aide de la télécommande de la caméra.
- La perte de l’accès à l’écran tactile de la console est connue. Dans de tels cas, le problème est parfois résolu en redémarrage du système salles Microsoft Teams.
- La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue. Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.
    
