---
title: maintenance et opérations Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: En savoir plus sur la gestion des Salles Microsoft Teams.
ms.openlocfilehash: e214d0b438ea7dd9b710a7aba8597de6c5b76bdf
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106259"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>maintenance et opérations Salles Microsoft Teams
 
 
Salles Microsoft Teams est la solution de conférence de Microsoft conçue pour transformer votre salle de réunion en une expérience riche et collaborative. Les utilisateurs apprécieront son interface Microsoft Teams ou Skype Entreprise familière, et les administrateurs informatiques apprécieront une application Windows 10 salles Teams facile à déployer et managée. Salles Microsoft Teams est conçu pour tirer parti de l’équipement existant pour faciliter l’installation afin d’amener Microsoft Teams ou Skype Entreprise dans votre salle de réunion.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Collecte des journaux d’activité sur Salles Microsoft Teams
<a name="Logs"> </a>

Pour collecter des journaux dans Teams centre d’administration, accédez à **Teams appareils > salles Teams sur Windows**. Sélectionnez le nom complet de l’appareil pour lequel vous souhaitez ouvrir des journaux. Dans le panneau supérieur, sélectionnez « Télécharger les journaux d’activité des appareils ». Une fois que vous avez confirmé, les journaux d’activité seront prêts à être téléchargés dans l’onglet Historique après quelques minutes.

Vous pouvez également utiliser PowerShell pour collecter des journaux. Vous devez appeler le script de collecte de journaux fourni avec l’application Salles Microsoft Teams. En [mode Administrateur](rooms-operations.md), démarrez une invite de commandes avec élévation de privilèges et exécutez la commande suivante :
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

Les journaux d’activité sont générés sous la forme d’un fichier ZIP dans c:\rigel.
  
## <a name="front-of-room-display-settings"></a>Paramètres d’affichage de l’avant de la salle
<a name="Display"> </a>

Configurez les paramètres de vos affichages avant de salle pour prendre en charge le contrôle Électronique grand public (CEC) ou activer le mode PC.
  
