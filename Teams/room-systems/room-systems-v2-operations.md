---
title: Opérations et gestion des salles d’équipes Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Lisez cette rubrique pour en savoir plus sur la gestion des salles d’équipes Microsoft, la nouvelle génération de systèmes de salle Skype.
ms.openlocfilehash: efaf2a1bae7980855501b826d6a2ee902f0f56b2
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362789"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Opérations et gestion des salles d’équipes Microsoft 
 
Lisez cette rubrique pour en savoir plus sur la gestion des salles d’équipes Microsoft, la nouvelle génération de systèmes de salle Skype.
  
Salles d’équipes Microsoft est conçue pour transformer la salle de réunion en une expérience riche et collaborative la solution conférence le plus récent de Microsoft. Les utilisateurs bénéficiera de son Teams Microsoft familière ou Skype pour l’interface de l’entreprise et les administrateurs informatiques apprécierez une application Windows 10 Skype réunion facilement déployée et gérée. Salles d’équipes Microsoft est conçu pour tirer parti de l’équipement existant comme panneaux LCD pour faciliter d’installation pour intégrer des Teams Microsoft ou Skype pour les entreprises à la salle de réunion.
  
Avec une configuration supplémentaire, la gestion à distance est possible à l’aide de Microsoft Azure Monitor comme décrit dans la [gestion de planification Microsoft équipes salles avec Azure moniteur](azure-monitor-plan.md), [gestion de déployer Microsoft équipes salles avec Azure moniteur](azure-monitor-deploy.md), [gérer Périphériques de salles d’équipes Microsoft Azure moniteur](azure-monitor-deploy.md). Vous pouvez également [Gérer les salles d’équipes Microsoft paramètres à distance avec un fichier XML de configuration de la console](xml-config-file.md), qui inclut l’application d’un thème d’affichage personnalisé. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Collecte de journaux sur salles d’équipes Microsoft
<a name="Logs"> </a>

Pour collecter des journaux, vous devez appeler le script de collection de journal est fourni avec l’application Microsoft équipes salles. En mode d’administration, démarrez une invite de commandes avec élévation de privilèges et exécutez la commande suivante :
  
