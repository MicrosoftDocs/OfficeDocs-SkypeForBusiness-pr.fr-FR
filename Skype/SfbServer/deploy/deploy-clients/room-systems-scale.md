---
title: Déployer des systèmes de salle Skype à l’aide de System Center Configuration Manager
ms.author: jambirk
author: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: Turgayo
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cette rubrique pour en savoir plus sur le déploiement de systèmes de salle Skype v2 sur les déploiements à grande échelle.
ms.openlocfilehash: 536530fa7836389d8c621f7c81287bfb564f024d
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699550"
---
# <a name="deploy-skype-room-systems-v2-by-using-system-center-configuration-manager"></a>Déployer des systèmes de salle Skype v2 à l’aide de System Center Configuration Manager

Cet article vous offre toutes les informations nécessaires pour créer vos déploiements v2 de systèmes de salle Skype à l’aide de System Center Configuration Manager.

Avec les méthodes d’utilisation fournies par System Center Configuration Manager, vous pouvez déployer le système d’exploitation et autres applications à plusieurs périphériques cible.

Utilisez l’approche illustrée ci-dessous pour vous guider tout au long de votre configuration du Gestionnaire de Configuration et personnaliser les exemples de packages et les scripts fournis dans ce guide, selon les besoins de votre organisation.