Si vous souhaitez qu’un écran avant de la salle bascule automatiquement vers salles Teams lorsqu’il sort du mode veille, certaines conditions doivent être remplies. Cette fonctionnalité est facultative, mais prise en charge par Salles Microsoft Teams logiciel, à condition que le matériel sous-jacent prenne en charge la fonctionnalité. Un téléviseur grand public utilisé comme écran frontal doit prendre en charge la fonctionnalité CCE (Consumer Electronics Control) de HDMI.  Selon la station d’accueil ou la console sélectionnée (qui peut ne pas prendre en charge CEC, reportez-vous à la documentation de support du fabricant), un contrôleur tel qu’un [contrôleur HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron ou [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) d’Extron peut être nécessaire pour activer le comportement souhaité.

### <a name="scale-and-resolution"></a>Mise à l’échelle et résolution

Pour obtenir salles Teams expérience conçue, vos écrans Front of Room doivent répondre aux exigences de résolution et de mise à l’échelle.

Pour définir l’échelle et la résolution de vos affichages front of Rooms à distance, consultez [Gérer les paramètres de la console Salles Microsoft Teams à distance avec un fichier de configuration XML](xml-config-file.md#set-front-of-room-scale-and-resolution).

Pour définir manuellement la mise à l’échelle et la résolution dans les paramètres d’administration Teams Room :

1. Dans votre Teams Room, basculez en [mode administrateur](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. Sélectionnez l’icône de démarrage. Afficher ensuite **Paramètres > > système**

3. Accédez à **Mettre à l’échelle et à la disposition**, puis **modifiez la taille du texte, des applications et d’autres éléments**, puis définissez la mise à l’échelle sur 100 %.

4. Définissez la résolution d’affichage sur 1080p. Si vous avez deux moniteurs, définissez l’échelle et la résolution pour les deux écrans.

5. Ensuite, sélectionnez l’icône de démarrage et entrez **l’invite de commandes**. Sélectionnez **Exécuter en tant qu’administrateur**.

6. Exécutez la commande suivante :

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. Redémarrez l’appareil.
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>réinitialisation Salles Microsoft Teams (restauration d’usine)
<a name="Reset"> </a>

Si Salles Microsoft Teams ne s’exécute pas correctement, l’exécution d’une réinitialisation d’usine peut vous aider. Pour ce faire, utilisez [l’outil de récupération Microsoft Teams Room](recovery-tool.md) et suivez les instructions de restauration d’usine.

> [!NOTE]
> Il existe un problème connu où l’Salles Microsoft Teams peut devenir inutilisable si l’option **Conserver mes fichiers - Supprime les applications et les paramètres, mais conserve votre option de fichiers personnels** est sélectionnée pendant le processus de réinitialisation Windows. *N’utilisez pas* cette option.
  
## <a name="supported-remote-options"></a>Options distantes prises en charge
<a name="RemoteOptions"> </a>

Le tableau suivant récapitule les opérations distantes possibles et les méthodes que vous pouvez utiliser pour les accomplir.
  

|Groupe de travail |Aucun domaine joint|Domaine joint|
|:-----|:-----|:-----|
|Redémarrer  <br/> |centre d’administration Teams  <br/> Bureau distant  <br/> PowerShell distant  <br/> | <br/>Bureau à distance (nécessite une configuration supplémentaire)  <br/> PowerShell distant (nécessite une configuration supplémentaire)  <br/> Configuration Manager  <br/> |
|Mise à jour du SE  <br/> |Windows Update  <br/> |Windows Update  <br/> WSUS  <br/> |
|Mise à jour de l';application  <br/> |	Windows Store  <br/> |Windows Store  <br/> Configuration Manager  <br/> |
|Configuration du compte  <br/> |centre d’administration Teams  <br/> |centre d’administration Teams  <br/> |
|Accès aux journaux  <br/> |centre d’administration Teams  <br/> Powershell  <br/> |centre d’administration Teams <br/> Powershell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Configuration de stratégie de groupe pour Salles Microsoft Teams
<a name="GroupPolicy"> </a>

Cette section traite des paramètres système dont Salles Microsoft Teams dépend pour fonctionner correctement. 

Joindre salles Teams à un domaine Active Directory offre les avantages suivants :

- La jonction de domaine salles Teams vous permet d’accorder des droits d’administration aux utilisateurs de domaine et aux groupes. En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.

- Vous pouvez déployer Windows configuration de la qualité de service sur salles Teams.

- Si vous utilisez Skype Entreprise, la jonction de domaine au salles Teams automatise l’importation de la chaîne de certificats racine privée de votre organisation.

Lorsque vous joignez salles Teams à un domaine, vous devez créer une unité d’organisation distincte afin de pouvoir fournir des exclusions stratégie de groupe Object (GPO) à l’unité d’organisation où résident tous les objets salles Teams. Désactivez l’héritage de tous les objets de stratégie de groupe afin que les paramètres de stratégie de groupe non pris en charge ne soient pas appliqués à salles Teams. Créez des objets de machine dans l’unité d’organisation avant de joindre salles Teams au domaine pour vous assurer que les stratégies de groupe appliquées à l’unité d’organisation par défaut des ordinateurs ne sont pas appliquées.

> [!NOTE]
> Même si vous créez une unité d’organisation distincte et bloquez l’héritage, certaines stratégies de groupe peuvent provoquer des problèmes si aucun remplacement n’est défini. Un stratégie de groupe sans remplacement bat une unité d’organisation avec un jeu d’héritage de stratégie de bloc.

De nombreuses organisations ont les objets de stratégie de groupe suivants, qui affectent salles Teams fonctionnalités. Veillez à remplacer ou bloquer l’héritage de ces éléments :

  - Délai d’ouverture de sessions (verrouillage automatique)
  - Stratégies connexes de gestion de l’alimentation
  - Besoin d’étapes d’authentification supplémentaires
  - Accès aux lecteurs locaux refusé
  - Inviter les utilisateurs à des connexions réseau lentes
  - Démarrer un programme donné à l’ouverture
  - Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.
  - Envoyer (push) Windows Update à salles Teams

Lorsque vous joignez Salles Microsoft Teams à un domaine, assurez-vous que vos stratégies de groupe ne remplacent pas les paramètres du tableau suivant.

|Paramètres|Permet|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Permet à Salles Microsoft Teams de démarrer  <br/> |
|Gestion de l’alimentation :\> sur AC, désactivez l’écran après 10 minutes  <br/> Gestion de l’alimentation -\> Sur ac, ne jamais mettre le système en veille  <br/> |Permet à Salles Microsoft Teams de désactiver les affichages attachés et de se réveiller automatiquement  <br/> |
|net accounts /maxpwage:unlimited  <br/> Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local. Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe. Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.   <br/> |Active le compte Skype avec lequel toujours se connecter  <br/> |

> [!NOTE]
> Quand Salles Microsoft Teams est compatible avec la prochaine version de Windows 10 système d’exploitation, salles Teams automatiquement mises à jour vers la version suivante via Windows Update. Salles Microsoft Teams ne doit pas être mis à niveau vers la prochaine version de Windows 10 manuellement ou via l’activation des stratégies de groupe Windows Update for Business (WUFB) « Sélectionner le niveau de préparation Windows pour les mises à jour que vous souhaitez recevoir » et « Sélectionner lors de la réception des versions d’évaluation et des mises à jour des fonctionnalités » par le biais de l’objet de stratégie de groupe. salles Teams avec ces stratégies de groupe activées est connu pour rencontrer des problèmes avec Windows 10 mises à jour du système d’exploitation.

## <a name="remote-management-using-powershell"></a>Gestion distante à l’aide de PowerShell
<a name="RemotePS"> </a>

Vous pouvez effectuer les opérations de gestion suivantes à distance à l’aide de PowerShell (consultez le tableau ci-dessous pour obtenir des exemples de scripts) :
  
- Obtenir les périphériques raccordés
- Obtenir l';état de l';application
- Obtenir les informations système
- Redémarrer le système
- Récupérer les journaux
- Transférer des fichiers (nécessite un Salles Microsoft Teams joint à un domaine)
    
> [!NOTE]
> Cette fonctionnalité est désactivée par défaut. Vous devez activer PowerShell à distance pour votre environnement sur le système Salles Microsoft Teams afin d’effectuer les opérations ci-dessous. Reportez-vous à la documentation sur **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** pour plus d’informations sur l’activation de PowerShell à distance.
  
Par exemple, vous pouvez activer PowerShell à distance comme suit :
  
1. Connectez-vous en tant qu’administrateur sur un appareil Salles Microsoft Teams.
2. Ouvrez une invite de commandes PowerShell avec élévation de privilèges.
3. Entrez la commande suivante : `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. Ouvrez la stratégie de sécurité locale et ajoutez le groupe de sécurité *Administrateurs* à **Security Paramètres** >  **Local PoliciesUser** >  **Rights AssignmentAccess** >  **à partir du réseau**.

Pour effectuer une opération de gestion :
  
1. Connectez-vous à un PC avec des informations d’identification de compte qui ont l’autorisation d’exécuter des commandes PowerShell sur un appareil Salles Microsoft Teams.
2. Ouvrez une invite de commandes PowerShell standard sur le PC.
3. Copiez le texte de la commande du tableau ci-dessous et collez-le à l’invite.
4. Remplacez  `<Device fqdn>` les champs par des valeurs de nom de domaine complet appropriées à votre environnement.
5. Remplacez  *\<path\>*  par le nom de fichier et le chemin d’accès local du fichier de configuration SkypeSettings.xml maître (ou image de thème).
    
Pour obtenir des appareils attachés
  
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

Envoyer (push) un fichier de configuration XML (ou un graphique de thème)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>Mises à jour logicielles
<a name="SWupdate"> </a>

Par défaut, Salles Microsoft Teams tente de se connecter au Windows Store pour obtenir la dernière version de Salles Microsoft Teams logiciel. Par conséquent, salles Teams nécessite un accès Internet régulier. Avant de contacter Microsoft avec des problèmes de support, assurez-vous que Salles Microsoft Teams est chargé avec la dernière version de l’application.
  
Salles Microsoft Teams se connecte à Windows Update pour récupérer les mises à jour du microprogramme du système d’exploitation et des périphériques. Il se connecte également au Microsoft Store pour récupérer les mises à jour d’application.

Si vous devez gérer les mises à jour des applications manuellement, mais que vous ne pouvez pas suivre la procédure normale pour [Microsoft Store pour Entreprises](https://businessstore.microsoft.com/store) distribuer des [applications hors connexion](/microsoft-store/distribute-offline-apps), vous pouvez acquérir salles Teams packages de mise à jour pour effectuer des mises à jour d’application sur les systèmes d’exploitation pris en charge. La mise à jour peut être en retard par rapport à la version du magasin, et elle peut ne pas toujours correspondre à la dernière build disponible. Pour plus d’informations, consultez [Mettre à jour manuellement un appareil Salles Microsoft Teams](manual-update.md).

## <a name="admin-mode-and-device-management"></a>Mode Administrateur et gestion des appareils
<a name="AdminMode"> </a>

Certaines fonctions de gestion, telles que l’installation manuelle d’un certificat d’autorité de certification privé, nécessitent de placer salles Teams en mode Administrateur. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Basculement vers le mode Administrateur et retour lorsque l’application Salles Microsoft Teams est en cours d’exécution

1. Raccrochez tous les appels en cours et revenez à l’écran d’accueil.
2. Sélectionnez l’icône Engrenage et affichez le menu (les options sont **Paramètres**, **Accessibilité** et **Redémarrer l’appareil**).
3. Sélectionnez **Paramètres**.
4. Entrez le mot de passe administrateur. L’écran d’installation s’affiche.  Si l’appareil n’est pas joint à un domaine, le compte d’administration local (nom d’utilisateur « Administrateur ») est utilisé par défaut. Le mot de passe par défaut de ce compte est « sfb ». Modifiez ce mot de passe dès que possible. Si l’ordinateur est joint à un domaine, vous pouvez vous connecter avec un compte de domaine disposant des privilèges appropriés.
5. Sélectionnez **Windows Paramètres** dans la colonne de gauche.
6. Connectez-vous au bureau avec vos informations d’identification administrateur. Vous disposez des privilèges nécessaires pour gérer l’appareil.
7. Exécutez les tâches administratives requises.
8.  Redémarrez l’ordinateur lorsque vous avez terminé.
    
La console revient à présent à son mode de fonctionnement normal. La procédure suivante nécessite le raccordement d’un clavier à l’appareil si ce n’est pas déjà fait.  
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Basculement vers le mode Administrateur et retour en cas de blocage de l’application Salles Microsoft Teams

1. Appuyez rapidement cinq fois sur la touche Windows. L’écran de connexion de Windows apparaît.  
2. Connectez-vous au bureau avec vos informations d’identification administrateur.
3. Exécutez les tâches administratives requises.
4. Redémarrez l’ordinateur lorsque vous avez terminé.

    > [!NOTE]
    > Cette méthode ne journalise pas l’utilisateur Skype désactivé ou termine correctement l’application, mais vous l’utiliseriez si l’application ne répondait pas et que l’autre méthode n’était pas disponible. 

   La console redémarre en mode d’opération normal, exécutant l’application Salles Microsoft Teams. Vous pouvez supprimer le clavier si vous en avez attaché un pour effectuer cette procédure.
   ## <a name="troubleshooting-tips"></a>Astuces de dépannage
   <a name="TS"> </a>

- Les invitations à une réunion peuvent ne pas apparaître lorsqu’elles sont envoyées au-delà des limites de domaine (par exemple, entre deux entreprises). Dans ce cas, les administrateurs informatiques doivent décider s’il faut autoriser les utilisateurs externes à planifier une réunion. Consultez l’article relatif à la Exchange l’applet de commande PowerShell [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), en particulier le paramètre « ProcessExternalMeetingMessages ».
- Salles Microsoft Teams ne prend pas en charge les redirections de découverte automatique Exchange via Exchange 2010.
- En général, il est recommandé aux administrateurs informatiques de désactiver les points de terminaison audio qu’ils n’ont pas l’intention d’utiliser.
- Dans le cas où une image miroir s’afficherait en préversion de la salle, l’administrateur informatique peut corriger le problème en mettant l’appareil photo sous tension ou en renversant l’orientation de l’image à l’aide des paramètres de l’appareil photo.
- La perte de l’accès à l’écran tactile de la console est connue. Dans ce cas, le problème est parfois résolu en redémarrant salles Teams.
- La perte de l’audio local lors de la connexion d’un ordinateur à la console via une réception par câble est connue. Dans ce cas, le redémarrage de l’ordinateur peut résoudre le problème de lecture audio locale.
