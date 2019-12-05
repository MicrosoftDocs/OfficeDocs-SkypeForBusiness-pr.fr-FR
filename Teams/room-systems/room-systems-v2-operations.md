---
title: Maintenance et opérations des salles de Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Pour en savoir plus sur la gestion des salles de Microsoft Teams, reportez-vous à la rubrique nouvelle génération de systèmes de salle Skype.
ms.openlocfilehash: aeab9235b54138d649cee2f5e67a76a109c36c6a
ms.sourcegitcommit: b8e16703e4611ca2bde55896ec158b33be4f9ba0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39842476"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Maintenance et opérations des salles de Microsoft teams 
 
Pour en savoir plus sur la gestion des salles de Microsoft Teams, reportez-vous à la rubrique nouvelle génération de systèmes de salle Skype.
  
Microsoft teams est la solution de conférence la plus récente de Microsoft conçue pour transformer votre salle de réunion en une expérience riche et collaborative. Les utilisateurs apprécieront l’interface familière de Microsoft teams ou Skype entreprise et les administrateurs informatiques apprécieront une application de réunion Skype facilement déployée et gérée dans Windows 10. Les salles de Microsoft teams sont conçues pour exploiter les équipements existants tels que les écrans LCD pour faciliter l’installation de Microsoft teams ou de Skype entreprise dans votre salle de réunion.
  
Dans le cadre de la configuration supplémentaire, la gestion à distance est possible à l’aide de l’outil Moniteur Microsoft Azure, comme décrit dans la rubrique planification de la gestion [](azure-monitor-deploy.md)des [salles de](azure-monitor-plan.md)Microsoft teams avec Azure Monitor, déploiement de la gestion de [Microsoft teams pour](azure-monitor-deploy.md)Microsoft teams Vous pouvez également [gérer les paramètres de la console de Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md), qui inclut l’application d’un thème d’affichage personnalisé. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Collecte de journaux sur les salles de Microsoft teams
<a name="Logs"> </a>

Pour recueillir les journaux, vous devez appeler le script de collection de journaux qui est fourni avec l’application Microsoft Teams. En mode admin, démarrez une invite de commandes avec élévation de privilèges et émettez la commande suivante :
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Les journaux seront en sortie sous forme de fichier ZIP dans c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Paramètres de l’écran d’affichage
<a name="Display"> </a>

Configurez l’écran d’affichage en mode étendu. Cela permet de s’assurer que l’interface utilisateur de la console n’est pas dupliquée sur cet écran lorsque vous allumez le mode d’affichage.
  
