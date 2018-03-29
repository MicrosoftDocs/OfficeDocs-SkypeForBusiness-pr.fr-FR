---
title: Gestion de Skype Room System v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
description: Lisez cette rubrique pour en savoir plus sur la gestion des systèmes de salle Skype v2, la nouvelle génération de systèmes de salle de Skype.
ms.openlocfilehash: 5ef699bed1a77fc48f59ba4c5f8eb78ccc286ef7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-room-systems-v2"></a>Gestion de Skype Room System v2
 
Lisez cette rubrique pour en savoir plus sur la gestion des systèmes de salle Skype v2, la nouvelle génération de systèmes de salle de Skype.
  
Systèmes de salle Skype v2 est la dernière solution de conférence de Microsoft conçue pour transformer votre salle de réunion un Skype riche et de collaboration pour une expérience. Les utilisateurs apprécieront son interface Skype Entreprise familière, et les administrateurs informatiques approuveront la facilité de déploiement et de gestion de l’application de réunion Skype sous Windows 10. Systèmes de salle Skype v2 est conçu pour tirer parti des équipements existants tels que des panneaux LCD pour faciliter d’installation pour mettre Skype pour entreprise dans votre salle de réunion.
  
Une configuration supplémentaire, l’administration à distance est possible à l’aide de Microsoft Operations Management Suite (OMS) comme décrit dans le [Plan Skype salle v2 SMS avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [déployer Skype salle v2 SMS avec OMS](../../deploy/deploy-clients/with-oms.md)et [gérer Les périphériques systèmes de salle Skype v2 avec OMS](oms.md). Vous pouvez également [un v2 Skype salle de systèmes de gérer les paramètres de console à distance avec un fichier de configuration XML](xml-config-file.md), qui inclut l’application d’un thème d’affichage personnalisé. 
  
## <a name="collecting-logs-on-skype-room-systems-v2"></a>Collecte de journaux sur Skype Room Systems v2
<a name="Logs"> </a>

Pour collecter des journaux, vous devez appeler le script de collection de journal qui est fourni avec l’application v2 de systèmes de salle de Skype. En mode administrateur, démarrez une invite de commandes avec élévation de privilèges et exécutez la commande suivante :
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Les journaux seront générés sous la forme d’un fichier ZIP dans c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Paramètres de l’écran d’affichage
<a name="Display"> </a>

Configurez l’écran d’affichage en mode étendu. Vous vous assurez ainsi que l’interface utilisateur de la console n’est pas dupliquée sur cet affichage lors de la mise sous tension de l’affichage.
  
> [!NOTE]
> Un poste de télévision utilisé comme frontal de salle d’affichage pour la prise en charge/activer la fonctionnalité de contrôle des appareils électroniques grand public (CEC) de HDMI afin qu’il peut basculer automatiquement vers une source vidéo active du mode veille. Cette fonctionnalité n’est pas pris en charge sur tous les téléviseurs. 
  
## <a name="skype-room-systems-v2-reset-factory-restore"></a>Réinitialisation de Skype Room Systems v2 (Restaurer les paramètres d’usine)
<a name="Reset"> </a>

Si v2 de systèmes de salle Skype ne fonctionne pas bien, peut aider à effectuer une réinitialisation de l’usine. Pour ce faire dans l’application à partir de l’onglet « Récupération » sous l’en-tête « Réinitialiser ce PC », sélectionnez « Démarrer » suivi de « Supprimer tout ». Suivez les autres invites selon votre choix pour réinitialiser le périphérique.
  
> [!NOTE]
> Il existe un problème connu où le v2 Skype salle systèmes peuvent devenir inutilisables si l’option « Conserver mes fichiers - supprime les applications et les paramètres, mais conserve vos fichiers personnels » est sélectionnée au cours du processus de réinitialisation de Windows. **N';utilisez pas** cette option.
  
## <a name="supported-remote-options"></a>Options distantes prises en charge
<a name="RemoteOptions"> </a>

Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.
  

|**Groupe de travail**|**Joint pas au domaine**|**Joint au domaine**|
|:-----|:-----|:-----|
|Redémarrer  <br/> |Bureau distant  <br/> Powershell distant  <br/> |Bureau à distance (nécessite une configuration supplémentaire)  <br/> Powershell distant (nécessite une configuration supplémentaire)  <br/> SCCM  <br/> |
|Mise à jour du SE  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Mise à jour de l';application  <br/> |	Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Configuration du compte Skype  <br/> |	Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
|Accès aux journaux  <br/> |	Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
||||
   
## <a name="configuring-group-policy-for-skype-room-systems-v2"></a>Configuration de la stratégie de groupe pour Skype Room Systems v2
<a name="GroupPolicy"> </a>

Cette section traite des paramètres système qui dépend des systèmes de salle Skype v2 pour fonctionner correctement. Lorsque vous intégrez des systèmes de salle Skype v2 à un domaine, veuillez vous assurer que votre stratégie de groupe ne remplace pas les paramètres suivants :
  

|**Paramètre**|**Permet de**|
|:-----|:-----|
|	HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AdminAutoLogon = (dword) 1  <br/> |V2 de systèmes de salle Skype permet de démarrer  <br/> |
|Gestion - de l’alimentation\> sur CA, désactiver écran après 10 minutes  <br/> Gestion - de l’alimentation\> sur CA, ne placez jamais de mise en veille du système  <br/> |Permet de v2 de systèmes de salle Skype activer joint affiche et mode veille automatiquement  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.  <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |
   
Transfert de fichiers à l’aide de stratégies de groupe est traité dans [un élément de fichier de configuration](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Vous pouvez effectuer les opérations de gestion suivantes à distance à l’aide de PowerShell (consultez le tableau ci-dessous pour des exemples de script) :
  
- Obtenir les périphériques raccordés
    
- Obtenir l';état de l';application
    
- Obtenir les informations système
    
- Redémarrer le système
    
- Récupérer les journaux
    
- Transfert de fichiers (nécessite un domaine rejoint Skype salle systèmes v2)
    
> [!NOTE]
> Cette fonctionnalité est désactivée par défaut. Vous devez activer PowerShell distant pour votre environnement sur le système v2 de systèmes de salle Skype effectuer les opérations ci-dessous. Reportez-vous à la documentation sur **[Activer-PSRemoting](https://technet.microsoft.com/en-us/library/hh849694.aspx)** pour plus d’informations sur l’activation du PowerShell distant.
  
Par exemple, vous pouvez activer PowerShell à distance comme suit :
  
1. Ouvrez une session en tant qu’administrateur sur un périphérique de v2 de systèmes de salle de Skype.
    
2. Lancez une invite de commande PowerShell avec élévation de privilèges.
    
3. Entrez la commande suivante : Enable-PSRemoting - force
    
Pour effectuer une opération de gestion :
  
1. Vous connecter à un ordinateur avec des informations d’identification de compte qui ont l’autorisation d’exécuter des commandes PowerShell sur un périphérique de v2 de systèmes de salle de Skype.
    
2. Lancez une invite de commande PowerShell régulière sur votre ordinateur.
    
3. Copiez le texte de commande du tableau ci-dessous et collez-le dans l’invite.
    
4. Remplacer `<Device fqdn>` champs avec les valeurs de nom de domaine complet approprié à votre environnement.
    
5. Remplacer * \<chemin d’accès\> * avec le nom de fichier et le chemin d’accès local du fichier de configuration maître SkypeSettings.xml (ou image de thème).
    
Pour obtenir des équipements reliés
  
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

Pousser une configuration XML ou un graphique de thème)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Mises à jour logicielles
<a name="SWupdate"> </a>

Par défaut, systèmes de salle Skype v2 tentent de se connecter au magasin de Windows pour obtenir la dernière version de Skype salle v2 de logiciels de systèmes, afin que le périphérique nécessite un accès régulier à internet. Assurez-vous que le périphérique de v2 de systèmes de salle de Skype est chargé avec la version la plus récente de l’application, avant de contacter Microsoft avec les problèmes de prise en charge.
  
Par défaut, systèmes de salle Skype v2 se connectera mise à jour de Windows pour extraire du système d’exploitation, ainsi que du microprogramme de périphérique USB mises à jour et les installer en dehors des heures d’activité configurés. Vous pouvez configurer les heures d’ouverture en vous connectant au compte administrateur et en exécutant l’application Paramètres.
  
Si vous souhaitez gérer manuellement les mises à jour et ne peuvent pas suivre la procédure normale pour la [Banque d’informations Microsoft pour les entreprises](https://businessstore.microsoft.com/en-us/store) à [distribuer des applications en mode hors connexion](https://docs.microsoft.com/en-us/microsoft-store/distribute-offline-apps), vous pouvez acquérir les fichiers APPX et les dépendances à partir du [kit de déploiement](https://go.microsoft.com/fwlink/?linkid=851168) (à partir de les instructions pour [configurer une console v2 de systèmes de salle Skype](../../deploy/deploy-clients/console.md)) qui peut être utilisé avec SCCM. La version de kit de déploiement retard sur la version de la banque, donc il peut ne pas toujours correspond à la dernière version disponible.
  
### <a name="to-update-using-powershell"></a>Mise à jour à l’aide de Powershell

1. Extrayez le package de l’installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) sur un partage accessible du périphérique.
    
2. Exécutez le script suivant qui ciblent les périphériques systèmes de salle Skype v2, la modification \<partager\> sur le périphérique de partage le cas échéant :
    
  ```
  Add-AppxPackage -Update -ForceApplicationShutdown -Path \\<share>\Rigel\x64\Ship\AppPackages\*\*.appx -DependencyPath (Get-ChildItem \\<share>\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx | Foreach-Object {$_.FullName}) 

  ```

## <a name="admin-mode-and-device-management"></a>Mode Administrateur et gestion des appareils
<a name="AdminMode"> </a>

Certaines fonctions de gestion, comme l’installation manuelle d’un certificat privé de l’AC, nécessitent de basculer l’appareil Surface 4 en mode Administrateur.  
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-is-running"></a>Commutation en Admin Mode et lors de l’exécution de l’application v2 de systèmes de salle de Skype

1. Raccrochez les appels en cours et revenez à l’écran d’accueil.
    
2. Cliquez sur l’icône d’engrenage et afficher le menu (options sont des **paramètres**, **l’accessibilité**et **Redémarrer le périphérique** ).
    
3. Sélectionnez **Paramètres**.
    
4. Entrez le mot de passe de l’administrateur. L’écran d’installation s’affiche.
    
    > [!NOTE]
    > Si l’appareil ne possède pas de domaine joint, le compte administratif local (nom d’utilisateur "Admin") sera utilisé par défaut. Le mot de passe par défaut de ce compte est "sfb", mais il est recommandé que votre organisation le change dès que possible pour des raisons de sécurité. Si l’appareil possède un domaine joint, vous pouvez vous connecter avec un compte de domaine disposant des privilèges appropriés. 
  
5. Cliquez sur **Paramètres Windows** dans la colonne de gauche.
    
6. Sélectionnez **Atteindre connexion d’administration**.
    
7. Entrez le mot de passe de l’administrateur. Vous serez déconnecté de l’application et reviendrez à l’écran de connexion de Windows. 
    
8. Connectez-vous au bureau avec vos informations d’identification administrateur. Vous disposez des privilèges requis pour gérer l’appareil.
    
9. Exécutez les tâches administratives requises.
    
10. Déconnectez-vous du compte Administrateur.
    
11. Revenir à v2 de systèmes de salle de Skype en cliquant sur l’icône de compte d’utilisateur à l’extrême gauche de l’écran et sélectionnez **Skype**.
    
    Si l’utilisateur **Skype** n’est pas répertorié, vous devrez sélectionner **l’autre utilisateur** , puis entrez **. \skype** comme nom d’utilisateur et de connexion.
    
 La console est maintenant dans son mode de fonctionnement normal. La procédure suivante nécessite que vous permet de connecter un clavier à l’appareil si une n’est pas déjà attachée. 
  
### <a name="switching-to-admin-mode-and-back-when-the-skype-room-systems-v2-app-crashes"></a>Commutation en Admin Mode et lorsque l’application v2 Skype salle systèmes se bloque.

1. Appuyez rapidement cinq fois sur la touche Windows. L’écran de connexion de Windows apparaît.  
    
2. Connectez-vous au bureau avec vos informations d’identification administrateur.
    
    > [!NOTE]
    > Cette méthode ne déconnecte pas l’utilisateur de Skype ou ne ferme pas l’application. Vous ne devez toutefois l’utiliser que si l’application ne répond pas et que l’autre méthode n’est pas disponible. 
  
3. Exécutez les tâches administratives requises.
    
4. Redémarrez l’appareil lorsque vous avez terminé.
    
 Redémarrage de la console dans son mode de fonctionnement normal, l’application v2 de systèmes de salle de Skype en cours d’exécution. Vous pouvez retirer le clavier raccordé pour exécuter cette procédure, le cas échéant.
## <a name="troubleshooting-tips"></a>Astuces de dépannage
<a name="TS"> </a>

- Les invitations aux réunions peuvent ne pas apparaître lorsqu’elles sont envoyées sur plusieurs domaines (par exemple, entre deux entreprises). Dans de tels cas, les administrateurs informatiques devraient décidés de permettre ou non aux utilisateurs externes de planifier une réunion.
    
- Systèmes de salle Skype v2 ne supporte pas les redirections d’AutoDiscover d’Exchange via Exchange 2010.
    
- En général, il est recommandé aux administrateurs informatiques de désactiver les terminaux audio non destinés à être utilisés
    
- Dans le cas où une image miroir est affichée dans la prévisualisation de la salle, l’administrateur informatique peut corriger en mettant sous tension la caméra ou en retournant l’orientation de l’image à l’aide de la télécommande de la caméra.
    
- La perte de l’accès à l’écran tactile de la console est connue. Dans ce cas, le problème est parfois résolu en redémarrant le système v2 de systèmes de salle de Skype.
    
- La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue. Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.
    
## <a name="see-also"></a>Voir aussi
<a name="TS"> </a>

#### 

[Plan de salle de Skype systèmes v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Déployer Skype salle systèmes v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](../../deploy/deploy-clients/console.md)
  
[Gérer les paramètres de console de systèmes de salle Skype v2 à distance avec un fichier de configuration XML](xml-config-file.md)

