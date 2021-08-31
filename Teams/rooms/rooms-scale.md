---
title: Déployer des Salles Microsoft Teams l’aide Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Découvrez comment déployer des déploiements Salles Microsoft Teams à grande échelle à l’aide de Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 27cd37df8516973ddf9fbe6401a1e4c21ce01e0a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731573"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Déployer des Salles Microsoft Teams l’aide de Microsoft Endpoint Configuration Manager

Cet article vous fournit toutes les informations nécessaires à la création de Salles Microsoft Teams déploiements à l’aide de Microsoft Endpoint Configuration Manager.

Grâce aux méthodes simples d’utilisation fournies par Configuration Manager, vous pouvez déployer le système d’exploitation et d’autres applications sur plusieurs appareils cibles.

Utilisez l’approche illustrée ci-dessous pour vous guider tout au long de votre configuration de Configuration Manager et personnaliser les exemples de packages et de scripts fournis dans le cadre de ces instructions, selon les besoins de votre organisation.

![Salles Microsoft Teams déploiement à l’aide de Configuration Manager.](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Cette solution n’a été testée qu’avec Surface Pro déploiements basés sur des déploiements. Suivez les instructions du fabricant pour les configurations qui ne sont pas basées sur Surface Pro.

## <a name="validate-prerequisites"></a>Valider les conditions préalables

Pour déployer des Salles Microsoft Teams avec Configuration Manager, assurez-vous que vous respectez les conditions préalables et requises suivantes.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager requise

-   Microsoft Endpoint Configuration Manager version doit être au moins 1706. Nous vous recommandons d’utiliser 1710 ou une date ultérieure. Consultez [la prise en charge Windows 10 de Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) pour en savoir plus sur les versions Windows 10 que Configuration Manager prend en charge.

-   Une version prise en charge Windows Kit de déploiement et d’évaluation de l’Windows 10 doit être installée. Consultez les versions du [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) que vous pouvez utiliser avec différentes versions de Configuration Manager et assurez-vous que votre déploiement inclut la version correcte.

-   Le rôle de point de distribution doit avoir été attribué aux serveurs système de site et les images de démarrage doivent être activées pour la prise en charge de l’environnement d’exécution de [préboot (PXE)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) pour permettre les déploiements initiés par le réseau. Si la prise en charge de PXE n’est pas activée, vous pouvez utiliser un support [démarrageable](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements.

-   Un compte d’accès réseau doit être configuré pour prendre en charge de nouveaux scénarios de déploiement d’ordinateurs (métal métallique). Pour en savoir plus sur la configuration d’un compte d’accès réseau, voir [Comptes utilisés dans Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   Nous vous recommandons d’activer la prise en charge [multicast,](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)si vous êtes susceptible de déployer la même image Salles Microsoft Teams plusieurs unités en même temps.

### <a name="networking-requirements"></a>Exigences en matière de mise en réseau

-   Votre réseau doit avoir un serveur DHCP (Dynamic Host Configuration Protocol), configuré pour la distribution automatique d’adresses IP sur les sous-réseaux où Salles Microsoft Teams unités seront déployées.

    > [!NOTE]
    > La durée du contrat de location DHCP doit être définie sur une valeur plus longue que la durée du déploiement de l’image. Dans le cas contraire, le déploiement peut échouer.

-   Votre réseau, y compris les commutateurs et les réseaux lan virtuels (VLAN), doit être configuré pour prendre en charge PXE. Pour plus d’informations sur les configurations IP Helper et PXE, reportez-vous à votre fournisseur réseau. Vous pouvez également utiliser un support [qui](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) démarre pour vos déploiements, si la prise en charge de PXE n’est pas activée.

    > [!NOTE]
    > Pour Surface Pro, le démarrage à partir du réseau (démarrage PXE) n’est pris en charge que lorsque vous utilisez un adaptateur Ethernet ou une station d’accueil microsoft. Les cartes Ethernet tierces ne supportent pas le démarrage PXE avec Surface Pro. Pour [plus d’informations,](/surface/ethernet-adapters-and-surface-device-deployment) voir les cartes Ethernet et le déploiement de Surface.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Configurer des Microsoft Endpoint Configuration Manager pour le déploiement du système d’exploitation

Cet article part du principe que vous avez déjà un déploiement de Configuration Manager sain et ne détaille pas toutes les étapes requises pour déployer et configurer Configuration Manager de toutes pièces. La [documentation et les conseils de configuration sur](/configmgr/) le Microsoft Endpoint Configuration Manager ressources sont très précieuses ; nous vous recommandons de commencer avec ces ressources si vous n’avez pas encore déployé Configuration Manager.

Utilisez les instructions suivantes pour vérifier que les fonctionnalités de déploiement du système d’exploitation sont correctement configurées.

### <a name="validate-and-upgrade-configuration-manager"></a>Valider et mettre à niveau Configuration Manager

1.  Dans la console Configuration  Manager, sélectionnez Mises à jour \> **d’administration et Maintenance.**

2.  Vérifiez la build installée et les mises à jour applicables qui n’ont pas encore été installées.

3.  Passer [en revue la prise en charge Windows 10 dans Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); si vous avez besoin de mettre à niveau votre déploiement, sélectionnez la mise à jour que vous voulez installer, puis sélectionnez **Télécharger.**

4.  Une fois le téléchargement terminé, sélectionnez la mise à jour, puis sélectionnez **Installer le pack de mise à jour.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurer des points de distribution pour prendre en charge PXE et multicast

1.  Dans la console Configuration Manager, sélectionnez **Points de** \> **distribution** Administration.

2.  Sélectionnez le serveur de points de distribution qui servira Salles Microsoft Teams déploiement, puis **Propriétés.**

3.  Sélectionnez **l’onglet PXE** et assurez-vous que les paramètres suivants sont activés :
    -   Activer la prise en charge PXE pour les clients
    -   Autoriser ce point de distribution à répondre aux demandes PXE entrantes
    -   Activer le support informatique inconnu

4.  *Facultatif :* Pour activer la prise en charge **multicast,** sélectionnez l’onglet Multicast et assurez-vous que les paramètres suivants sont activés :
    -   Activer la multicast pour envoyer simultanément des données à plusieurs clients
    -   Configurer la plage de ports UDP selon les recommandations de votre équipe réseau

### <a name="configure-the-network-access-account"></a>Configurer le compte d’accès réseau

1.  Dans la console Configuration  Manager, allez sur Sites de configuration du \> **site** \> Administration, puis sélectionnez le site.

2.  Dans le **Paramètres,** sélectionnez **Configurer la distribution de logiciels de composants de** \> **site.**

3.  Sélectionnez **l’onglet Compte d’accès** réseau. Configurer un ou plusieurs comptes, puis sélectionner **OK.**

> [!NOTE]
> Les comptes n’ont pas besoin de droits spéciaux, à l’exception de **l’ordinateur Access de** ce réseau, directement sur le serveur du point de distribution. Un compte d’utilisateur de domaine générique sera approprié. Pour plus d’informations, [voir Comptes utilisés dans Configuration Manager.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Configurer une image de démarrage

1.  Dans la console Configuration Manager, sélectionnez **Images de** démarrage du système d’exploitation \> **Bibliothèque** \> **de logiciels.**

2.  Sélectionnez **Image de démarrage (x64),** puis **Propriétés.**

3.  Sélectionnez **l’onglet Source** de données et **activez l’image** de démarrage à partir du point de distribution activé pour PXE.

4.  Sélectionnez **l’onglet Composants facultatifs** pour installer les composants requis :

    1.  Sélectionnez l’icône d’étoile et **recherchez HTML (WinPE-HTA)**

    2.  Sélectionnez **OK** pour ajouter la prise en charge de l’application HTML à l’image de démarrage.

5.  *Facultatif :* Pour personnaliser l’expérience de déploiement, sélectionnez **l’onglet Personnalisation.**
    -   Activez la prise en charge des commandes **(test uniquement)** si vous voulez avoir accès à une invite de commandes pendant le déploiement. Lorsque cette commande est activée, vous pouvez démarrer une invite de commandes en sélectionnant **F8** à tout moment pendant le déploiement.
    -   Vous pouvez également spécifier une image d’arrière-plan personnalisée à afficher pendant le déploiement. Pour définir une image, activez Spécifier le fichier d’image d’arrière-plan **personnalisé (chemin UNC et** sélectionnez votre arrière-plan.

6.  Lorsque vous y avez été invité, **sélectionnez Oui** et distribuez l’image de démarrage mise à jour à vos points de distribution.

Pour plus d’informations, voir [Gérer les images de démarrage avec Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> Vous pouvez créer un support USB en démarrage pour initier des déploiements de séquence de tâches dans Configuration Manager pour les environnements qui n’ont pas de prise en charge PXE. Le support de démarrage contient uniquement l’image de démarrage, les commandes de démarrage facultatives et les fichiers requis, et les fichiers binaires de Configuration Manager pour prendre en charge le démarrage dans Windows PE et la connexion à Configuration Manager pour le reste du processus de déploiement. Pour plus d’informations, voir [Créer un média qui peut être démarré.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Créer des packages Configuration Manager

> [!IMPORTANT]
> La version requise du système d’exploitation pour chaque version du programme d’installation SRS change à chaque publication MSI. Pour déterminer la meilleure version du système d’exploitation pour un MSI donné, exécutez le script de configuration de la console une seule fois. Pour en savoir plus, [consultez La Salles Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager.](rooms-scale.md)

Configuration Manager nécessite un certain nombre de packages pour déployer et configurer les unités Salles Microsoft Teams packages.

Vous devez créer et configurer les packages suivants, puis les distribuer aux systèmes de site Configuration Manager qui ont reçu le rôle de serveur de point de distribution.

| **Nom du package**                     | **Type**               | **Description**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - Package d’application SRS     | Package logiciel       | Package pour le kit de déploiement Salles Microsoft Teams’équipe                                      |
| SRS v2 - Sysprep Package             | Package logiciel       | Package pour le groupe Unattended.xml configure les unités Salles Microsoft Teams personnalisées            |
| SRS v2 - Set-SRSComputerName Package | Package logiciel       | Package pour l’application HTML (HTA) pour affecter un nom d’ordinateur pendant le déploiement    |
| SRS v2 - Configurer la configuration SRS         | Package logiciel       | Package de configuration du déploiement de l’application Salles Microsoft Teams                          |
| SRS v2 - Package de mises à jour du système d’exploitation          | Package logiciel       | Package pour déployer des mises à jour de système d’exploitation obligatoires                                      |
| SRS v2 - Package de certificat racine    | Package logiciel       | Facultatif - Package pour déployer le certificat racine (non requis pour les unités jointes au domaine)  |
| SRS v2 - Microsoft Monitoring Agent package | Package logiciel       | Facultatif - Package pour déployer et configurer l’agent de la suite Microsoft Operations Management|
| SRS v2 - Package d’arrière-plan WinPE    | Package logiciel       | Package pour l’image d’arrière-plan personnalisée à utiliser avec les images de démarrage                           |
| Windows 10 Entreprise                | Image du système d’exploitation | Package pour le fichier d’installation du système d’exploitation (install.wim)                          |
| Surface Pro                          | Package du pilote         | Package pour les pilotes de périphériques et le microprogramme de Microsoft Surface Pro                     |
| Surface Pro 4                        | Package du pilote         | Package pour les pilotes de périphérique et microprogramme pour Microsoft Surface Pro 4                   |

Pour plus d’informations, voir [Packages et programmes dans Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>Créer des dossiers pour les fichiers source du package

Configuration Manager nécessite que les fichiers source de package soient organisés dans une structure de dossiers spécifique lors de leur création et de leur mise à jour.

Créez la structure de dossiers suivante sur le Microsoft Endpoint Configuration Manager d’administration centrale ou le site principal, ou sur un partage serveur que vous utilisez pour héberger des fichiers source de package :

-   SRS v2 - Microsoft Monitoring Agent package
-   SRS v2 - Package de mises à jour du système d’exploitation
-   SRS v2 - Package de certificat racine
-   SRS v2 - Set-SRSComputerName Package
-   SRS v2 - Package d’application SRS
-   SRS v2 - Configurer la configuration SRS
-   SRS v2 - Sysprep Package
-   Pilotes
    -   Surface Pro
    -   Surface Pro 4
-   Systèmes d’exploitation
    -   Windows 10 Entreprise

> [!TIP]
> Vous pouvez [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) également télécharger et utiliser le fichier zip qui inclut la structure des dossiers pour les packages, les scripts que vous devez utiliser et le modèle de séquence des tâches, que vous devez importer.

### <a name="create-the-monitoring-agent-package"></a>Créer le package de l’agent de surveillance

1. Téléchargez l’Agent de surveillance à partir <https://go.microsoft.com/fwlink/?LinkId=828603> de .

2. Extrayez le package dans le **dossier SRS v2 - Microsoft Monitoring Agent Package** en ouvrant une fenêtre d’invite de commandes et enMMASetup-AMD64.exe **/C:** à l’invite de commandes.

3. Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**

4. Entrez les informations suivantes pour créer le package :

   - Nom<strong>: SRS v2 - Microsoft Monitoring Agent package</strong>

   - Fabricant<strong>: Microsoft Corporation</strong>

   - Version<strong>: 8.1.11081.0</strong> (entrez la version du fichier d’installation téléchargé)

   - Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **SRS v2 - Microsoft Monitoring Agent Package,** puis sélectionnez **Suivant.**

5. Sélectionnez **Ne pas créer un programme,** puis **Suivant.**

6. Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**

7. Sélectionnez **Fermer.**

### <a name="create-the-operating-system-updates-package"></a>Créer le package de mises à jour du système d’exploitation

1. Dans le **dossier SRS v2 - Mises** à jour du package du système d’exploitation, créez un script PowerShell nommé **Install-SRSv2-OS-Updates.ps1.**

2. Copiez le script ci-dessous **dansInstall-SRSv2-OS-Updates.ps1** script. Vous pouvez également télécharger le script Install-SRSv2-OS-Updates.ps1 [ici.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. Téléchargez l’application Windows mettre à jour les packages dans le même dossier.
   > [!NOTE]
   > Lors de la publication de cet article, seule la mise à niveau [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) était requise. Consultez [Configurer une console Salles Microsoft Teams pour](console.md)voir si d’autres mises à jour sont requises.

4. Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**

5. Entrez les informations suivantes pour créer le package :
   -   Nom : **SRS v2 – Package de mises à jour du système d’exploitation**
   -   Fabricant : **Microsoft Corporation**
   -   Version : **1.0.0**
   -   Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **SRS v2 - Mises** à jour du système d’exploitation, puis sélectionnez **Suivant.**

6. Sélectionnez **Ne pas créer un programme,** puis **Suivant.**

7. Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**

8. Sélectionnez **Fermer.**

### <a name="create-the-root-certificate-package-optional"></a>Créer le package de certificat racine (facultatif)

Vous créez ce package pour distribuer le certificat racine pour les appareils qui ne sont pas joints à un domaine Active Directory. Créez ce package uniquement si les deux conditions suivantes s’appliquent :
-   Votre déploiement inclut Lync ou Skype Entreprise Server.
-   Salles Microsoft Teams unités sont configurées pour fonctionner dans un groupe de travail plutôt que dans un membre de domaine.

1.  Copiez le certificat racine dans le **dossier SRS v2 – Package de certificat** racine.

2.  Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**

3.  Entrez les informations suivantes pour créer le package :
    -   Nom : **SRS v2 – Package de certificat racine**
    -   Fabricant : *nom de votre organisation*
    -   Version : **1.0.0**
    -   Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **SRS v2 – Package** de certificat racine, puis sélectionnez **Suivant.**

4.  Sélectionnez **Ne pas créer un programme,** puis **Suivant.**

5.  Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**

6.  Sélectionnez **Fermer.**

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Créer le package Salles Microsoft Teams kit de déploiement d’équipe

1.  Téléchargez la dernière version du kit de déploiement **Salles Microsoft Teams et** <https://go.microsoft.com/fwlink/?linkid=851168> installez-la sur une station de travail.

2.  Copiez le contenu de **C : Program Files \\ (x86) \\ Skype Room System Deployment Kit** vers le dossier Package d’application **SRS v2 - SRS.**

3.  Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**

4.  Entrez les informations suivantes pour créer le package :
    -   Nom : **SRS v2 – Package d’application SRS**
    -   Fabricant : **Microsoft Corporation**
    -   Version : **3.1.104.0** (entrez la version du fichier d’installation téléchargé)
    -   Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier Package d’application **SRS v2 – SRS,** puis sélectionnez **Suivant.**
5.  Sélectionnez **Ne pas créer un programme,** puis **Suivant.**

6.  Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**

7.  Sélectionnez **Fermer.**

### <a name="create-the-computer-name-assignment-package"></a>Créer le package d’affectation du nom de l’ordinateur

1.  Dans le **dossier SRS v2 - Set-SRSComputerName Package,** créez une application HTML nommée **Set-SRSComputerName.hta.**

2.  Copiez le script suivant dans le fichier **Set-SRSComputerName.hta.** Vous pouvez également télécharger le fichier Set-SRSComputerName.hta à partir [d’ici.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**

4.  Entrez les informations suivantes pour créer le package :

    -   Nom : **SRS v2 - Set-SRSComputerName package**

    -   Fabricant : **Microsoft Corporation**

    -   Version : **1.0.0**

    -   Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **SRS v2 - Set-SRSComputerName Package,** puis sélectionnez **Suivant.**

5.  Sélectionnez **Ne pas créer un programme,** puis **Suivant.**

6.  Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**

7.  Sélectionnez **Fermer.**

### <a name="create-the-sysprep-package"></a>Créer le package Sysprep

1. Dans le **dossier SRS v2 – Package Sysprep,** créez un fichier XML nommé **Unattend.xml.**

2. Copiez le texte suivant dans le **Unattend.xml** fichier. Vous pouvez également télécharger le fichier Unattend.xml [ici.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**

4. Entrez les informations suivantes pour créer le package :
   -   Nom : **SRS v2 - Package Sysprep**
   -   Fabricant : **Microsoft Corporation**
   -   Version : **1.0.0**
   -   Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au dossier **Package SRS v2 – Sysprep,** puis sélectionnez **Suivant.**
5. Sélectionnez **Ne pas créer un programme,** puis **Suivant.**

6. Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**

7. Sélectionnez **Fermer.**

### <a name="create-the-windows-10-enterprise-package"></a>Créer le package Windows 10 Entreprise package

1.  Obtenez un Windows 10 Entreprise multimédia x64, puis copiez le fichier **install.wim** dans le dossier Windows 10 Entreprise systèmes **\\ d’exploitation.**

2.  Dans la console Configuration Manager, sélectionnez **Images** du système d’exploitation de la bibliothèque de logiciels, puis \>  \>  **sélectionnez Ajouter une image du système d’exploitation.**

3.  Spécifiez le chemin **d’accès au fichier install.wim** que vous avez copié, puis sélectionnez **Suivant.**

4.  Mettez à **jour le** champ Version pour qu’il corresponde au numéro de build Windows 10 Entreprise’image, puis sélectionnez **Suivant.**

5.  Examinez la page **Détails,** puis sélectionnez **Suivant.**

6.  Sélectionnez **Fermer.**

Pour plus d’informations, voir [Gérer les images du système d’exploitation avec Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Créer Surface Pro packages de pilote de périphérique

Salles Microsoft Teams est pris en charge pour les Surface Pro et Surface Pro 4. Vous devez créer un package de pilote pour chaque Surface Pro modèle que vous avez dans votre environnement.

> [!IMPORTANT]
> Les pilotes doivent être compatibles avec la version Windows 10 Entreprise et la version Salles Microsoft Teams du kit de déploiement. Pour plus d’informations, [consultez Télécharger le dernier microprogramme](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) et pilotes pour les appareils Surface et [Configurer une console.](console.md)

1.  Téléchargez les pilotes et microprogrammes les plus récents.
    -   Pour Surface Pro :<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Pour Surface Pro 4 :<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extraire le pilote et le microprogramme téléchargés. Ouvrez une fenêtre d’invite de commandes, puis à l’invite de commandes, entrez l’une des commandes suivantes :
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  Dans la console Configuration Manager, sélectionnez **Pilotes** de systèmes d’exploitation de la bibliothèque de \>  \> **logiciels,** puis **sélectionnez Importer un pilote.**

4.  Sélectionnez Importer tous les pilotes dans le chemin d’accès réseau **suivant (UNC),** sélectionnez le dossier source (par exemple, C : _Sources pilotes Surface Pro), puis \\ \\ \\ **Suivant.**

5.  Dans la page Spécifier les détails pour les pilotes **importés,** sélectionnez tous les pilotes répertoriés, puis sélectionnez Activer ces pilotes et autoriser les ordinateurs à **les installer.**

6.  Sélectionnez **Catégories,** créez une catégorie qui correspond au modèle Surface, **sélectionnez OK,** puis **Suivant.**

7.  Sélectionnez **Nouveau package.**

8.  Spécifiez le nom du package qui correspond au modèle Surface Pro, entrez un chemin d’accès de dossier pour stocker les fichiers de package de pilote dans, sélectionnez **OK,** puis **Suivant.**

9.  Sur la page **des images de** démarrage, assurez-vous qu’aucune image de démarrage n’est sélectionnée, puis sélectionnez **Suivant.**

10. Sélectionnez **Fermer.**

11. Sélectionnez  Pilotes des systèmes d’exploitation de bibliothèque de \>  \> **logiciels,** **\>** créez un dossier, puis entrez un nom de dossier qui correspond au modèle Surface Pro que vous viennent d’importer les pilotes.

12. Déplacez tous les pilotes importés vers le dossier nouvellement créé pour faciliter la navigation et le fonctionnement.

> [!NOTE]
> Répétez les mêmes étapes pour d Surface Pro autres modèles que vous pourriez avoir. Pour plus d’informations, [voir Gérer les pilotes dans Configuration Manager.](/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Créer Salles Microsoft Teams package de configuration

1.  Dans la console Configuration Manager, sélectionnez **Packages** de gestion d’application de bibliothèque de \>  \> **logiciels,** puis **sélectionnez Créer un package.**

2.  Entrez les informations suivantes pour créer le package :

    -   Nom : **SRS v2 - Configurer le package d’installation SRS**

    -   Fabricant : **Microsoft Corporation**

    -   Version : **1.0.0**

    -   Cochez la case Ce package contient les fichiers **sources,** entrez le chemin d’accès au **fichier SRS v2 - Configurer** le dossier d’installation SRS, puis sélectionnez **Suivant.**

3.  Sélectionnez **Ne pas créer un programme,** puis **Suivant.**

4.  Examinez la page **Confirmer les paramètres,** puis sélectionnez **Suivant.**

5.  Sélectionnez **Fermer.**



## <a name="distribute-configuration-manager-packages"></a>Distribuer des packages Configuration Manager

Tous les packages doivent être distribués aux serveurs qui ont reçu le rôle de point de distribution dans la hiérarchie de Configuration Manager. Suivez les instructions ci-dessous pour initier la distribution du package.

1.  Distribuer des packages logiciels.

    1.  Dans la console Configuration Manager, sélectionnez **Packages de** gestion d’application \>  \> **de bibliothèque de logiciels.** Sélectionnez tous les packages logiciels que vous voulez distribuer, puis **Distribuer le contenu.**

    2.  Examinez la liste des packages, puis sélectionnez **Suivant.**

    3.  Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, selon votre hiérarchie Configuration Manager) à la liste, puis sélectionnez **Suivant.**

    4.  **Sélectionnez** Suivant, puis **Fermer.**

2.  Distribuez des packages de pilotes.

    1.  Dans la console Configuration Manager, sélectionnez **Packages** de pilote de la bibliothèque \>  \> **de logiciels.** Sélectionnez tous les packages de pilotes que vous souhaitez distribuer, puis **distribuer le contenu.**

    2.  Examinez la liste des packages, puis sélectionnez **Suivant.**

    3.  Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, selon votre hiérarchie Configuration Manager) à la liste, puis sélectionnez **Suivant.**

    4.  **Sélectionnez** Suivant, puis **Fermer.**

3.  Distribuer des packages de système d’exploitation.

    1.  Dans la console Configuration Manager, sélectionnez **Images** du système d’exploitation de la bibliothèque \>  \> **de logiciels.** Sélectionnez toutes les images du système d’exploitation à distribuer, puis **distribuer le contenu.**

    2.  Examinez la liste des packages, puis sélectionnez **Suivant.**

    3.  Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, selon votre hiérarchie Configuration Manager) à la liste, puis sélectionnez **Suivant.**

    4.  **Sélectionnez** Suivant, puis **Fermer.**

> [!NOTE]
> La distribution de package peut prendre du temps, selon la taille du package, la hiérarchie configuration manager, le nombre de serveurs de points de distribution et la bande passante disponible dans votre réseau.
> 
> Tous les packages doivent être distribués avant de pouvoir commencer à déployer Salles Microsoft Teams unités.
> 
> Vous pouvez passer en revue l’état de votre distribution de package dans la console Configuration Manager en allant à **Surveillance** de l’état du contenu de \>  \> **l’état de distribution.**

## <a name="configuration-manager-task-sequences"></a>Séquences de tâches dans Configuration Manager

Vous utilisez des séquences de tâches avec Configuration Manager pour automatiser les étapes de déploiement d’une image de système d’exploitation sur un ordinateur de destination. Pour déployer une unité de Salles Microsoft Teams de manière automatisée, vous créez une séquence des tâches qui fait référence à l’image de démarrage utilisée pour démarrer l’ordinateur de Salles Microsoft Teams de destination, l’image du système d’exploitation Windows 10 Entreprise à installer, ainsi que tout autre contenu supplémentaire, tel que d’autres mises à jour d’applications ou de logiciels.

### <a name="import-the-sample-task-sequence"></a>Importer l’exemple de séquence de tâches

Vous pouvez télécharger et importer facilement un exemple de séquence de tâches et la personnaliser selon vos besoins.

1.  [**Téléchargez**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) l’exemple de séquence de tâches et copiez le fichier zip téléchargé dans un emplacement partagé.
2.  Dans la console Configuration Manager, **sélectionnez** Séquences de tâches de la bibliothèque de logiciels de systèmes d’exploitation, puis \>  \>  **sélectionnez Importer la séquence des tâches.**

3.  **Sélectionnez** Parcourir, accédez à l’emplacement du dossier partagé que vous avez utilisé à l’étape 1, sélectionnez le fichier Salles Microsoft Teams Déploiement d'.zip, puis  **Suivant.**

4.  Définissez **l’action** **Créer nouveau,** puis sélectionnez **Suivant.**

5.  Confirmez les paramètres, puis sélectionnez **Suivant.**

6.  Sélectionnez **Fermer.**

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Vérifier que les packages de référence sont correctement liés à chaque étape de séquence de tâches.

1. Sélectionnez la séquence de tâches importée, puis sélectionnez **Modifier.**

    L’Éditeur de séquence des tâches s’ouvre et affiche chaque étape séquentielle dont vous avez besoin pour déployer et configurer Salles Microsoft Teams unité de travail.

2. Parcourir chaque étape et mettre à jour les mises à jour recommandées :

   1. **Redémarrez dans Windows pe**: cette étape redémarre, puis démarre l’ordinateur dans Windows PXE. Aucune modification n’est requise pour cette étape.

   2. **Partition Disk 0 – UEFI**: Cette étape efface la configuration du disque et crée des partitions sur la base des paramètres configurés. Nous vous recommandons de ne pas apporter de modifications à cette étape.

   3. Définir le nom de l’ordinateur **SRS**: cette étape inclut une application HTML qui fournit une interface utilisateur qui permet de définir un nom d’ordinateur pour l Salles Microsoft Teams de données pendant le déploiement.
      -  Cette étape est facultative, mais elle ne peut être désactivée que si vous voulez gérer l’attribution de noms d’ordinateurs via un autre processus.
      -  Vérifiez que le package **SRS v2 - Set-SRSComputerName** est sélectionné. Si ce n’est pas le cas, recherchez le package et sélectionnez-le.

   4. **Appliquer le système d’exploitation**: cette étape spécifie l’image du système d’exploitation à déployer et le fichier de réponse Sysprep sans surveillance à utiliser.
      -  Vérifiez que le fichier image Windows 10 Entreprise système d’exploitation correct est sélectionné.
      -  Vérifiez que l’utilisation d’un fichier de réponse sans surveillance ou **Sysprep** pour une installation personnalisée est activée et que le **package SRS v2 - Sysprep** est sélectionné. Assurez-vous également **que le nom du** fichier estunattend.xml. ****

   5. **Appliquer Windows Paramètres**: cette étape collecte des informations sur l’installation Windows’installation.
      -  Fournissez des informations sur les licences et l’enregistrement, notamment la clé de produit, le mot de passe du compte d’administrateur local et le fuseau horaire (selon vos besoins).

   6. **Appliquer des Paramètres** réseau : cette étape vous permet de spécifier un nom de domaine de groupe de travail ou Active Directory et une unité organisationnelle.
      > [!NOTE]
      > Consultez Skype domaine Room System joignant les considérations pour les actions [recommandées](domain-joining-considerations.md) que vous devez prendre dans le déploiement d’unités de Salles Microsoft Teams en tant que membres d’un domaine d’annuaire Actve.
   7. **Appliquer des pilotes :** Cette étape et ses sous-étapes sont utilisées pour déployer les pilotes d’appareils applicables et le microprogramme en fonction Surface Pro modèle que vous avez. Mettez à jour chaque étape pour spécifier le package pilote approprié associé à ce déploiement.
      -   Chaque package de pilote est configuré pour tirer parti des filtres Windows Management (WMI) pour déployer des pilotes et microprogrammes pertinents en fonction des Surface Pro et du modèle.
      -   Il est vivement recommandé de ne pas modifier la configuration de ces pilotes, sans quoi le déploiement pourrait échouer.

   8. **Configurez Windows configuration manager :** cette étape déploie et configure le client Configuration Manager. Mettez à jour cette étape pour spécifier le package client intégré à Configuration Manager.

   9. **Installer le certificat racine**: cette étape distribue le certificat racine pour les appareils qui ne sont pas joints au domaine; par conséquent, il est facultatif et désactivé par défaut.
      -   Activez cette étape si vous avez besoin de déployer un certificat racine vers Salles Microsoft Teams unités de base.
      -   Si vous devez effectuer cette étape, vérifiez que le **package SRS v2 - Root Certificate Package** et désactiver la redirection du système de fichiers **64 bits** sont sélectionnés.

   10. Installer et **configurer l’Agent** de surveillance : cette étape installe la version 64 bits de l’agent de surveillance Microsoft Azure et configure l’agent pour qu’il se connecte à votre espace de travail Analyse journal.
       -   Cette étape est désactivée par défaut. Activez cette étape uniquement si vous comptez utiliser l’Agent de surveillance pour surveiller l’état de vos unités Salles Microsoft Teams surveillance.
       -   Modifiez cette étape et mettez à jour les paramètres de ligne de commande pour spécifier votre **ID** et votre touche **Espace de travail.**
       -   Pour [plus d’informations](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) sur l’obtention de l’ID d’espace de travail de la suite Operations Management Suite et de la clé primaire, voir Configurer les périphériques de test pour Azure Monitoring.
       -   Vérifiez que la **redirection SRS v2 – Microsoft Monitoring Agent package 64** bits et désactivez la redirection du système de fichiers **64 bits** est sélectionnée.
       -   Pour plus d’informations sur la surveillance de l’état de votre déploiement Salles Microsoft Teams, voir Planifier la gestion des Salles Microsoft Teams avec Azure Monitor, Déployer la gestion de l’Salles Microsoft Teams avec [Azure Monitor](azure-monitor-deploy.md) et Gérer les appareils Salles Microsoft Teams avec [Azure](azure-monitor-manage.md) [Monitor.](azure-monitor-plan.md)

   11. Copier les fichiers de configuration **SRS v2**: cette étape copie les fichiers de configuration et de configuration requis à partir du kit de déploiement Salles Microsoft Teams vers le disque dur local. Aucune personnalisation n’est requise pour cette étape.
       -   Vérifiez que le **package d’application SRS v2 – SRS** et la désactivation de la redirection du système de fichiers **64 bits** sont sélectionnés.

   12. **Mises à jour install-SRSv2-OS-Updates**: cette étape déploie toutes les mises à jour obligatoires du système d’exploitation requises dans le Salles Microsoft Teams déploiement. Procédez comme suit :
       -   Vérifiez [configurer une console Salles Microsoft Teams pour](console.md) voir quelles mises à jour sont requises.
       -   Vérifiez que votre package **SRS v2 – Mises à** jour du système d’exploitation inclut toutes les mises à jour requises.
       -   Vérifiez que le **package SRS v2 – Mises à** jour du système d’exploitation est sélectionné.
       -   Vérifiez que la stratégie d’exécution de PowerShell est définie sur **Contourner.**

   13. **Redémarrer l’ordinateur**: Cette étape redémarre l’ordinateur une fois que les mises à jour obligatoires du système d’exploitation sont installées. Aucune personnalisation n’est requise pour cette étape.

   14. **Configurer Windows composants principaux**: cette étape configure les fonctionnalités requises Windows’équipe. Aucune personnalisation n’est requise pour cette étape.

   15. **Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur une fois Windows fonctionnalités configurées. Aucune personnalisation n’est requise pour cette étape.

   16. **Ajouter un utilisateur Skype** local : cette étape crée le compte Skype local utilisé pour se Windows et démarrer l’application Salles Microsoft Teams local. Aucun package logiciel n’est associé à cette étape et aucune personnalisation n’est requise pour cette étape.

   17. **Configurer et configurer l’application SRS**: cette étape configure l’installation Salles Microsoft Teams’application pour le prochain démarrage du système d’exploitation.
       -   Vérifiez que la configuration du package d’installation **SRS v2** et la désactivation de la redirection du système de fichiers **64 bits** sont sélectionnées.

> [!IMPORTANT]
> Il est très important que les étapes de la séquence des tâches soient dans l’ordre fourni. La modification de l’ordre des étapes ou la configuration d’étapes supplémentaires peuvent rompre le déploiement.
>
> **La configuration et la configuration de l’étape de l’application SRS** doivent être la dernière étape de la séquence des tâches, faute de quoi le déploiement peut échouer.

### <a name="create-deployment-for-the-task-sequence"></a>Créer un déploiement pour la séquence des tâches

1. Sélectionnez la séquence des tâches, puis **Sélectionnez Déployer.**

2. Sélectionnez **Parcourir** pour sélectionner la collection cible pour le déploiement.

3. Sélectionnez **Tous les ordinateurs inconnus,** puis **OK.**

4. Sélectionnez **Suivant.**

5. **Sélectionnez** Disponible dans la **liste** de liste bas Objectif.

6. Sélectionnez **Média et PXE uniquement** dans la liste Rendre **disponible,** puis **Suivant.**
   > [!WARNING]
   > Il est très important que **l’objectif** soit réglé sur **Disponible.** Assurez-vous que **l’objectif** **n’est PAS** définie sur **Obligatoire.** Veillez également à sélectionner Uniquement le média **et PXE** dans **la liste Rendre disponible pour les informations suivantes.**
   >
   > La définition de ces valeurs sur une autre valeur peut entraîner l’installation de l’image Salles Microsoft Teams de déploiement de tous les ordinateurs au démarrage.
7. Ne spécifiez aucun échéancier et sélectionnez **Suivant.**

8. Ne modifiez rien dans la section Expérience utilisateur **et** sélectionnez **Suivant.**

9. Ne modifiez rien dans la section **Alertes** et sélectionnez **Suivant.**

10. Ne modifiez rien dans la section **Points de distribution et** sélectionnez **Suivant.**

11. Confirmez les paramètres, puis sélectionnez **Suivant.**

12. Sélectionnez **Fermer.**

**Valider et résoudre les problèmes de la solution**

Une fois que vous avez terminé les séquences de tâches Microsoft Endpoint Configuration Manager, vous devez effectuer une exécuter un test pour vérifier que la séquence des tâches peut être déployée et configurer Salles Microsoft Teams unités.

1.  Connecter d’utiliser le périphérique de test sur le réseau câblé à l’aide de l’un des adaptateurs Ethernet pris en charge ou de la station d’accueil Surface. Si la fonctionnalité de démarrage PXE n’a pas été configurée pour votre [](/configmgr/osd/deploy-use/create-bootable-media) environnement, vous pouvez utiliser l’image de démarrage sur le lecteur flash USB que vous avez créé précédemment pour démarrer à partir de l’USB et vous connecter à Configuration Manager.

2.  Accédez au microprogramme et démarrez le démarrage PXE :

    1.  Assurez-vous que l’appareil Surface est éteint.

    2.  Appuyez de long sur le **bouton Monter le** volume.

    3.  Appuyez sur le bouton **d’alimentation et relâchez-le.**

    4.  Lorsque le démarrage de l’appareil commence, relâchez le **bouton Monter le** volume.

    5.  Sélectionnez **Configuration du démarrage.**

    6.  Effectuez l’une des opérations suivantes :

        -   Sélectionnez **le démarrage PXE,** puis faites-le glisser vers le haut de la liste. Vous pouvez également balayer vers la gauche sur l’adaptateur réseau pour démarrer sur l’appareil immédiatement. Cela n’affecte pas l’ordre de démarrage.
        -   Sélectionnez le lecteur flash USB qui contient le support de démarrage.

3.  Sélectionnez **Quitter,** puis **Redémarrer maintenant.**

4.  À l’invite, **sélectionnez Entrée pour** le service de démarrage réseau.

5.  Windows Pe se charge en mémoire et l’Assistant Séquence des tâches démarre. Sélectionnez **Suivant** pour continuer.

6.  Sélectionnez la séquence des tâches que vous avez importée précédemment, puis **Suivant.**

7.  Une fois la configuration du disque appliquée, vous êtes invité à spécifier un nom d’ordinateur pour l’appareil. L’interface utilisateur affiche un nom d’ordinateur recommandé en fonction du numéro de série du Surface Pro appareil. Vous pouvez accepter le nom proposé ou en spécifier un nouveau. Suivez les instructions dans l’écran d’affectation du nom de l’ordinateur. Lorsque vous **sélectionnez Accepter,** le déploiement commence.

8.  Le reste du processus de déploiement est automatique et ne demande pas plus d’intervention des utilisateurs.

9.  Une fois que la séquence des tâches de déploiement aura terminé de configurer l’appareil, l’écran de configuration suivant s’affiche pour vous demander de configurer les Salles Microsoft Teams d’application.

    ![Écran de configuration initial pour Salles Microsoft Teams application.](../media/room-systems-scale-image2.png)

10.  Branchez le Surface Pro à la console Salles Microsoft Teams et configurez les paramètres de l’application.

11.  Validez que les fonctionnalités répertoriées dans [Salles Microsoft Teams’aide](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionnent sur l’appareil déployé.


Pour résoudre un échec d’installation, consultez le fichier **SMSTS.log,** qui enregistre toutes les étapes exécutées dans une séquence de tâches du Gestionnaire de configuration.

Le fichier SMSTS.log est stocké sur l’un des chemins d’accès suivant l’étape du processus de création. Consultez le tableau suivant pour identifier le chemin d’accès au fichier SMSTS.log.


| **Phase de déploiement**                                                            | **Chemin d’accès du journal de séquence de tâches**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, avant format HDD                                                        | X : \\ Windows \\ \\ Smstslog \\ smsts.log             |
| WinPE, après le format HDD                                                         | C : \\ _SMSTaskSequence \\ \\ Smstslog \\ smsts.log    |
| Système d’exploitation déployé avant l’installation de l’agent Configuration Manager | c : \\ _SMSTaskSequence \\ \\ Smstslog \\ smsts.log    |
| Système d’exploitation et agent Configuration Manager déployés                   | %windir% \\ System32 \\ ccm \\ logs \\ SMStslog \\ smsts.log |
| Exécution de séquence de tâches terminée                                                | %windir% \\ System32 \\ ccm \\ logs \\ smsts.log           |

> [!TIP]
> Vous pouvez sélectionner **F8 à** tout moment pendant la séquence des tâches pour ouvrir une console de commande, puis accéder au fichier SMSTS.log.

Pour résoudre les problèmes de démarrage PXE, vérifiez les deux fichiers journaux sur le serveur Configuration Manager qui sont spécifiques aux actions PXE :

-   **Pxecontrol.log,** situé dans le répertoire des journaux d’installation de Configuration Manager

-   **Smspxe.log,** situé dans le répertoire des journaux du point de gestion configuration manager (MP)

Pour obtenir la liste complète des fichiers journaux que vous pouvez utiliser pour résoudre les problèmes d’installation de Configuration Manager, consultez la Microsoft Endpoint Configuration Manager [référence du fichier journal.](/configmgr/core/plan-design/hierarchy/log-files)