```
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Les journaux seront sortie dans un fichier ZIP c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Paramètres de l’écran d’affichage
<a name="Display"> </a>

Configurez l’écran d’affichage en mode étendu. Cela permet de garantir que la console de que l’interface utilisateur n’est pas dupliquée sur qui s’affichent lorsque vous interrompre l’alimentation de l’affichage.
  
> [!NOTE]
> Un téléviseur utilisé comme écran à l’avant de la salle doit prendre en charge/permettre la fonctionnalité CEC (Consumer Electronics Control ) HDMI afin de pouvoir basculer automatiquement sur une source vidéo active depuis le mode veille. Cette fonctionnalité n’est pas prise en charge sur tous les téléviseurs. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Les équipes Microsoft salles réinitialisation (restaurer usine)
<a name="Reset"> </a>

Si les salles d’équipes Microsoft ne fonctionne pas correctement, effectuer une réinitialisation peut-être vous aider. Cela peut s’effectuer dans l’application des paramètres sous l’onglet **récupération** sous **Réinitialiser ce PC**, sélectionnez **Démarrer**, puis **supprimez tout le contenu**. Suivez les invites restantes pour réinitialiser le périphérique.
  
> [!NOTE]
> Il existe un problème connu où les salles d’équipes Microsoft peut devenir inutilisables si l’option **Conserver mes fichiers - supprime les applications et les paramètres, mais conserve vos fichiers personnels** est sélectionnée au cours du processus de réinitialiser Windows. Effectuez _pas_ utiliser cette option.
  
## <a name="supported-remote-options"></a>Options distantes prises en charge
<a name="RemoteOptions"> </a>

Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.
  

|**Groupe de travail **|**Aucun domaine joint**|**Domaine joint**|
|:-----|:-----|:-----|
|Redémarrer  <br/> |Bureau distant  <br/> Powershell distant  <br/> |Bureau à distance (nécessite une configuration supplémentaire)  <br/> Powershell distant (nécessite une configuration supplémentaire)  <br/> SCCM  <br/> |
|Mise à jour du SE  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Mise à jour de l';application  <br/> |	Windows Store  <br/> |Windows Store  <br/> SCCM  <br/> |
|Configuration du compte Skype  <br/> |Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
|Accès aux journaux  <br/> |	Actuellement pas pris en charge  <br/> |	Actuellement pas pris en charge  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuration de la stratégie de groupe pour les équipes Microsoft salles
<a name="GroupPolicy"> </a>

Cette section traite des paramètres système qui dépend de salles d’équipes Microsoft fonctionne correctement. Pour prendre part à des salles d’équipes Microsoft à un domaine, assurez-vous que votre stratégie de groupe ne remplace pas les paramètres dans le tableau suivant.
  

|**Paramètre**|**Permet de**|
|:-----|:-----|
|HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permet de salles d’équipes Microsoft amorçage  <br/> |
|Gestion - de l’alimentation\> sur CA, désactiver écran au bout de 10 minutes  <br/> Gestion - de l’alimentation\> sur CA, placez jamais système en mode veille  <br/> |Permet de salles d’équipes Microsoft activer affiche attaché et réactiver automatiquement  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.  <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |
   
Transfert de fichiers à l’aide de stratégies de groupe est traitée dans [un élément de fichier de configuration](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Vous pouvez effectuer les opérations suivantes de gestion à distance à l’aide de PowerShell (voir le tableau ci-dessous pour les exemples de script) :
  
- Obtenir les périphériques raccordés
    
- Obtenir l';état de l';application
    
- Obtenir les informations système
    
- Redémarrer le système
    
- Récupérer les journaux
    
- Transférer des fichiers (requiert un salles d’équipes Microsoft à un domaine)
    
> [!NOTE]
> Cette fonctionnalité est désactivée par défaut. Vous devez activer PowerShell à distance pour votre environnement sur le système de salles d’équipes Microsoft effectuer les opérations ci-dessous. Reportez-vous à la documentation sur **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** pour plus d’informations sur l’activation de PowerShell à distance.
  
Par exemple, vous pouvez activer PowerShell à distance comme suit :
  
1. Connectez-vous en tant qu’administrateur sur un appareil Microsoft équipes salles.
    
2. Ouvrez une invite de commandes PowerShell avec élévation de privilèges.
    
3. Entrez la commande suivante : Enable-PSRemoting -force
    
Pour effectuer une opération de gestion :
  
1. Connectez-vous à un ordinateur avec les informations d’identification de compte qui est autorisé à exécuter des commandes PowerShell sur un appareil Microsoft équipes salles.
    
2. Ouvrez une invite de commandes PowerShell régulière sur le PC.
    
3. Copiez le texte de commande à partir du tableau ci-après et collez-le à l’invite.
    
4. Remplacez `<Device fqdn>` champs dont les valeurs de nom de domaine complet approprié à votre environnement.
    
5. Remplacez * \<chemin d’accès\> * avec le nom de fichier et chemin d’accès local du fichier de configuration maître SkypeSettings.xml (ou image de thème).
    
Pour obtenir des équipements
  
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

Distribuer un fichier de configuration XML (ou les graphismes)
  
```
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Mises à jour logicielles
<a name="SWupdate"> </a>

Par défaut, salles d’équipes Microsoft essaie de se connecter à la banque de Windows pour obtenir la dernière version du logiciel Microsoft équipes salles, afin que le périphérique devra être régulière accès à internet. Avant de contacter Microsoft ayant des problèmes de prise en charge, assurez-vous que le périphérique Microsoft équipes salles est chargé avec la dernière version de l’application.
  
Par défaut, les salles d’équipes Microsoft se connecte à Windows Update pour récupérer le système d’exploitation et les mises à jour de microprogramme de périphérique USB et les installe en dehors des heures ouvrées configurés. Vous pouvez configurer les heures d’ouverture en vous connectant au compte administrateur et en exécutant l’application Paramètres.
  
Si vous souhaitez gérer manuellement les mises à jour et que vous ne parvenez pas à la procédure normale pour le [Magasin de Microsoft pour les entreprises](https://businessstore.microsoft.com/store) à [distribuer des applications en mode hors connexion](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), vous pouvez vous procurer le fichier APPX approprié et les dépendances dans le [kit de déploiement](https://go.microsoft.com/fwlink/?linkid=851168) (à partir de les instructions pour [configurer une console Microsoft équipes salles](console.md)) qui peut être utilisé avec SCCM. La version de kit de déploiement retard sur la version de la banque, afin qu’il correspondent ne peut-être pas toujours à la dernière version disponible.
  
### <a name="to-update-using-powershell"></a>Pour mettre à jour à l’aide de Powershell

1. Extraire le package de l’installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) sur un partage de l’appareil peut accéder.
    
