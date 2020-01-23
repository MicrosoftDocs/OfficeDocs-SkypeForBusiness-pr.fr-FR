---
title: Déploiement de salles de Microsoft teams à l’aide de System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Consultez cette rubrique pour en savoir plus sur le déploiement de salles de Microsoft teams à des déploiements à grande échelle.
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
ms.openlocfilehash: fe6ea140f15c5234117aabe6612e0190e47ddc4d
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268933"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a>Déploiement de salles de Microsoft teams à l’aide de System Center Configuration Manager

Cet article vous fournit toutes les informations nécessaires pour créer les déploiements de Microsoft Teams.

À l’aide des méthodes simples d’utilisation fournies par System Center Configuration Manager, vous pouvez déployer le système d’exploitation et d’autres applications sur plusieurs appareils cibles.

Utilisez l’approche illustrée ci-dessous pour vous guider dans votre configuration du gestionnaire de configuration et personnaliser les packages et les scripts fournis dans ces conseils selon les besoins de votre organisation.

![Processus de déploiement de Microsoft teams à l’aide de Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Cette solution n’a été testée qu’avec des déploiements en surface Pro. Suivez les instructions du fabricant pour les configurations qui ne sont pas basées sur surface Pro.

## <a name="validate-prerequisites"></a>Valider les conditions préalables

Pour déployer des salles Microsoft teams avec Configuration Manager, vérifiez que vous remplissez les conditions préalables et requises suivantes.

### <a name="system-center-configuration-manager-requirements"></a>Configuration requise pour System Center Configuration Manager

-   La version de System Center Configuration Manager doit être au minimum 1706 ou une version ultérieure. Nous vous recommandons d’utiliser 1710 ou une version ultérieure. Pour en savoir plus sur les versions de Windows 10 prises en charge par Configuration Manager, voir [prise en charge de Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) .

-   Une version prise en charge de kit de déploiement et d’évaluation Windows (ADK) pour Windows 10 doit être installée. Découvrez les versions de [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que vous pouvez utiliser avec différentes versions de Configuration Manager et assurez-vous que votre déploiement inclut la version correcte.

-   Les serveurs de systèmes de site doivent avoir reçu le rôle de point de distribution et les images de démarrage doivent être activées pour la [prise en charge de l’environnement d’exécution prédémarrage (PXE)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) pour permettre les déploiements initiés par le réseau. Si la prise en charge de PXE n’est pas activée, vous pouvez utiliser un [média amorçable](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements.

-   Un compte d’accès réseau doit être configuré pour prendre en charge les scénarios de déploiement de nouveaux ordinateurs (de matériel vierge). Pour en savoir plus sur la configuration d’un compte d’accès réseau, voir [gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Nous vous recommandons d’activer la [prise en charge de la multidiffusion](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si vous déployez en même temps la même image dans plusieurs salles de Microsoft Teams.

### <a name="networking-requirements"></a>Configuration réseau requise

-   Votre réseau doit être doté d’un serveur de protocole de configuration de l’hôte dynamique, configuré pour la distribution automatique de l’adresse IP sur les sous-réseaux dans lesquels les unités de salles de Microsoft teams sont déployées.

    > [!NOTE]
    > La durée du bail DHCP doit être définie sur une valeur supérieure à la durée du déploiement d’image. Dans le cas contraire, le déploiement risque d’échouer.

-   Votre réseau, notamment les commutateurs et les réseaux locaux virtuels (VLAN), doit être configuré pour prendre en charge PXE. Pour plus d’informations sur l’assistance IP et la configuration PXE, reportez-vous à la rubrique fournisseur de votre réseau. Par ailleurs, vous pouvez utiliser un [média amorçable](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements si la prise en charge de PXE n’est pas activée.

    > [!NOTE]
    > Pour les appareils surface Pro, le démarrage à partir du réseau (démarrage PXE) est uniquement pris en charge lorsque vous utilisez une carte Ethernet ou une station d’accueil de Microsoft. Les cartes Ethernet tierces ne prennent pas en charge le démarrage PXE avec surface Pro. Pour plus d’informations, reportez-vous à la rubrique [cartes Ethernet et déploiement de surface](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>Configurer System Center Configuration Manager pour le déploiement du système d’exploitation

Cet article part du principe que vous disposez déjà d’un déploiement de System Center Configuration Manager correct et que vous n’avez pas d’informations détaillées sur les étapes nécessaires au déploiement et à la configuration de Configuration Manager à partir de zéro. La [documentation et les instructions de configuration](https://docs.microsoft.com/sccm/) de System Center Configuration Manager constituent une formidable ressource. Nous vous recommandons de commencer avec ces ressources si vous n’avez pas encore déployé Configuration Manager.

Utilisez les instructions suivantes pour vérifier que les fonctionnalités de déploiement du système d’exploitation sont correctement configurées.

### <a name="validate-and-upgrade-configuration-manager"></a>Valider et mettre à niveau le gestionnaire de configuration

1.  Dans la console Configuration Manager, accédez à **** \> **mises à jour d’administration et service de maintenance**.

2.  Recherchez les mises à jour installées et applicables qui n’ont pas encore été installées.

3.  Consultez la [prise en charge de Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). Si vous devez mettre à niveau votre déploiement, sélectionnez la mise à jour que vous voulez installer, puis sélectionnez **Télécharger**.

4.  Une fois le téléchargement terminé, sélectionnez la mise à jour, puis cliquez sur **installer le Pack de mise à jour**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurer les points de distribution pour la prise en charge de PXE et de la multidiffusion

1.  Dans la console Configuration Manager, accédez à **** \> **points de distribution**d’administration.

2.  Sélectionnez le serveur de point de distribution qui servira le déploiement de Microsoft Teams, puis sélectionnez **Propriétés**.

3.  Sélectionnez l’onglet **PXE** et assurez-vous que les paramètres suivants sont activés :
    -   Activer la prise en charge PXE pour les clients
    -   Autoriser ce point de distribution à répondre aux demandes PXE entrantes
    -   Activer la prise en charge d’ordinateurs non connus

4.  *Facultatif :* Pour activer la prise en charge de la multidiffusion, sélectionnez l’onglet **multidiffusion** et assurez-vous que les paramètres suivants sont activés :
    -   Autoriser la multidiffusion à envoyer des données simultanément à plusieurs clients
    -   Configurer la plage de ports UDP conformément aux recommandations de votre équipe réseau

### <a name="configure-the-network-access-account"></a>Configurer le compte d’accès au réseau

1.  Dans la console Configuration Manager, accédez à **sites**d' **administration** \> de **configuration** \> de site, puis sélectionnez le site.

2.  Dans le groupe **paramètres** , sélectionnez **configurer les composants** \> de site **distribution de logiciels**.

3.  Sélectionnez l’onglet **compte d’accès au réseau** . Configurez un ou plusieurs comptes, puis sélectionnez **OK**.

> [!NOTE]
> Les comptes n’ont pas besoin de droits spéciaux, à l’exception de l' **accès à cet ordinateur à partir du réseau** , directement sur le serveur du point de distribution. Un compte d’utilisateur de domaine générique est approprié. Pour plus d’informations, voir [gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Configurer une image de démarrage

1.  Dans la console Configuration Manager, accédez à l' **image de démarrage**du **système** \> d’exploitation de la **bibliothèque** \> logiciel.

2.  Sélectionnez **image de démarrage (x64)**, puis sélectionnez **Propriétés**.

3.  Sélectionnez l’onglet **source de données** , puis activez l’option **déploiement de cette image de démarrage à partir du point de distribution PXE**.

4.  Sélectionnez l’onglet **composants facultatifs** pour installer les composants nécessaires :

    1.  Sélectionner l’icône d’étoile et rechercher du **code html (WinPE-HTA)**

    2.  Sélectionnez **OK** pour ajouter la prise en charge de l’application HTML dans l’image de démarrage.

5.  *Facultatif :* Pour personnaliser l’interface de déploiement, sélectionnez l’onglet de **personnalisation** .
    -   Activez le **support des commandes (tests uniquement)** si vous souhaitez accéder à une invite de commandes pendant le déploiement. Lorsque cette option est activée, vous pouvez démarrer une invite de commandes en sélectionnant **F8** à tout moment pendant le déploiement.
    -   Vous pouvez également spécifier une image d’arrière-plan personnalisée à afficher lors du déploiement. Pour définir une image, activez **l’option spécifier le fichier d’image d’arrière-plan personnalisé (chemin d’accès UNC** ), puis sélectionnez l’arrière-plan.

6.  Lorsque vous y êtes invité, sélectionnez **Oui** et distribuez l’image de démarrage mise à jour aux points de distribution.

Pour plus d’informations, voir [gérer les images de démarrage à l’aide de System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).

> [!NOTE]
> Vous pouvez créer un média USB amorçable pour lancer des déploiements de séquence de tâches de Configuration Manager pour les environnements n’ayant pas de prise en charge PXE. Le média amorçable contient uniquement l’image de démarrage, les commandes de prédémarrage facultatives et les fichiers requis, ainsi que les fichiers binaires de configuration pour la prise en charge du démarrage dans Windows PE et la connexion à Configuration Manager pour le reste du processus de déploiement. Pour plus d’informations, reportez-vous [à la rubrique Création d’un média amorçable](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Créer des packages de Configuration Manager

> [!IMPORTANT]
> La version de système d’exploitation requise pour chaque version du programme d’installation de SRS change avec chaque version MSI. Pour déterminer la meilleure version du système d’exploitation pour un fichier MSI donné, exécutez le script de configuration de la console une seule fois. Pour plus d’informations, reportez-vous à la rubrique [déploiement de salles Microsoft teams à l’aide de System Center Configuration Manager](rooms-scale.md).

Configuration Manager nécessite un certain nombre de packages pour déployer et configurer les unités de salles de Microsoft Teams.

Vous avez besoin de créer et de configurer les packages suivants, puis de les distribuer sur les systèmes de site de Configuration Manager ayant reçu le rôle serveur de point de distribution.

| **Nom du package**                     | **Type**               | **Description**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-package d’application SRS     | Package logiciel       | Package pour le kit de déploiement de Microsoft teams                                      |
| SRS v2-package Sysprep             | Package logiciel       | Package pour le fichier Unattended. XML de Microsoft teams            |
| SRS v2-Set-package SRSComputerName | Package logiciel       | Package pour l’application HTML (HTA) permettant d’affecter un nom d’ordinateur lors du déploiement    |
| SRS v2-configurer le programme de configuration de SRS         | Package logiciel       | Package permettant de configurer le déploiement de l’application Microsoft teams                          |
| Package de mise à jour de SRS v2-OS          | Package logiciel       | Package de déploiement des mises à jour de systèmes d’exploitation obligatoires                                      |
| SRS v2-package de certificats racines    | Package logiciel       | Package facultatif pour le déploiement du certificat racine (non requis pour les unités jointes au domaine)  |
| SRS v2-package de l’agent de surveillance Microsoft | Package logiciel       | Package facultatif pour le déploiement et la configuration de l’agent Microsoft Operations Management Suite|
| SRS v2-package d’arrière-plan WinPE    | Package logiciel       | Package de l’image d’arrière-plan personnalisée à utiliser avec les images de démarrage                           |
| Windows 10 entreprise                | Image de système d’exploitation | Package du fichier d’installation du système d’exploitation (Install. wim)                          |
| Surface Pro                          | Package de pilotes         | Package pour les pilotes de périphériques et le microprogramme pour Microsoft surface Pro                     |
| Surface Pro 4                        | Package de pilotes         | Package pour les pilotes de périphériques et le microprogramme pour Microsoft surface Pro 4                   |

Pour plus d’informations, voir [packages et programmes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Créer des dossiers pour les fichiers source du package

Configuration Manager exige que les fichiers sources du package soient organisés dans une structure de dossiers spécifique lors de leur création initiale et de leur mise à jour.

Créez la structure de dossiers suivante dans le site d’administration centrale de System Center Configuration Manager ou le site principal, ou sur un partage de serveur que vous utilisez pour héberger les fichiers sources du package :

-   SRS v2-package de l’agent de surveillance Microsoft
-   Package de mise à jour de SRS v2-OS
-   SRS v2-package de certificats racines
-   SRS v2-Set-package SRSComputerName
-   SRS v2-package d’application SRS
-   SRS v2-configurer le programme de configuration de SRS
-   SRS v2-package Sysprep
-   Pilote
    -   Surface Pro
    -   Surface Pro 4
-   Systèmes d’exploitation
    -   Windows 10 entreprise

> [!TIP]
> Vous pouvez également [Télécharger](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) et utiliser le fichier zip qui inclut la structure de dossiers des packages, les scripts que vous devez utiliser et le modèle de séquence de tâches que vous devez importer.

### <a name="create-the-monitoring-agent-package"></a>Créer un package d’agent de surveillance

1. Téléchargez l’agent de surveillance <https://go.microsoft.com/fwlink/?LinkId=828603>de.

2. Extrayez le package dans le dossier **SRS v2-Microsoft Analysis agent** en ouvrant une fenêtre d’invite de commandes et en entrant **MMASetup-amd64. exe/c :** à l’invite de commandes.

3. Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.

4. Entrez les informations suivantes pour créer le package :

   - Nom<strong>: SRS v2-package de l’agent de surveillance Microsoft</strong>

   - Fabricant<strong>: Microsoft Corporation</strong>

   - Version<strong>: 8.1.11081.0</strong> (entrez la version du fichier d’installation téléchargé)

   - Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2-Microsoft Monitoring agent** , puis sélectionnez **suivant**.

5. Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.

6. Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.

7. Sélectionnez **Fermer**.

### <a name="create-the-operating-system-updates-package"></a>Créer le package mises à jour du système d’exploitation

1. Dans le dossier de **package de mise à jour de SRS v2-OS** , créez un nouveau script PowerShell appelé **install-SRSv2-OS-Updates. ps1**.

2. Copiez le script ci-dessous dans le script **install-SRSv2-OS-Updates. ps1** . Vous pouvez également télécharger le script Install-SRSv2-OS-Updates. ps1 à partir de [cet emplacement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Téléchargez les packages de mise à jour Windows obligatoires dans le même dossier.
   > [!NOTE]
   > Au moment de la publication de cet article, seul [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) est requis. Cochez [la case configurer une console Microsoft teams](console.md)pour voir si d’autres mises à jour sont requises.

4. Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.

5. Entrez les informations suivantes pour créer le package :
   -   Nom : **SRS v2 – package mises à jour du système d’exploitation**
   -   Fabricant : **Microsoft Corporation**
   -   Version : **1.0.0**
   -   Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier des **mises à jour de SRS v2-OS** , puis sélectionnez **suivant**.

6. Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.

7. Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.

8. Sélectionnez **Fermer**.

### <a name="create-the-root-certificate-package-optional"></a>Créer le package de certificat racine (facultatif)

Vous créez ce package pour distribuer le certificat racine pour les appareils qui ne seront pas joints à un domaine Active Directory. Créez ce package uniquement si les deux conditions suivantes s’appliquent :
-   Votre déploiement inclut Lync local ou Skype entreprise Server.
-   Les unités de salles de Microsoft teams sont configurées pour fonctionner au sein d’un groupe de travail au lieu d’un membre du domaine.

1.  Copiez le certificat racine dans le dossier **SRS v2 – certificat racine** .

2.  Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.

3.  Entrez les informations suivantes pour créer le package :
    -   Nom : **SRS v2-package de certificat racine**
    -   Fabricant : *nom de votre organisation*
    -   Version : **1.0.0**
    -   Activez la case à cocher **ce package contient les fichiers sources** , entrez le chemin d’accès du dossier **SRS v2 – certificat racine du package** , puis sélectionnez **suivant**.

4.  Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.

5.  Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.

6.  Sélectionnez **Fermer**.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Créer le package du kit de déploiement de Microsoft teams

1.  Téléchargez la version la plus récente du **Kit de déploiement de Microsoft teams** <https://go.microsoft.com/fwlink/?linkid=851168>, puis installez-la sur une station de travail.

2.  Copiez le contenu de **C\\: Program Files (x86\\) Skype Room System Deployment Kit** vers le dossier **SRS v2-package d’application SRS** .

3.  Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.

4.  Entrez les informations suivantes pour créer le package :
    -   Nom : **SRS v2-package d’application SRS**
    -   Fabricant : **Microsoft Corporation**
    -   Version : **3.1.104.0** (entrez la version du fichier d’installation téléchargé)
    -   Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2 – package d’application SRS** , puis sélectionnez **suivant**.
5.  Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.

6.  Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.

7.  Sélectionnez **Fermer**.

### <a name="create-the-computer-name-assignment-package"></a>Créer le package d’attribution de nom d’ordinateur

1.  Dans le dossier **SRS v2-Set-SRSComputerName package** , créez une nouvelle application HTML nommée **Set-SRSComputerName. hta** .

2.  Copiez le script suivant dans le fichier **Set-SRSComputerName. hta** . Vous pouvez également télécharger le fichier Set-SRSComputerName. hta à partir de [cet emplacement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3.  Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.

4.  Entrez les informations suivantes pour créer le package :

    -   Nom : **SRS v2-Set-package SRSComputerName**

    -   Fabricant : **Microsoft Corporation**

    -   Version : **1.0.0**

    -   Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2-Set-SRSComputerName package** , puis sélectionnez **suivant**.

5.  Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.

6.  Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.

7.  Sélectionnez **Fermer**.

### <a name="create-the-sysprep-package"></a>Créer le package Sysprep

1. Dans le dossier **SRS v2 – package Sysprep** , créez un nouveau fichier XML intitulé **Unattend. xml** .

2. Copiez le texte suivant dans le fichier **Unattend. xml** . Vous pouvez également télécharger le fichier Unattend. XML à partir de [cet emplacement](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
3. Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.

4. Entrez les informations suivantes pour créer le package :
   -   Nom : **SRS v2-package Sysprep**
   -   Fabricant : **Microsoft Corporation**
   -   Version : **1.0.0**
   -   Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au dossier **SRS v2 – package Sysprep** , puis sélectionnez **suivant**.
5. Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.

6. Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.

7. Sélectionnez **Fermer**.

### <a name="create-the-windows-10-enterprise-package"></a>Créer le package Windows 10 entreprise

1.  Obtenez un média Windows 10 entreprise x64 et copiez le fichier **install. wim** dans le dossier **systèmes\\d’exploitation Windows 10 entreprise** .

2.  Dans la console Configuration Manager, accédez à l’image **systèmes** \> **d’exploitation des**systèmes d’exploitation de la **bibliothèque** \> de logiciels, puis sélectionnez **Ajouter une image de système d’exploitation**.

3.  Spécifiez le chemin d’accès du fichier d' **installation. wim** que vous venez de copier, puis sélectionnez **suivant**.

4.  Mettez à jour le champ **version** pour correspondre au numéro de build de l’image Windows 10 entreprise, puis sélectionnez **suivant**.

5.  Examinez la page des **Détails** , puis sélectionnez **suivant**.

6.  Sélectionnez **Fermer**.

Pour plus d’informations, voir [gérer les images du système d’exploitation à l’aide de System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Créer des packages de pilotes de périphériques de surface Pro

Les salles de Microsoft teams sont prises en charge pour surface Pro et surface Pro 4. Vous devez créer un package de pilotes pour chaque modèle surface Pro dans votre environnement.

> [!IMPORTANT]
> Les pilotes doivent être compatibles avec la version de Windows 10 entreprise et celle du kit de déploiement de Microsoft Teams. Pour plus d’informations, reportez-vous à [la rubrique Télécharger le microprogramme et pilotes les plus récents pour les appareils surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) et [configurer une console](console.md).

1.  Téléchargez les derniers pilotes et microprogrammes.
    -   Pour surface Pro :<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Pour surface Pro 4 :<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extrayez le pilote et le microprogramme téléchargés. Ouvrez une fenêtre d’invite de commandes, puis à l’invite de commandes, entrez l’une des commandes suivantes :
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Dans la console Configuration Manager, sélectionnez \> **pilotes**de **systèmes d’exploitation** de la **bibliothèque** \> de logiciels, puis **importer le pilote**.

4.  Sélectionnez **Importer tous les pilotes dans le chemin réseau suivant (UNC)**, sélectionnez le dossier source (par exemple, C\\:\\_Sources\\pilotes surface Pro), puis sélectionnez **suivant**.

5.  Dans la page **spécifier les détails pour les pilotes importés** , sélectionnez tous les pilotes répertoriés, puis sélectionnez **activer ces pilotes et autoriser les ordinateurs à les installer**.

6.  Sélectionnez **catégories**, créez une nouvelle catégorie qui correspond au modèle de surface, sélectionnez **OK**, puis sélectionnez **suivant**.

7.  Sélectionnez **nouveau package**.

8.  Spécifiez le nom du package qui correspond au modèle surface Pro, entrez le chemin d’accès du dossier dans lequel vous souhaitez stocker les fichiers du package de pilotes, sélectionnez **OK**, puis sélectionnez **suivant**.

9.  Dans la page **images de démarrage** , assurez-vous qu’aucune image de démarrage n’est sélectionnée, puis sélectionnez **suivant**.

10. Sélectionnez **Fermer**.

11. Accédez à **** \> **pilotes**de \> **systèmes d’exploitation** des bibliothèques de logiciels, sélectionnez ** \> créer un dossier**, puis entrez le nom du dossier qui correspond au modèle surface Pro pour lequel vous venez d’importer les pilotes.

12. Déplacez tous les pilotes importés dans le dossier nouvellement créé pour faciliter la navigation et l’utilisation.

> [!NOTE]
> Répétez ces étapes pour les autres modèles surface Pro que vous avez peut-être. Pour plus d’informations, voir [gérer les pilotes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Créer un package de configuration de Microsoft teams

1.  Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels, puis sélectionnez **créer un package**.

2.  Entrez les informations suivantes pour créer le package :

    -   Nom : **SRS v2-configurer le package d’installation de SRS**

    -   Fabricant : **Microsoft Corporation**

    -   Version : **1.0.0**

    -   Cochez la case **ce package contient les fichiers sources** , entrez le chemin d’accès au **service SRS v2-configurer le dossier d’installation de SRS** , puis sélectionnez **suivant**.

3.  Sélectionnez **ne pas créer de programme**, puis sélectionnez **suivant**.

4.  Examinez la page **confirmez les paramètres** , puis sélectionnez **suivant**.

5.  Sélectionnez **Fermer**.



## <a name="distribute-configuration-manager-packages"></a>Distribuer des packages de Configuration Manager

Tous les packages doivent être distribués aux serveurs auxquels le rôle de point de distribution a été attribué dans la hiérarchie du gestionnaire de configuration. Suivez les instructions ci-dessous pour lancer la distribution de package.

1.  Distribution des packages de logiciels.

    1.  Dans la console Configuration Manager, accédez à **packages**de **gestion** \> des applications de la **bibliothèque** \> de logiciels. Sélectionnez tous les packages de logiciels que vous souhaitez distribuer, puis sélectionnez **distribuer le contenu**.

    2.  Examinez la liste des packages, puis sélectionnez **suivant**.

    3.  Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie du gestionnaire de configuration) à la liste, puis sélectionnez **suivant**.

    4.  Sélectionnez **suivant**, puis sélectionnez **Fermer**.

2.  Distribuer des packages de pilotes ;

    1.  Dans la console Configuration Manager, accédez à **packages de pilotes**de **systèmes** \> d’exploitation des **bibliothèques** \> de logiciels. Sélectionnez tous les packages de pilotes que vous souhaitez distribuer, puis sélectionnez **distribuer le contenu**.

    2.  Examinez la liste des packages, puis sélectionnez **suivant**.

    3.  Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie du gestionnaire de configuration) à la liste, puis sélectionnez **suivant**.

    4.  Sélectionnez **suivant**, puis sélectionnez **Fermer**.

3.  Distribuer des packages de système d’exploitation.

    1.  Dans la console Configuration Manager, accédez à l' **image**des systèmes d’exploitation des \> **systèmes** \> d’exploitation de la **bibliothèque logicielle** . Sélectionnez toutes les images de système d’exploitation que vous souhaitez distribuer, puis sélectionnez **distribuer le contenu**.

    2.  Examinez la liste des packages, puis sélectionnez **suivant**.

    3.  Ajoutez tous les serveurs de points de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie du gestionnaire de configuration) à la liste, puis sélectionnez **suivant**.

    4.  Sélectionnez **suivant**, puis sélectionnez **Fermer**.

> [!NOTE]
> La distribution de package peut prendre un certain temps en fonction de la taille du package, de la hiérarchie de Configuration Manager, du nombre de serveurs de points de distribution et de la bande passante disponible dans votre réseau.
> 
> Pour pouvoir commencer le déploiement d’une unité de Microsoft Teams, tous les packages doivent être distribués.
> 
> Vous pouvez consulter l’état de la distribution de votre package dans la console Configuration Manager en accédant à **surveiller** \> l' **État du contenu**de l’état \> de **distribution** .

## <a name="configuration-manager-task-sequences"></a>Séquences de tâches de Configuration Manager

Vous utilisez les séquences de tâches avec System Center Configuration Manager pour automatiser les étapes de déploiement d’une image de système d’exploitation sur un ordinateur de destination. Pour déployer une unité de salle Microsoft teams de manière automatisée, vous devez créer une séquence de tâches qui fait référence à l’image de démarrage utilisée pour démarrer l’ordinateur de destination Microsoft Teams, l’image du système d’exploitation Windows 10 entreprise que vous voulez installer, et les autres autres contenus supplémentaires, tels que d’autres applications ou mises à jour logicielles.

### <a name="import-the-sample-task-sequence"></a>Importer la séquence de tâches d’exemple

Vous pouvez télécharger et importer facilement un exemple de séquence de tâches et le personnaliser en fonction de vos besoins.

1.  [**Téléchargez**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) l’exemple de séquence de tâches et copiez le fichier zip téléchargé dans un emplacement partagé.
2.  Dans la console Configuration Manager, sélectionnez \> **séquences de tâches**des **systèmes d’exploitation** de la **bibliothèque** \> de logiciels, puis importer la séquence de **tâches**.

3.  Sélectionnez **Parcourir**, accédez à l’emplacement du dossier partagé que vous avez utilisé à l’étape 1, sélectionnez le fichier de **déploiement de Microsoft Teams (en-US). zip** , puis sélectionnez **suivant**.

4.  Définissez **action** sur **créer**, puis sélectionnez **suivant**.

5.  Confirmez les paramètres, puis sélectionnez **suivant**.

6.  Sélectionnez **Fermer**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Vérifiez que les packages de référence sont correctement liés à chaque étape de séquence de tâches.

1. Sélectionnez la séquence de tâches importée, puis sélectionnez **modifier**.

    L’éditeur de séquence de tâches s’ouvre et affiche les étapes séquentielles requises pour le déploiement et la configuration d’une unité de salle Microsoft Teams.

2. Parcourez chacune des étapes et effectuez les mises à jour recommandées :

   1. **Redémarrer dans Windows PE**: cette étape redémarre puis initialise l’ordinateur dans Windows PXE. Aucune modification n’est requise pour cette étape.

   2. **Partition Disk 0 – UEFI**: cette étape efface la configuration du disque et crée des partitions en fonction des paramètres configurés. Nous vous recommandons de ne pas apporter de modifications à cette étape.

   3. **Définir le nom de l’ordinateur SRS**: cette étape inclut une application HTML pour fournir une interface utilisateur permettant de définir le nom d’un ordinateur pour l’unité de salle Microsoft teams lors du déploiement.
      -  Il s’agit d’une étape facultative, mais elle peut uniquement être désactivée si vous souhaitez gérer le nom de l’ordinateur via un autre processus.
      -  Vérifiez que le package **SRS v2-Set-SRSComputerName** est sélectionné. Si ce n’est pas le cas, recherchez le package et sélectionnez-le.

   4. **Appliquer le système d’exploitation**: cette étape spécifie l’image du système d’exploitation à déployer et le fichier de réponses Sysprep sans assistance à utiliser.
      -  Vérifiez que le fichier d’image du système d’exploitation Windows 10 entreprise approprié est sélectionné.
      -  Vérifiez que l’option **utiliser un fichier de réponses sans assistance ou Sysprep pour une installation personnalisée** est activée et que le **package SRS v2-Sysprep** est sélectionné. Assurez-vous également que le **nom de fichier** est défini sur **Unattend. xml**.

   5. **Appliquer les paramètres Windows**: cette étape collecte des informations sur l’installation de Windows.
      -  Fournir des informations sur les licences et l’inscription, notamment la clé de produit, le mot de passe du compte d’administrateur local et le fuseau horaire (selon vos besoins).

   6. **Appliquer les paramètres réseau**: cette étape vous permet de spécifier un groupe de travail ou un nom de domaine Active Directory et une unité d’organisation.
      > [!NOTE]
      > Pour plus d’informations sur les actions recommandées, consultez la rubrique accès au [domaine du système de salle Skype](domain-joining-considerations.md) pour le déploiement d’unités de réunion Microsoft teams en tant que membres d’un domaine Actve
   7. **Appliquer des axes stratégiques :** Cette étape et ses sous-étapes permettent le déploiement de pilotes de périphériques et de microprogrammes applicables en fonction du modèle de surface Pro que vous utilisez. Mettez à jour chaque étape pour spécifier le package de pilotes approprié associé au déploiement.
      -   Chaque package de pilotes est configuré de manière à tirer parti des filtres WMI (Windows Management Instrumentation) pour déployer les pilotes et le microprogramme appropriés en fonction de la marque et du modèle de surface Pro.
      -   Nous vous recommandons vivement de ne pas modifier la configuration de ces pilotes, sinon le déploiement risque d’échouer.

   8. **Configurer Windows et Configuration Manager**: cette étape déploie et configure le client Configuration Manager. Mettez à jour cette étape pour spécifier le package client intégré de Configuration Manager.

   9. **Installer le certificat racine**: cette étape distribue le certificat racine pour les appareils non joints au domaine et est par conséquent facultatif et désactivé par défaut.
      -   Activez cette étape si vous avez besoin de déployer un certificat racine vers les unités de salles de Microsoft Teams.
      -   Si vous n’avez pas besoin d’effectuer cette étape, vérifiez que le **package SRS (SRS)** 64 et la **redirection** de votre système de fichiers sont sélectionnés.

   10. **Installer et configurer l’agent de surveillance**: cette étape installe la version 64 bits de l’agent de suivi Microsoft Azure et configure l’agent pour la connexion à votre espace de travail d’analyse du journal.
       -   Cette étape est désactivée par défaut. Activez cette étape uniquement si vous envisagez d’utiliser l’agent de surveillance pour contrôler l’état de vos unités de salle Microsoft Teams.
       -   Modifiez cette étape et mettez à jour les paramètres de ligne de commande pour spécifier votre **ID d’espace de travail** et votre **espace de travail**.
       -   Pour plus d’informations sur l’obtention de l’ID d’espace de travail de la suite de gestion des opérations et de la clé primaire, voir [configurer des périphériques de test pour la surveillance Azure](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .
       -   Assurez-vous que le **service SRS v2 – Microsoft Analysis agent** et **désactivez la redirection de système de fichiers 64 bits** est sélectionné.
       -   Pour plus d’informations sur la surveillance de l’état du déploiement de Microsoft Teams, reportez-vous à la rubrique planification de la [gestion des salles de Microsoft teams avec](azure-monitor-plan.md)Azure Monitor, déploiement de la [gestion des salles de Microsoft teams avec Azure Monitor](azure-monitor-deploy.md) et [gestion des appareils Microsoft teams avec Azure Monitor](azure-monitor-manage.md).

   11. **Copier les fichiers de configuration de SRS v2**: cette étape copie les fichiers d’installation et de configuration requis du kit de déploiement de Microsoft teams sur le disque dur local. Aucune personnalisation n’est requise pour cette étape.
       -   Vérifiez que le **package d’application SRS pour le service SRS** et la **désactivation de la redirection de système de fichiers 64 bits** sont sélectionnés.

   12. **Installation-SRSv2-OS-mises à jour**: cette étape déploie toutes les mises à jour de système d’exploitation obligatoires requises avec le déploiement de Microsoft Teams. Procédez comme suit :
       -   Cochez [la case configurer une console de salle Microsoft teams](console.md) pour afficher les mises à jour nécessaires.
       -   Vérifiez que le **package de mise à jour de SRS v2 –** y compris toutes les mises à jour requises.
       -   Vérifiez que le **package SRS v2 – mises à jour du système d’exploitation** est sélectionné.
       -   Vérifiez que la stratégie d’exécution PowerShell est définie sur **Bypass**.

   13. **Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur après l’installation des mises à jour de système d’exploitation obligatoires. Aucune personnalisation n’est requise pour cette étape.

   14. **Configurer les composants Windows**: cette étape configure les fonctionnalités Windows requises. Aucune personnalisation n’est requise pour cette étape.

   15. **Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur une fois les fonctionnalités Windows configurées. Aucune personnalisation n’est requise pour cette étape.

   16. **Ajouter un utilisateur Skype local**: cette étape crée le compte Skype local utilisé pour vous connecter automatiquement à Windows et lancer l’application Microsoft Teams. Il n’y a pas de package logiciel associé et aucune personnalisation n’est requise pour cette étape.

   17. **Installer et configurer l’application SRS**: cette étape configure l’installation de l’application Microsoft teams salles pour le prochain démarrage du système d’exploitation.
       -   Vérifiez que le **service SRS v2 – configurer le package d’installation SRS** et **désactiver la redirection de système de fichiers 64 bits** est sélectionné.

> [!IMPORTANT]
> Il est très important que les étapes de la séquence de tâches doivent être dans l’ordre fourni. La modification de l’ordre des étapes ou la configuration d’étapes supplémentaires peuvent interrompre le déploiement.
>
> Configuration **et configuration de l’application SRS** vous devez disposer de la dernière étape de la séquence de tâches, sinon le déploiement risque d’échouer.

### <a name="create-deployment-for-the-task-sequence"></a>Créer un déploiement pour la séquence de tâches

1. Sélectionnez la séquence de tâches, puis **déployer**.

2. Sélectionnez **Parcourir** pour sélectionner collection cible pour le déploiement.

3. Sélectionnez **tous les ordinateurs inconnus** , puis cliquez sur **OK**.

4. Sélectionnez **Next (suivant**).

5. Sélectionnez **disponible** dans la liste déroulante **objectif** .

6. Sélectionnez **uniquement les éléments multimédias et PXE** dans la liste **mettre à disposition de** , puis sélectionnez **suivant**.
   > [!WARNING]
   > Il est très important que l' **objectif** soit défini sur **disponible**. Assurez-vous que l' **objectif** n’est **pas** défini sur **obligatoire**. Veillez également à sélectionner **uniquement média et PXE** dans le **rendez-vous disponible pour ce qui suit**.
   >
   > La définition de ces valeurs sur un autre fichier peut entraîner l’affichage de l’image de déploiement de Microsoft teams sur tous les ordinateurs.
7. Ne spécifiez aucun planning et sélectionnez **Next (suivant**).

8. Ne modifiez aucune valeur dans la section utilisation de l' **utilisateur** , puis sélectionnez **suivant**.

9. Ne modifiez aucune valeur dans la section **alertes** et sélectionnez **suivant**.

10. Ne modifiez aucune valeur dans la section **points de distribution** et sélectionnez **suivant**.

11. Confirmez les paramètres, puis sélectionnez **suivant**.

12. Sélectionnez **Fermer**.

<a name="validate-and-troubleshoot-the-solution"></a>Valider et dépanner la solution
--------------------------------------

Une fois que vous avez terminé les séquences de tâches System Center Configuration Manager, vous devez effectuer une opération de test pour vérifier que la séquence de tâches peut déployer et configurer des unités de Microsoft Teams.

1.  Connectez l’appareil de test au réseau filaire en utilisant l’une des cartes Ethernet prises en charge ou à l’aide du Dock surface. Si la fonctionnalité de démarrage PXE n’a pas été configurée pour votre environnement, vous pouvez utiliser l’image de démarrage sur le lecteur flash USB [que vous avez créé précédemment](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) pour démarrer à partir de la clé USB et vous connecter à Configuration Manager.

2.  Accédez au microprogramme et démarrez un démarrage PXE :

    1.  Assurez-vous que le périphérique surface est éteint.

    2.  Appuyez de façon prolongée sur le bouton **monter le volume** .

    3.  Appuyez et relâchez le bouton **d’alimentation** .

    4.  Après le démarrage de l’appareil, relâchez le bouton **monter le volume** .

    5.  Sélectionnez **configuration de démarrage**.

    6.  Effectuez l’une des actions suivantes :

        -   Sélectionnez **démarrage PXE**et faites-le glisser vers le haut de la liste. Vous pouvez également effectuer un balayage vers la gauche sur la carte réseau pour démarrer l’appareil immédiatement. Cela n’affecte pas l’ordre de démarrage.
        -   Sélectionnez le lecteur flash USB qui contient le média de démarrage.

3.  Sélectionnez **quitter**, puis cliquez sur **redémarrer maintenant**.

4.  Lorsque vous y êtes invité, sélectionnez **entrée** pour le service de démarrage réseau.

5.  Windows PE est chargé en mémoire et l’Assistant séquence de tâches démarre. Sélectionnez **Next (suivant** ) pour continuer.

6.  Sélectionnez la séquence de tâches que vous avez importée précédemment, puis sélectionnez **suivant**.

7.  Une fois l’application configurée, vous êtes invité à spécifier le nom d’un ordinateur pour l’appareil. L’interface utilisateur affiche un nom d’ordinateur recommandé en fonction du numéro de série de l’appareil surface Pro. Vous pouvez accepter le nom proposé ou en spécifier un nouveau. Suivez les instructions qui s’affichent sur l’écran d’attribution du nom de l’ordinateur. Lorsque vous sélectionnez **accepter**, le déploiement commence.

8.  Le reste du processus de déploiement est automatique et ne demande plus d’entrée utilisateur.

9.  Une fois la séquence de tâches de déploiement terminée, vous verrez l’écran de configuration suivant qui vous demande de configurer les paramètres de l’application Microsoft Teams.

    ![Écran de configuration initiale de l’application Microsoft teams](../media/room-systems-scale-image2.png)

10.  Branchez surface Pro dans la console Microsoft teams salles et configurez les paramètres de l’application.

11.  Vérifiez que les fonctionnalités répertoriées dans l' [aide de Microsoft teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) pour travailler sur l’appareil déployé.


Pour résoudre un problème d’échec de l’installation, recherchez le fichier **smsts. log** qui enregistre toutes les étapes exécutées dans une séquence de tâches de Configuration Manager.

Le fichier SMSTS. log est stocké sur l’un des chemins d’accès, en fonction de l’étape du processus de génération. Consultez le tableau suivant pour identifier le chemin d’accès au fichier SMSTS. log.


| **Phase de déploiement**                                                            | **Chemin du journal de séquence des tâches**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, avant le format HDD                                                        | X :\\Windows\\Temp\\smstslog\\smsts. log             |
| WinPE, après le format HDD                                                         | C :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts. log    |
| Système d’exploitation déployé avant l’installation de l’agent Configuration Manager | c :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts. log    |
| Système d’exploitation et agent Configuration Manager déployé                   | journaux\\de CCM\\\\%\\windir% system32\\Smstslog smsts. log |
| Exécution d’une séquence de tâches terminée                                                | % windir%\\system32\\,\\journaux\\de CCM smsts. log           |

> [!TIP]
> Vous pouvez sélectionner **F8** à tout moment au cours de la séquence de tâches pour ouvrir une console de commandes, puis accéder au fichier smsts. log.

Pour résoudre les problèmes de démarrage PXE, recherchez dans les deux fichiers journaux du serveur Configuration Manager spécifiques aux actions PXE :

-   **Pxecontrol. log**, situé dans le répertoire des journaux d’installation de Configuration Manager

-   **SMSPXE. log**, situé dans le répertoire des journaux du point de gestion de Configuration Manager

Pour obtenir la liste complète des fichiers journaux que vous pouvez utiliser pour résoudre les problèmes de l’installation de votre gestionnaire de configuration, voir [fichiers journaux dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).