![Processus de déploiement v2 Skype salle systèmes à l’aide du Gestionnaire de Configuration](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Cette solution a été testée uniquement avec les déploiements basés sur la Surface Pro. Suivez les instructions du fabricant pour les configurations qui ne sont pas basées sur la Surface Pro.

## <a name="validate-prerequisites"></a>Valider la configuration requise

Pour déployer des systèmes de salle Skype v2 avec le Gestionnaire de Configuration, vérifiez que vous disposez de la configuration requise et conditions préalables suivantes.

### <a name="system-center-configuration-manager-requirements"></a>Configuration requise de System Center Configuration Manager

-   Version du système Center Configuration Manager doit être au moins 1706 ou version ultérieure. Nous vous recommandons d’utiliser 1710 ou version ultérieure. Consultez la rubrique [prise en charge pour Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) pour en savoir plus sur les versions de Windows 10 prend en charge le Gestionnaire de Configuration.

-   Une version prise en charge de l’évaluation de Windows et le Kit de déploiement (ADK) pour Windows 10 doit être installée. Voir les versions de l' [ADK de 10 Windows](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) que vous pouvez utiliser avec différentes versions du Gestionnaire de Configuration et vous assurer que votre déploiement comprend la version correcte.

-   Les serveurs de système de site doivent avoir reçu le rôle de point de distribution et les images de démarrage doivent être activées pour la [prise en charge de l’exécution environment (PXE) précédant le démarrage](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) activer des déploiements initiées par le réseau. Si la prise en charge PXE n’est pas activée, vous pouvez utiliser [un support de démarrage](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements.

-   Un compte d’accès au réseau doit être configuré pour prendre en charge de nouveaux scénarios de déploiement de l’ordinateur (vierge). Pour en savoir plus sur la configuration d’un compte d’accès au réseau, voir [Gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Il est recommandé d’activer la [prise en charge multidiffusion](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), si vous êtes susceptible de déployer la même image v2 Skype salle systèmes à plusieurs unités en même temps.

### <a name="networking-requirements"></a>Exigences de mise en réseau

-   Votre réseau doit posséder un serveur DHCP Dynamic Host Configuration Protocol (), configuré pour la distribution automatique des adresses IP pour les sous-réseaux où les systèmes de salle de Skype v2 unités seront déployés.

    > [!NOTE]
    > Durée de bail DHCP doit être définie sur une valeur supérieure à la durée de déploiement d’image. Dans le cas contraire, le déploiement peut échouer.

-   Votre réseau, y compris des commutateurs et des réseaux locaux virtuels (VLAN), doit être configuré pour prendre en charge PXE. Consultez votre fournisseur de réseau pour plus d’informations sur la configuration d’assistance IP et PXE. Autrement, vous pouvez utiliser [support](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) pour vos déploiements, si la prise en charge PXE n’est pas activé.

    > [!NOTE]
    > Surface Pro appareils, démarrage à partir du réseau (démarrage PXE) sont uniquement pris en charge lorsque vous utilisez une carte réseau Ethernet ou une station d’accueil de Microsoft. Les cartes Ethernet tiers ne prend en charge démarrage PXE avec Surface Pro. Pour plus d’informations, voir [déploiement de Surface et de cartes Ethernet](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>Configuration de System Center Configuration Manager pour le déploiement de système d’exploitation

Cet article suppose que vous disposez d’un déploiement de System Center Configuration Manager intègre et ne détail toutes les étapes nécessaires pour déployer et configurer le Gestionnaire de Configuration à partir de zéro. [documentation et les conseils de configuration](https://docs.microsoft.com/sccm/) de System Center Configuration Manager est une ressource importante ; Nous vous recommandons de que commencer avec ces ressources si vous n’avez pas encore déployé le Gestionnaire de Configuration.

Utilisez les instructions suivantes pour vérifier que les fonctionnalités de déploiement (système d’exploitation) du système d’exploitation sont correctement configurées.

### <a name="validate-and-upgrade-configuration-manager"></a>Valider et le Gestionnaire de Configuration de la mise à niveau

1.  Dans la console Configuration Manager, accédez à **Administration** \> **mises à jour et maintenance**.

2.  Vérifiez la version installée et les mises à jour qui n’ont pas encore été installés.

3.  Passez en revue la [prise en charge de Windows 10 dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Si vous devez mettre à niveau votre déploiement, sélectionnez la mise à jour que vous voulez installer, puis sélectionnez **Télécharger**.

4.  Une fois que le téléchargement est terminé, sélectionnez la mise à jour, puis sélectionnez **Installer le Pack de mise à jour**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Configurer des points de distribution pour prendre en charge PXE et la multidiffusion

1.  Dans la console Configuration Manager, accédez à **Administration** \> **Points de Distribution**.

2.  Sélectionnez le serveur du point de distribution qui va traiter le déploiement de v2 Skype salle systèmes, puis sélectionnez **Propriétés**.

3.  Sélectionnez l’onglet **PXE** et vérifiez que les paramètres suivants sont activés :
    -   Activer la prise en charge PXE pour les clients
    -   Autoriser ce point de distribution répondre aux demandes PXE entrantes
    -   Activer la prise en charge de l’ordinateur inconnu

4.  *Facultatif :* Pour activer la prise en charge multidiffusion, sélectionnez l’onglet **multidiffusion** et vérifiez que les paramètres suivants sont activés :
    -   Activer la multidiffusion envoyer des données simultanément à plusieurs clients
    -   Configurer la plage de ports UDP selon les recommandations de l’équipe de votre réseau

### <a name="configure-the-network-access-account"></a>Configurer le compte d’accès réseau

1.  Dans la console Configuration Manager, accédez à **Administration** \> **Site Configuration** \> **Sites**et sélectionnez le site.

2.  Dans le groupe **paramètres** , sélectionnez **Configurer les composants de Site** \> **La Distribution de logiciels**.

3.  Sélectionnez l’onglet **Compte d’accès au réseau** d’un ou plusieurs comptes, puis sélectionnez **OK**.

> [!NOTE]
> Les comptes n’avez pas besoin des droits spéciaux, à l’exception de l' **accéder à cet ordinateur à partir du réseau** sur le serveur du point de distribution. Un compte d’utilisateur de domaine générique sera approprié. Pour plus d’informations, voir [Gérer les comptes pour accéder au contenu dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Configurer une image de démarrage

1.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **système d’exploitation** \> **Images de démarrage**.

2.  Sélectionnez **l’image de démarrage (x64)**, puis sélectionnez **Propriétés**.

3.  Sélectionnez l’onglet **Source de données** et activez **déployer cette image de démarrage à partir du point de distribution à extension PXE**.

4.  Sélectionnez l’onglet **Composants facultatifs** pour installer les composants requis :

    1.  Sélectionnez l’icône en étoile et de recherche pour le **code HTML (HTA-WinPE)**

    2.  Cliquez sur **OK** pour ajouter la prise en charge des applications de HTML dans à l’image de démarrage.

5.  *Facultatif :* Pour personnaliser l’expérience de déploiement, sélectionnez l’onglet **personnalisation** .
    -   Activer la **commande prend en charge (test uniquement)** si vous souhaitez avoir accès à une invite de commandes au cours du déploiement. Lorsque cette option est activée, vous pouvez lancer une invite de commandes en sélectionnant **F8** à tout moment au cours du déploiement.
    -   Vous pouvez également spécifier un arrière-plan personnalisé à afficher lors du déploiement. Pour définir une image, activez **spécifier le fichier d’image arrière-plan personnalisé (chemin d’accès UNC** et sélectionnez votre arrière-plan.

6.  Lorsque vous êtes invité, sélectionnez **Oui** et distribuer l’image de démarrage mise à jour pour vos points de distribution.

Pour plus d’informations, voir [Gérer les images de démarrage avec System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).

> [!NOTE]
> Vous pouvez créer un support USB pour lancer le Gestionnaire de Configuration des déploiements basés sur la séquence tâche pour les environnements qui n’ont aucune prise en charge PXE. Le support amorçable contient uniquement l’image de démarrage, commandes prestart facultatifs leurs requis et les fichiers binaires du Gestionnaire de Configuration pour prendre en charge le démarrage de Windows PE et la connexion au Gestionnaire de Configuration pour le reste du processus de déploiement. Pour plus d’informations, voir [comment créer un support de démarrage](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Créer des packages de gestionnaire de Configuration

Gestionnaire de configuration requiert un nombre de packages pour déployer et configurer les unités de v2 Skype salle système.

Vous devez créer et configurer les packages suivants, puis les distribuer aux systèmes de site Configuration Manager qui ont été attribués le rôle de serveur de point de distribution.

| **Nom du package**                     | **Type**               | **Description**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - SRS Package d’Application     | Package de logiciels       | Package pour le kit de déploiement de systèmes de salle Skype v2                                      |
| SRS v2 - Package Sysprep             | Package de logiciels       | Package pour la Unattended.xml personnalisée configurer les unités v2 de systèmes de salle de Skype            |
| SRS v2 - Package Set-SRSComputerName | Package de logiciels       | Package de l’application HTML (HTA) attribuer un nom d’ordinateur au cours du déploiement    |
| SRS v2 - configurer le programme d’installation SRS         | Package de logiciels       | Package pour configurer le déploiement de l’application v2 de systèmes de salle de Skype                          |
| Système d’exploitation de SRS v2 - mises à jour de Package          | Package de logiciels       | Package de déploiement des mises à jour du système d’exploitation obligatoire                                      |
| SRS v2 - Package du certificat racine    | Package de logiciels       | Facultatif : Package pour déployer le certificat racine (non requis pour les unités à un domaine)  |
| SRS v2 - Package de l’Agent Microsoft OMS | Package de logiciels       | Facultatif : Package pour déployer et configurer l’agent Microsoft Operations Management Suite|
| SRS v2 - Package WinPE arrière-plan    | Package de logiciels       | Nom du package de l’image d’arrière-plan personnalisé à utiliser avec les images de démarrage                           |
| Entreprise Windows 10                | Image du système d’exploitation | Package pour le fichier d’installation de système d’exploitation (install.wim)                          |
| Surface Pro                          | Package de pilotes         | Package pour les pilotes de périphériques et le microprogramme Microsoft Surface Pro                     |
| Surface Pro 4                        | Package de pilotes         | Package pour les pilotes de périphériques et de microprogrammes pour Microsoft Surface Pro 4                   |

Pour plus d’informations, voir [Packages et des programmes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Créer des dossiers pour le package de fichiers sources

Gestionnaire de configuration requiert des fichiers sources du package pour être organisés en une structure de dossiers spécifiques lorsqu’elles sont d’abord créées et lorsqu’ils sont mis à jour.

Créez la structure de dossier suivante sur le site administration centrale de System Center Configuration Manager ou principal ou sur un partage de serveur que vous utilisez pour les fichiers sources du package hôte :

-   SRS v2 - Package de l’Agent Microsoft OMS
-   Système d’exploitation de SRS v2 - mises à jour de Package
-   SRS v2 - Package du certificat racine
-   SRS v2 - Package Set-SRSComputerName
-   SRS v2 - SRS Package d’Application
-   SRS v2 - configurer le programme d’installation SRS
-   SRS v2 - Package Sysprep
-   Pilotes
    -   Surface Pro
    -   Surface Pro 4
-   Systèmes d’exploitation
    -   Entreprise Windows 10

> [!TIP]
> Vous pouvez également [Télécharger](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) et utilisez le fichier zip qui inclut la structure de dossiers pour les packages, que vous devez utiliser les scripts et le modèle de séquence de tâches que vous devez l’importer.

### <a name="create-the-microsoft-operations-management-suite-agent-package"></a>Créer le package de l’agent Microsoft Operations Management Suite

1. Télécharger l’agent Operations Management Suite X-64 <https://go.microsoft.com/fwlink/?LinkId=828603>.

2. Extraire le package dans le dossier **SRS v2 - Package de l’Agent Microsoft OMS** en ouvrant une fenêtre d’invite de commandes et en **saisissant/C: MMASetup-AMD64.exe** à l’invite de commandes.

3. Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.

4. Entrez les informations suivantes pour créer le package :

   - Nom<strong>: SRS v2 - Package de l’Agent Microsoft OMS</strong>

   - Fabricant<strong>: Microsoft Corporation</strong>

   - Version<strong>: 8.1.11081.0</strong> (entrez la version du fichier d’installation téléchargé)

   - Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 - Package de l’Agent Microsoft OMS** , puis cliquez sur **suivant**.

5. Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.

6. Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.

7. Sélectionnez **Fermer**.

### <a name="create-the-operating-system-updates-package"></a>Créer le package de mises à jour de système d’exploitation

1. Dans le dossier **SRS v2 - Package de mises à jour du système d’exploitation** , créez un nouveau script PowerShell nommé **Install-SRSv2-OS-Updates.ps1**.

2. Copiez le script ci-dessous dans le script **Install-SRSv2-OS-Updates.ps1** . Vous pouvez également télécharger le script Install-SRSv2-OS-Updates.ps1 [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
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
   > Au moment de que cet article a été publié, uniquement [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) était requis. Vérifiez [Configure une console v2 de systèmes de salle Skype](console.md), pour voir si des mises à jour sont requises.

4. Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.

5. Entrez les informations suivantes pour créer le package :
   -   Nom : **SRS v2 – du système d’exploitation met à jour le Package**
   -   Fabricant : **Microsoft Corporation**
   -   Version : **1.0.0**
   -   Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 - Package de mises à jour du système d’exploitation** , puis cliquez sur **suivant**.

6. Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.

7. Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.

8. Sélectionnez **Fermer**.

### <a name="create-the-root-certificate-package-optional"></a>Créer le package de certificat racine (facultatif)

Vous créez ce package pour distribuer le certificat racine pour les périphériques qui ne sont pas être joint à un domaine Active Directory. Créer ce package uniquement si les deux conditions suivantes s’appliquent :
-   Votre déploiement comprend locale Lync ou Skype pour Business Server.
-   Unités de v2 Skype salle systèmes sont configurées pour fonctionner dans un groupe de travail au lieu d’un membre du domaine.

1.  Copiez le certificat racine dans le dossier **SRS v2 – Package du certificat racine** .

2.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.

3.  Entrez les informations suivantes pour créer le package :
    -   Nom : **SRS v2 – Package du certificat racine**
    -   Fabricant : *nom de votre organisation*
    -   Version : **1.0.0**
    -   Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 – Package du certificat racine** , puis cliquez sur **suivant**.

4.  Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.

5.  Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.

6.  Sélectionnez **Fermer**.

### <a name="create-the-skype-room-systems-v2-deployment-kit-package"></a>Créer le package de kit de déploiement v2 Skype salle systèmes

1.  Télécharger la dernière version du **kit de déploiement de systèmes de salle Skype v2** à partir de <https://go.microsoft.com/fwlink/?linkid=851168>, puis installez-le dans une station de travail.

2.  Copiez le contenu à partir de **c :\\Program Files (x86)\\Kit de déploiement de système de salle Skype** dans le dossier **SRS v2 - SRS Package d’Application** .

3.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.

4.  Entrez les informations suivantes pour créer le package :
    -   Nom : **SRS v2 – SRS Package d’Application**
    -   Fabricant : **Microsoft Corporation**
    -   Version : **3.1.104.0** (entrez la version du fichier d’installation téléchargé)
    -   Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 – SRS Package d’Application** , puis cliquez sur **suivant**.
5.  Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.

6.  Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.

7.  Sélectionnez **Fermer**.

### <a name="create-the-computer-name-assignment-package"></a>Créer le package d’affectation de nom ordinateur

1.  Dans le dossier **SRS v2 - Package Set-SRSComputerName** , créez une nouvelle application HTML nommée **Set-SRSComputerName.hta** .

2.  Copiez le script suivant dans le fichier **Set-SRSComputerName.hta** . Sinon, vous pouvez télécharger le fichier Set-SRSComputerName.hta à partir [d’ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
    ```
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
3.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.

4.  Entrez les informations suivantes pour créer le package :

    -   Nom : **SRS v2 - Package Set-SRSComputerName**

    -   Fabricant : **Microsoft Corporation**

    -   Version : **1.0.0**

    -   Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 - Set-SRSComputerName Package** , puis cliquez sur **suivant**.

5.  Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.

6.  Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.

7.  Sélectionnez **Fermer**.

### <a name="create-the-sysprep-package"></a>Créer le package Sysprep

1. Dans le dossier **SRS v2 – Sysprep Package** , créez un nouveau fichier XML nommé **Unattend.xml** .

2. Copiez le texte suivant dans le fichier **Unattend.xml** . Vous pouvez également télécharger le fichier Unattend.xml [ici](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).
   ```
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
3. Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**, puis sélectionnez **Créer un Package**.

4. Entrez les informations suivantes pour créer le package :
   -   Nom : **SRS v2 - Package Sysprep**
   -   Fabricant : **Microsoft Corporation**
   -   Version : **1.0.0**
   -   Activez la case à cocher **ce package contient des fichiers source** , entrez le chemin d’accès du dossier **SRS v2 – Sysprep Package** , puis cliquez sur **suivant**.
5. Sélectionnez **ne pas créer un programme**, puis cliquez sur **suivant**.

6. Passez en revue la page **vérifier les paramètres** , puis cliquez sur **suivant**.

7. Sélectionnez **Fermer**.

### <a name="create-the-windows-10-enterprise-package"></a>Créer le package Windows 10 Enterprise

1.  Obtenir un support Windows 10 entreprise x64 et copiez le fichier **install.wim** à le **systèmes d’exploitation\\Windows 10 entreprise** dossier.

2.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Images du système d’exploitation**, puis choisissez **Ajouter une Image de système d’exploitation**.

3.  Spécifiez le chemin d’accès au fichier **install.wim** que vous venez de copier, puis cliquez sur **suivant**.

4.  Mettre à jour le champ **Version** pour faire correspondre le numéro de version de l’image d’entreprise de 10 Windows, puis cliquez sur **suivant**.

5.  Passez en revue la page de **Détails** , puis cliquez sur **suivant**.

6.  Sélectionnez **Fermer**.

Pour plus d’informations, voir [Gérer les images de système d’exploitation avec System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Créer des packages de pilote de périphérique Surface Pro

Systèmes de salle Skype v2 est pris en charge pour la Surface Pro et Surface Pro 4. Vous devez créer un package pour chaque modèle de Surface Pro que vous disposez dans votre environnement.

> [!IMPORTANT]
> Les pilotes doivent être compatibles avec la version entreprise de 10 Windows et la version de kit de déploiement de v2 Skype salle systèmes. Pour plus d’informations, voir [télécharger les derniers microprogrammes et pilotes de périphériques de Surface](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) et [configurer une console](console.md).

1.  Téléchargez les pilotes et le microprogramme le plus récent.
    -   Pour une Surface Pro :<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Pour une Surface Pro 4 :<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extrayez le pilote téléchargé et le micrologiciel. Ouvrez une fenêtre d’invite de commandes et à l’invite de commandes, entrez l’une des commandes suivantes :
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **pilotes**, puis sélectionnez **Importation pilote**.

4.  Sélectionnez **Importer tous les pilotes dans le chemin d’accès réseau suivants (UNC)**, sélectionnez le dossier source (par exemple, c :\\_Sources\\pilotes\\Surface Pro), puis sélectionnez **suivant**.

5.  Dans la page **spécifier les détails pour les pilotes importés** , sélectionnez tous les pilotes répertoriés, puis sélectionnez **activer ces pilotes et autoriser des ordinateurs à les installer**.

6.  Sélectionner les **catégories**, créer une catégorie qui correspond au modèle de Surface, sélectionnez **OK**, puis cliquez sur **suivant**.

7.  Sélectionnez **Nouveau Package**.

8.  Spécifiez le nom du package qui correspond au modèle Surface Pro, entrez un chemin d’accès du dossier pour stocker les fichiers de package de pilote dans, sélectionnez **OK**, puis sélectionnez **suivant**.

9.  Dans la page **d’images de démarrage** , ne vérifiez que l’option Aucun images de démarrage sont sélectionnés, puis cliquez sur **suivant**.

10. Sélectionnez **Fermer**.

11. Accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **pilotes**, sélectionnez **dossier \> créer un dossier**, puis entrez un nom de dossier qui correspond au modèle de Surface Pro que vous venez d’importer les pilotes.

12. Déplacez tous les pilotes importées dans le dossier nouvellement créé pour faciliter la navigation et opération.

> [!NOTE]
> Répétez les étapes pour les autres modèles de Surface Pro, que vous devrez peut-être. Pour plus d’informations, voir [Gérer les pilotes dans System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).

## <a name="distribute-configuration-manager-packages"></a>Distribuer des packages de gestionnaire de Configuration

Tous les packages doivent être distribués sur les serveurs qui ont été attribués au rôle de point de distribution dans la hiérarchie du Gestionnaire de Configuration. Suivez les instructions ci-dessous pour lancer la distribution du package.

1.  Distribuer des logiciels.

    1.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **Gestion des applications** \> **Packages**. Sélectionnez tous les packages de logiciel que vous voulez distribuer, puis sélectionnez **Distribuer le contenu**.

    2.  Passez en revue la liste des packages, puis cliquez sur **suivant**.

    3.  Ajoutez tous les serveurs de point de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie de Configuration Manager) à la liste, puis cliquez sur **suivant**.

    4.  Cliquez sur **suivant**, puis sélectionnez **Fermer**.

2.  Distribuer des packages de pilotes.

    1.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Packages de pilotes**. Sélectionnez tous les packages à distribuer, puis sélectionnez **Distribuer le contenu**.

    2.  Passez en revue la liste des packages, puis cliquez sur **suivant**.

    3.  Ajoutez tous les serveurs de point de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie de Configuration Manager) à la liste, puis cliquez sur **suivant**.

    4.  Cliquez sur **suivant**, puis sélectionnez **Fermer**.

3.  Distribuer des packages de système d’exploitation.

    1.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Images du système d’exploitation**. Sélectionnez toutes les images de système d’exploitation que vous voulez distribuer, puis sélectionnez **Distribuer le contenu**.

    2.  Passez en revue la liste des packages, puis cliquez sur **suivant**.

    3.  Ajoutez tous les serveurs de point de distribution (ou groupes de points de distribution, en fonction de votre hiérarchie de Configuration Manager) à la liste, puis cliquez sur **suivant**.

    4.  Cliquez sur **suivant**, puis sélectionnez **Fermer**.

> [!NOTE]
> Distribution de package peut prendre un certain temps, en fonction de la taille du package, le Gestionnaire de Configuration hiérarchie, nombre de serveurs de point de distribution et la bande passante disponible dans votre réseau.
> 
> Tous les packages doivent être distribuées avant de pouvoir commencer le déploiement d’une unité de v2 Skype salle systèmes.
> 
> Vous pouvez consulter l’état de la distribution de package dans la console Configuration Manager en accédant à la **surveillance** \> **État de la Distribution** \> **État du contenu**.

## <a name="configuration-manager-task-sequences"></a>Séquences de tâches Configuration Manager

Vous utilisez séquences de tâches avec System Center Configuration Manager pour automatiser les étapes de déploiement d’une image du système d’exploitation sur un ordinateur de destination. Pour déployer une unité v2 de systèmes de salle Skype de manière automatique, vous créez une séquence de tâches qui fait référence à l’image de démarrage permet de démarrer l’ordinateur de destination Skype salle systèmes v2, l’image du système d’exploitation Windows 10 entreprise que vous voulez installer et les autre contenu supplémentaire, tel que d’autres applications ou les mises à jour logicielles.

### <a name="import-the-sample-task-sequence"></a>Importer la séquence de tâches exemple

Vous pouvez télécharger facilement importer une séquence de tâches exemple et personnaliser pour répondre à vos besoins.

1.  [**Télécharger**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) l’exemple de séquence de tâches et copiez le fichier .ZIP téléchargé dans un emplacement partagé.
2.  Dans la console Configuration Manager, accédez à la **Bibliothèque de logiciels** \> **systèmes d’exploitation** \> **Séquences de tâches**, puis sélectionnez **Séquence de tâches d’importation**.

3.  Sélectionnez **Parcourir**, accédez à l’emplacement de dossier partagé que vous avez utilisé à l’étape 1, sélectionnez le fichier **.zip de déploiement (EN-US) Skype salle systèmes v2** , puis cliquez sur **suivant**.

4.  Définir **l’Action** pour **Créer un nouveau**, puis cliquez sur **suivant**.

5.  Vérifier les paramètres, puis cliquez sur **suivant**.

6.  Sélectionnez **Fermer**.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Vérifiez que les packages de référence sont correctement liés à chaque étape de séquence de tâches.

1. Sélectionnez la séquence de tâches importés, puis sélectionnez **Modifier**.

    L’éditeur de séquence de tâches s’ouvre et affiche chaque étape séquentiel dont vous avez besoin pour déployer et configurer une unité de v2 Skype salle systèmes.

2. Passez en revue chaque étape et effectuer les mises à jour recommandées :

   1. **Redémarrez dans Windows PE**: cette étape redémarre et PXE Windows puis démarre l’ordinateur. Aucune modification n’est requise pour cette étape.

   2. **Partition de disque 0 – UEFI**: cette étape efface la configuration du disque et crée des partitions en fonction des paramètres configurés. Il est recommandé que vous apportez aucune modification à cette étape.

   3. **Nom de l’ordinateur SRS défini**: cette étape inclut une application HTML pour fournir une interface utilisateur pour définir un nom d’ordinateur de l’unité de v2 Skype salle systèmes lors du déploiement.
      -  Il s’agit d’une étape facultative, mais elle peut être désactivée uniquement si vous souhaitez gérer l’ordinateur d’attribution de noms via un processus de substitution.
      -  Vérifiez que le package **SRS v2 - Set-SRSComputerName** est activée. Si elle n’est pas le cas, accédez au package et sélectionnez-le.

   4. **Appliquer un système d’exploitation**: cette étape spécifie l’image de système d’exploitation à déployer et le fichier de réponses Sysprep automatisé à utiliser.
      -  Vérifiez que le fichier d’image de système d’exploitation Windows 10 entreprise approprié est sélectionné.
      -  Vérifiez que **utiliser une autonome ou le fichier de réponses Sysprep pour une installation personnalisée** est activée et le **SRS v2 - Sysprep Package** est sélectionnée. Vérifiez également que le **Nom de fichier** est définie sur **unattend.xml**.

   5. **Appliquer les paramètres Windows**: cette étape rassemble des informations sur l’installation de Windows.
      -  Fournissent des informations de gestion des licences et d’enregistrement, y compris la clé de produit, le mot de passe du compte administrateur local et le fuseau horaire (selon vos besoins).

   6. **Appliquer les paramètres réseau**: cette étape vous permet de spécifier un groupe de travail ou le nom de domaine Active Directory et l’unité d’organisation.
      > [!NOTE]
      > Pour les mesures recommandées à suivre dans le déploiement des unités de v2 Skype salle systèmes en tant que membres d’un domaine Active Directory, consultez la rubrique [Considérations en matière de système de salle Skype domaine rejoindre](domain-joining-considerations.md) .
   7. **Appliquer les pilotes :** Cette étape et ses sous-étapes sont utilisés pour déployer des pilotes de périphériques et de microprogrammes basée sur le modèle de Surface Pro que vous avez. Mettre à jour chaque étape pour spécifier le package de pilotes pertinents associé à ce déploiement.
      -   Chaque package de pilote est configuré pour tirer parti des filtres Windows Management Instrumentation (WMI) pour déployer les pilotes pertinents et microprogramme en fonction de la Surface Pro marque et le modèle.
      -   Nous vous recommandons vivement que vous ne modifiez pas la configuration de ces pilotes, sinon le déploiement peut échouer.

   8. **Configurer Windows et le Gestionnaire de Configuration**: cette étape déploie et configure le client Gestionnaire de Configuration. Mettre à jour cette étape pour spécifier le Package du Client Gestionnaire de Configuration intégrés.

   9. **Installer le certificat racine**: cette étape distribue le certificat racine pour les périphériques non joints au domaine et par conséquent est facultative et désactivée par défaut.
      -   Activer cette étape si vous avez besoin déployer un certificat racine pour les unités de v2 Skype salle systèmes.
      -   Si vous n’avez pas besoin d’effectuer cette étape, vérifiez que le **SRS v2 – Package du certificat racine** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.

   10. **Installer et configurer l’Agent de OMS**: cette étape installe la version 64 bits de l’agent Microsoft Operations Management Suite et configure l’agent pour se connecter à votre espace de travail de journal Analytique.
       -   Cette étape est désactivée par défaut. Activer cette étape uniquement si vous prévoyez d’utiliser OMS pour surveiller l’intégrité de vos unités de v2 Skype salle systèmes.
       -   Modifier cette étape et mettre à jour les paramètres de ligne de commande pour spécifier votre **Clé de l’espace de travail**et **l’ID de l’espace de travail** .
       -   Pour plus d’informations sur l’obtention de l’ID d’espace de travail Suite opérations de gestion et de la clé primaire, voir [ordinateurs Windows de se connecter au service journal Analytique dans Azure](with-oms.md#configure-test-devices-for-operations-management-suite-setup) .
       -   Vérifiez que le **SRS v2 – Package de l’Agent Microsoft OMS** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.
       -   Pour plus d’informations sur la surveillance de l’intégrité de votre déploiement de v2 Skype salle systèmes, voir [planifier Skype salle systèmes v2 gestion avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md) et [déployer les systèmes salle Skype v2 avec OMS](with-oms.md#configure-test-devices-for-operations-management-suite-setup).

   11. **Fichiers de Configuration de copie SRS v2**: cette étape copie les fichiers requis du programme d’installation et de configuration à partir du kit de déploiement de systèmes de salle Skype v2 sur le disque dur local. Aucune personnalisation n’est requise pour cette étape.
       -   Vérifiez que le **SRS v2 – SRS Package d’Application** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.

   12. **Install-SRSv2-OS mises à jour**: cette étape déploie les mises à jour de système d’exploitation obligatoire requis avec le déploiement de v2 Skype salle systèmes. Procédez comme suit :
       -   Vérifiez la [console Configure un v2 de systèmes de salle Skype](console.md) pour vérifier les mises à jour sont nécessaires.
       -   Vérifiez que votre **SRS v2 – Package de mises à jour du système d’exploitation** inclut toutes les mises à jour requises.
       -   Vérifiez que le **SRS v2 – Package de mises à jour du système d’exploitation** est activée.
       -   Vérifiez que la stratégie d’exécution PowerShell est définie sur **Ignorer**.

   13. **Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur une fois que les mises à jour de système d’exploitation obligatoires sont installés. Aucune personnalisation n’est requise pour cette étape.

   14. **Configurer les composants Windows**: cette étape configure les fonctionnalités Windows requises. Aucune personnalisation n’est requise pour cette étape.

   15. **Redémarrer l’ordinateur**: cette étape redémarre l’ordinateur après avoir configuré les fonctionnalités de Windows. Aucune personnalisation n’est requise pour cette étape.

   16. **Ajouter un utilisateur Local Skype**: cette étape crée le compte Skype local utilisé pour se connecter à Windows et démarrer l’application v2 de systèmes de salle Skype automatiquement. Cette étape ne possède pas de tout logiciel associé, et aucune personnalisation n’est nécessaire pour qu’il.

   17. **Définir vers le haut et configurer l’application SRS**: cette étape configure l’installation d’applications Skype salle systèmes v2 pour le redémarrage du système d’exploitation.
       -   Vérifiez que le **SRS v2 – configurer un Package d’installation SRS** et **redirection désactiver les 64 bits du système de fichiers** sont sélectionnés.

> [!IMPORTANT]
> Il est très important que les étapes de séquence de tâches doivent être dans l’ordre indiqué. Modification de l’ordre des étapes, ou la configuration des étapes supplémentaires peut empêcher le déploiement.
>
> **Définir vers le haut et configurer l’application SRS** étape doit être la dernière étape de la séquence de tâches, sinon le déploiement peut échouer.

### <a name="create-deployment-for-the-task-sequence"></a>Créer le déploiement de la séquence de tâches

1. Sélectionnez la séquence de tâches, puis sélectionnez **déployer**.

2. Sélectionnez **Parcourir** pour sélectionner le regroupement cible pour le déploiement.

3. Sélectionnez **Tous les ordinateurs inconnus** , puis sélectionnez **OK**.

4. Cliquez sur **suivant**.

5. Dans la liste déroulante **objet** , sélectionnez **disponible** .

6. Sélectionnez **uniquement multimédia et PXE** dans la liste **mettre à disposition de ce qui suit** , puis cliquez sur **suivant**.
   > [!WARNING]
   > Il est très important que le **rôle** est défini sur **disponible**. Assurez-vous que l' **objet** n’est **pas** la valeur **obligatoire**. Assurez-vous également que vous sélectionnez **uniquement multimédia et PXE** dans le **rendre disponible pour les éléments suivants**.
   >
   > Définition de ces valeurs à une chose risque de tous les ordinateurs obtenir l’image de déploiement de systèmes de salle Skype lors du démarrage.
7. Ne pas spécifier un calendrier et cliquez sur **suivant**.

8. Ne pas modifier tous les éléments dans la section **Expérience utilisateur** et cliquez sur **suivant**.

9. Ne pas modifier tous les éléments dans la section **alertes** et cliquez sur **suivant**.

10. Ne pas modifier tous les éléments dans la section **Points de Distribution** et cliquez sur **suivant**.

11. Vérifier les paramètres, puis sélectionnez **suivant**.

12. Sélectionnez **Fermer**.

<a name="validate-and-troubleshoot-the-solution"></a>Valider et résoudre les problèmes de la solution
--------------------------------------

Après avoir réalisé les séquences de tâches System Center Configuration Manager, vous devez effectuer une série de tests pour valider que la séquence de tâches permettre déployer et configurer des systèmes de salle de Skype v2 unités.

1.  Connectez le périphérique de test au réseau câblé à l’aide d’une des cartes Ethernet pris en charge ou à l’aide de la surface d’exposition station d’accueil. Si la fonctionnalité de démarrage PXE n’a pas été configurée pour votre environnement, vous pouvez utiliser l’image de démarrage sur la USB lecteur flash [que vous avez créé précédemment](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) pour démarrer à partir de USB et se connecter au Gestionnaire de Configuration.

2.  Accès du microprogramme et lancement de démarrage PXE :

    1.  Vérifiez que le périphérique Surface est éteint.

    2.  Maintenez le bouton **Volume** .

    3.  Appuyez puis relâchez le bouton **d’alimentation** .

    4.  Une fois le périphérique commence à démarrer, relâchez **le bouton** .

    5.  Sélectionnez **configuration de démarrage**.

    6.  Effectuez l’une des actions suivantes :

        -   Sélectionnez **démarrage PXE**et faites-le glisser vers le haut de la liste. Vous pouvez également, faites glisser gauche sur la carte réseau pour qu’il démarre immédiatement à l’appareil. Cela n’affecte pas l’ordre de démarrage.
        -   Sélectionnez le lecteur flash USB qui contient le support de démarrage.

3.  Sélectionnez **Quitter**, puis sélectionnez **Redémarrer maintenant**.

4.  Lorsque vous y êtes invité, sélectionnez **l’entrée** pour le service de démarrage réseau.

5.  Windows PE sont chargées en mémoire et démarre l’Assistant de séquence de tâches. Sélectionnez **suivant** pour continuer.

6.  Sélectionnez la séquence de tâches que vous avez importé précédemment, puis cliquez sur **suivant**.

7.  Une fois la configuration du disque est appliquée, vous devrez spécifier un nom d’ordinateur pour le périphérique. L’interface utilisateur affiche un nom d’ordinateur recommandée en fonction du numéro de série du périphérique Surface Pro. Vous pouvez accepter le nom proposé ou spécifier un autre. Suivez les instructions à l’écran d’affectation de nom. Lorsque vous sélectionnez **Accepter**, le déploiement commence.

8.  Le reste du processus de déploiement est automatique et ne demandez plus d’entrées utilisateur.

9.  Une fois que la séquence de tâches de déploiement a terminé la configuration du périphérique, vous verrez l’écran configuration suivant qui vous demande de configurer les paramètres d’application v2 Skype salle systèmes.

    ![Écran initial d’installation pour l’application v2 de systèmes de salle de Skype](../../media/room-systems-scale-image2.png)

10.  Branchez la Surface Pro dans la console de v2 Skype salle systèmes et configurer les paramètres d’application.

11.  Valider que les fonctionnalités répertoriées dans [l’aide de systèmes de salle Skype v2](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionnent sur l’appareil déployé.


Pour résoudre un échec de l’installation, vérifiez le fichier **SMSTS.log** , qui enregistre toutes les étapes exécutées dans une séquence de tâches du Gestionnaire de Configuration.

Le fichier SMSTS.log est stocké sur un d’un nombre de chemins d’accès, en fonction de l’étape du processus de génération. Consultez le tableau suivant pour identifier le chemin d’accès au fichier SMSTS.log.


| **Phase de déploiement**                                                            | **Chemin d’accès de tâche séquence journal**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, avant le format du disque dur                                                        | X :\\Windows\\Temp\\smstslog\\smsts.log             |
| WinPE, après le format du disque dur                                                         | C :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts.log    |
| Système d’exploitation déployé, avant l’installation de l’agent de Configuration Manager | c :\\_SMSTaskSequence\\journaux\\Smstslog\\smsts.log    |
| Système d’exploitation et l’agent de gestionnaire de Configuration déployé                   | %windir%\\System32\\ccm\\journaux\\Smstslog\\smsts.log |
| Complète de l’exécution de la séquence de tâches                                                | %windir%\\System32\\ccm\\journaux\\smsts.log           |

> [!TIP]
> Vous pouvez sélectionner **F8** à tout moment au cours de la séquence de tâches pour ouvrir une console de commande et accéder au fichier SMSTS.log.

Pour résoudre les problèmes de démarrage PXE, vérifiez les deux fichiers journaux sur le serveur du Gestionnaire de Configuration qui sont spécifiques aux actions PXE :

-   **Pxecontrol.log**, situé dans le répertoire de journaux d’installation Configuration Manager

-   **Smspxe.log**, situé dans le répertoire des journaux de Point de gestion Configuration Manager (MP)

Pour obtenir une liste complète des fichiers journaux que vous pouvez utiliser pour résoudre l’installation du Gestionnaire de Configuration, voir [fichiers journaux dans System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).