2. Exécutez le script suivant ciblant les périphériques salles des équipes Microsoft, la modification \<partager\> au périphérique partager le cas échéant :
    
```
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>Mode Administrateur et gestion des appareils
<a name="AdminMode"> </a>

Certaines fonctions de gestion, comme l’installation manuelle d’un certificat d’autorité de certification privé, nécessitent plaçant le périphérique Surface Pro en mode Admin. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Passer en Admin Mode et lorsque l’application Microsoft équipes salles est en cours d’exécution

1. Raccrocher tous les appels en cours et revenir à l’écran d’accueil.
    
2. Sélectionnez l’icône d’engrenage et afficher le menu (options sont **les paramètres**, **accessibilité**et **Redémarrez le dispositif** ).
    
3. Sélectionnez **Paramètres**.
    
4. Entrez le mot de passe de l’administrateur. L’écran d’installation s’affiche.
    
    > [!NOTE]
    > Si le périphérique n’est pas joint au domaine, le compte d’administrateur local (nom d’utilisateur « Admin ») sera utilisé par défaut. Le mot de passe par défaut de ce compte est "sfb", mais il est recommandé que votre organisation le change dès que possible pour des raisons de sécurité. Si l’ordinateur est joint au domaine, vous pouvez vous connecter avec un compte de domaine correctement privilégié. 
  
5. Dans la colonne de gauche, sélectionnez **Paramètres Windows** .
    
6. Sélectionnez **Atteindre connexion d’administration**.
    
7. Entrez le mot de passe de l’administrateur. Vous serez déconnecté de l’application et reviendrez à l’écran de connexion de Windows. 
    
8. Connectez-vous au bureau avec vos informations d’identification administrateur. Vous devez les privilèges nécessaires pour gérer le périphérique.
    
9. Exécutez les tâches administratives requises.
    
10. Déconnectez-vous du compte Administrateur.
    
11. Revenez à Microsoft équipes salles en sélectionnant l’icône de compte d’utilisateur sur le côté gauche de l’écran, puis **Skype**.
    
    Si l’utilisateur **Skype** n’est pas répertorié, vous devrez peut-être sélectionnez **autre utilisateur** , puis entrez **. \skype** comme nom d’utilisateur et de connexion.
    
La console est désormais dans son mode de fonctionnement normal. La procédure suivante nécessite que vous attacher un clavier à l’appareil si une n’est pas déjà attachée. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Passer en Admin Mode et lorsque l’application Microsoft équipes salles se bloque

1. Appuyez rapidement cinq fois sur la touche Windows. L’écran de connexion de Windows apparaît. 
    
2. Connectez-vous au bureau avec vos informations d’identification administrateur.
    
    > [!NOTE]
    > Cette méthode ne déconnecter l’utilisateur Skype ou terminer correctement l’application, mais vous pouvez l’utiliser si l’application n’a pas été répond et l’autre méthode n’était pas disponible. 
  
3. Exécutez les tâches administratives requises.
    
4. Redémarrez l’ordinateur lorsque vous avez terminé.
    
   Redémarrage de la console dans son mode de fonctionnement normal, l’application de salles d’équipes Microsoft en cours d’exécution. Vous pouvez supprimer le clavier, si elle a été attachée afin que vous puissiez effectuer cette procédure.
   ## <a name="troubleshooting-tips"></a>Astuces de dépannage
   <a name="TS"> </a>

- Les invitations aux réunions peut ne pas apparaîtront lors de l’envoi au-delà des frontières du domaine (par exemple, entre les deux sociétés). Dans ce cas, les administrateurs informatiques doivent décider s’il faut autoriser les utilisateurs externes organiser une réunion.
    
- Salles d’équipes Microsoft ne prend pas en charge la découverte automatique Exchange redirige via Exchange 2010.
    
- En règle générale, il est recommandé pour les administrateurs informatiques désactiver les points de terminaison audio que n’envisagez pas d’utiliser.
    
- Dans le cas où une image miroir est affichée dans la prévisualisation de la salle, l’administrateur informatique peut corriger en mettant sous tension la caméra ou en retournant l’orientation de l’image à l’aide de la télécommande de la caméra.
    
- La perte de l’accès à l’écran tactile de la console est connue. Dans ce cas, le problème est parfois résolu en redémarrant le système de salles d’équipes Microsoft.
    
- La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue. Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.
    