> [!NOTE]
> Si vous souhaitez qu’un écran de façade de la salle bascule automatiquement vers une source vidéo active (par exemple, une console MTR) lorsque la source quitte le mode veille, certaines conditions doivent être remplies. Cette fonctionnalité n’est pas disponible, mais elle est prise en charge par le logiciel de salle Microsoft teams ; Une télévision grand public utilisée comme devant l’écran de la salle doit prendre en charge la fonctionnalité de contrôle Consumer Electronics (CEC) de l’interface HDMI.  Selon le Dock ou la console sélectionné (qui n’est pas pris en charge par le CEC, voir documentation du fabricant), un contrôleur tel qu’une connexion [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron peut être nécessaire pour activer le comportement souhaité. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Réinitialisation des salles de Microsoft Teams (restauration d’usine)
<a name="Reset"> </a>

Si Microsoft Teams ne fonctionne pas correctement, il peut être utile d’effectuer une réinitialisation d’usine. Pour ce faire, utilisez l' [outil de récupération de salle de Microsoft teams](recovery-tool.md) , puis suivez les instructions de restauration d’usine.

> [!NOTE]
> Il existe un problème connu pour lequel les salles de Microsoft teams peuvent être désactivées si l’option **conserver mes fichiers-supprime des applications et des paramètres, mais** que vous avez sélectionné l’option conservation de vos fichiers personnels lors du processus de réinitialisation de Windows. N’utilisez *pas* cette option.
  
## <a name="supported-remote-options"></a>Options distantes prises en charge
<a name="RemoteOptions"> </a>

Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.
  

|Groupe de travail |Aucun domaine joint|Domaine joint|
|:-----|:-----|:-----|
|Redémarrer  <br/> |Bureau distant  <br/> Powershell distant  <br/> |Bureau à distance (nécessite une configuration supplémentaire)  <br/> PowerShell distant (nécessite une configuration supplémentaire)  <br/> SCCM  <br/> |
|Mise à jour du SE  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Mise à jour de l';application  <br/> |	Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Configuration du compte Skype  <br/> |Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
|Accès aux journaux  <br/> |	Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuration d’une stratégie de groupe pour les salles Microsoft teams
<a name="GroupPolicy"> </a>

Cette section décrit les paramètres système dont dépend le fonctionnement des salles de Microsoft Teams. Lorsque vous rejoignez des salles de Microsoft teams à un domaine, vérifiez que votre stratégie de groupe ne remplace pas les paramètres du tableau suivant.
  

|Paramètre|Permet|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permet au démarrage de Microsoft teams  <br/> |
|Gestion de l'\> alimentation-sur le ca, éteindre l’écran après 10 minutes  <br/> Gestion de l'\> alimentation-sur le secteur, jamais mettre le système en veille  <br/> |Activation de l’affichage et de la réactivation des salles de Microsoft teams  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.  <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |
   
Pour transférer des fichiers à l’aide de stratégies de groupe, voir [configurer un élément de fichier](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).

> [!NOTE]
> Lorsque l’appareil de salle Microsoft teams est compatible avec la version suivante du système d’exploitation Windows 10, l’appareil est automatiquement mis à jour vers la version suivante par le biais de Windows Update. La mise à niveau vers la nouvelle version de Windows 10, ou via l’activation de la stratégie de groupe Windows Update pour les entreprises (WUFB) de Microsoft Teams ne peut pas être mise à niveau vers une version ultérieure de Windows 10 Les mises à jour de fonctionnalités sont reçues par le biais d’un objet de stratégie de groupe. Un appareil doté de ces stratégies de groupe activé est connu pour rencontrer des problèmes liés à la mise à jour de Windows 10 du système d’exploitation par l’application Microsoft Teams.

## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Vous pouvez effectuer les opérations de gestion suivantes à distance à l’aide de PowerShell (voir le tableau ci-dessous pour les exemples de script) :
  
- Obtenir les périphériques raccordés
- Obtenir l';état de l';application
- Obtenir les informations système
- Redémarrer le système
- Récupérer les journaux
- Transférer des fichiers (nécessite une salle Microsoft teams dans un domaine)
    
> [!NOTE]
> Cette fonctionnalité est désactivée par défaut. Pour effectuer les opérations suivantes, vous devez activer PowerShell distant pour votre environnement dans le système de salle Microsoft Teams. Pour plus d’informations sur la façon d’activer PowerShell à distance, consultez la documentation sur **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** .
  
Par exemple, vous pouvez activer PowerShell à distance comme suit :
  
1. Connectez-vous en tant qu’administrateur sur un appareil Microsoft Teams.
2. Ouvrez une invite de commandes PowerShell avec élévation de privilèges.
3. Entrez la commande suivante : Enable-PSRemoting -force

Pour effectuer une opération de gestion :
  
1. Connectez-vous à un PC à l’aide d’informations d’identification de compte disposant des autorisations d’exécution des commandes PowerShell sur un appareil Microsoft Teams.
2. Ouvrez une invite de commandes PowerShell normale sur le PC.
3. Copiez le texte de commande du tableau ci-dessous, puis collez-le à l’invite.
4. Remplacez `<Device fqdn>` les champs par des valeurs FQDN appropriées à votre environnement.
5. Remplacez * \<Path\> * par le nom de fichier et le chemin d’accès local du fichier de configuration SkypeSettings. xml principal (ou de l’image de thème).
    
Pour obtenir des appareils connectés
  
```
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

Obtenir l’état de l’application
  
```
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

Obtenir les informations système
  
```
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

Redémarrer le système
  
```
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

Récupérer les journaux
  
```
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

Transférer un fichier de configuration XML (ou graphique de thème)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Mises à jour logicielles
<a name="SWupdate"> </a>

Par défaut, Microsoft teams services tente de se connecter au Windows Store pour obtenir la dernière version du logiciel de salle Microsoft Teams, de sorte que l’appareil exige un accès Internet régulier. Avant de contacter Microsoft avec des problèmes de support, assurez-vous que l’appareil Microsoft teams est chargé avec la dernière version de l’application.
  
Par défaut, Microsoft teams se connecte à Windows Update pour extraire les mises à jour du microprogramme du système d’exploitation et du périphérique USB, et les installe en dehors des heures d’activité configurées. Vous pouvez configurer les heures d’ouverture en vous connectant au compte administrateur et en exécutant l’application Paramètres.
  
Si vous souhaitez gérer les mises à jour manuellement et ne parvenez pas à suivre les procédures normales de la [Boutique Microsoft pour les entreprises](https://businessstore.microsoft.com/store) afin de [distribuer des applications hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), vous pouvez acquérir le fichier AppX approprié et les dépendances du [Kit de déploiement](https://go.microsoft.com/fwlink/?linkid=851168) (consultez les instructions de [configuration d’une console Microsoft teams](console.md)) qui peuvent être utilisées avec SCCM. Le kit de déploiement est en retard sur le Windows Store, il se peut donc que la version ne corresponde pas toujours à la version la plus récente.
  
### <a name="to-update-using-powershell"></a>Pour effectuer une mise à jour à l’aide de PowerShell

1. Extrayez le package de l’installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) vers un partage auquel le périphérique peut accéder.
2. Exécutez le script suivant ciblant les appareils de salle Microsoft Teams, en modifiant \<le partage\> sur le partage de l’appareil, selon le cas :
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Mode Administrateur et gestion des appareils
<a name="AdminMode"> </a>

Certaines fonctions de gestion (par exemple, l’installation manuelle d’un certificat d’autorité de certification privée) nécessitent la mise en mode d’administration de l’appareil surface Pro. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Basculement en mode administrateur et retour lors de l’exécution de l’application Microsoft teams

1. Raccrochez tout appel en cours et retournez sur l’écran d’accueil.
2. Sélectionner l’icône d’engrenage et afficher le menu (les options sont **paramètres**, **accessibilité**et **redémarrage** de l’appareil).
3. Sélectionnez **Paramètres**.
4. Entrez le mot de passe de l’administrateur. L’écran d’installation s’affiche.  Si l’appareil n’est pas joint à un domaine, le compte d’administrateur local (nom d’utilisateur « administrateur ») est utilisé par défaut. Le mot de passe par défaut de ce compte est « marketing », modifiez le mot de passe dès que possible. Si l’ordinateur est joint à un domaine, vous pouvez vous connecter à l’aide d’un compte de domaine à privilèges appropriés. 
5. Dans la colonne de gauche, sélectionnez **Paramètres Windows** .
6. Sélectionnez **Atteindre connexion d’administration**.
7. Entrez le mot de passe de l’administrateur. Vous serez déconnecté de l’application et reviendrez à l’écran de connexion de Windows. 
8. Connectez-vous au bureau avec vos informations d’identification administrateur. Vous disposez des autorisations nécessaires pour gérer l’appareil.
9. Exécutez les tâches administratives requises.
10. Déconnectez-vous du compte Administrateur.
11. Revenez à la page de Microsoft teams en sélectionnant l’icône du compte d’utilisateur dans la partie gauche de l’écran, puis sélectionnez **Skype**.
    
    Si l’utilisateur **Skype** n’est pas répertorié, vous devrez peut-être sélectionner **autre utilisateur** et entrer **.\skype** comme nom d’utilisateur et vous connecter.
    
La console est à présent en mode de fonctionnement normal. Pour utiliser la procédure suivante, vous devez joindre un clavier à l’appareil s’il n’y a pas encore de pièce jointe. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Basculement en mode administrateur et retour lorsque l’application Microsoft teams se bloque

1. Appuyez rapidement cinq fois sur la touche Windows. L’écran de connexion de Windows apparaît. 
2. Connectez-vous au bureau avec vos informations d’identification administrateur.
3. Exécutez les tâches administratives requises.
4. Lorsque vous avez terminé, redémarrez l’ordinateur.

    > [!NOTE]
    > Cette méthode n’entraîne pas la connexion de l’utilisateur Skype ou l’arrêt normal de l’application, mais vous pouvez l’utiliser si l’application ne répond pas et que l’autre méthode n’a pas été disponible. 

   La console redémarre en mode de fonctionnement normal et exécute l’application Microsoft Teams. Vous pouvez supprimer le clavier, s’il est attaché pour vous permettre d’effectuer cette procédure.
   ## <a name="troubleshooting-tips"></a>Astuces de dépannage
   <a name="TS"> </a>

- Les invitations aux réunions risquent de ne pas apparaître lors de leur envoi dans les limites du domaine (par exemple, entre deux sociétés). Dans ces cas, l’administrateur informatique doit décider d’autoriser ou non les utilisateurs externes à planifier une réunion.
- Les salles de Microsoft Teams ne prennent pas en charge la découverte automatique Exchange redirectionne via Exchange 2010.
- En règle générale, il est conseillé aux administrateurs informatiques de désactiver les points de terminaison audio qu’il n’est pas prévu d’utiliser.
- Dans le cas où une image miroir est affichée dans la prévisualisation de la salle, l’administrateur informatique peut corriger en mettant sous tension la caméra ou en retournant l’orientation de l’image à l’aide de la télécommande de la caméra.
- La perte de l’accès à l’écran tactile de la console est connue. Dans ce cas, le problème peut être résolu en redémarrant le système de salles Microsoft Teams.
- La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue. Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.
    
