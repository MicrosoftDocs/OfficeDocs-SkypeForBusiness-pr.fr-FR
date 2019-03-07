---
title: Obtenir des clients pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les différents clients disponibles pour Teams Microsoft qui incluent le web, de bureau (Windows et Mac) et mobile (Android et e/s).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32fba747deb73b7f4e2c19b96cb4c0c62b741722
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458907"
---
<a name="get-clients-for-microsoft-teams"></a>Obtenir des clients pour Microsoft Teams 
===========================

Microsoft Teams a des clients mobiles et disponibles pour les web (Windows et Mac) du bureau (Android et e/s). Ces clients requièrent une connexion Internet active et ne prennent pas en charge le mode hors connexion.

> [!NOTE]
> À compter du que 29 novembre 2018, vous ne serez en mesure d’utiliser le Teams Microsoft pour une application Windows 10 S (Preview), disponible à partir de Microsoft Store. Nous vous recommandons d’utiliser une des applications équipes décrites ci-dessous dans cet article après 29 novembre.

<a name="desktop-client"></a>Client de bureau 
--------------

> [!Tip]
> Regarder la session suivante pour en savoir plus sur les avantages du bureau Windows Client, comment planifier et comment le déployer : [Client de bureau Windows équipes](https://aka.ms/teams-clients)

Le client de bureau Microsoft Teams est une application autonome et actuellement ne fait pas partie d’Office 365 ProPlus. Les équipes est disponible pour Windows (7 +), les versions 32 bits et 64 bits et Mac OS (10.10 +). Sous Windows, les équipes nécessite le .NET Framework 4.5 ou version ultérieure ; le programme d’installation équipes propose d’installer pour vous si vous ne l’avez pas. 

Les clients de bureau prennent en charge de communications en temps réel (partage de contenu, vidéo et audio) pour les réunions de l’équipe, les appels en tête-à-tête group appelant et privés.

Clients de bureau peuvent être téléchargées et installées par les utilisateurs finaux directement à partir de [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) s’ils disposent des autorisations appropriées locales (des droits d’administration ne sont pas requis pour installer le client équipes sur un PC, mais sont requis sur un Mac).

Les administrateurs informatiques peuvent choisir leur méthode préférée pour distribuer les fichiers d’installation sur les ordinateurs de leur organisation, comme System Center Configuration Manager (Windows) ou Jamf Pro (Mac OS). Pour obtenir le package MSI pour la distribution de Windows, voir [installer des équipes de Microsoft à l’aide de MSI](msi-deployment.md).

> [!NOTE]
> La distribution du client via ces systèmes sert uniquement à l'installation initiale des clients Microsoft Teams, non pour les mises à jour futures.

### <a name="windows"></a>Windows

L’installation de Microsoft Teams pour Windows fournit des programmes d’installation téléchargeables dans l’architecture 32 bits et 64 bits.

> [!NOTE]
> L’architecture (32 bits et 64 bits) de Microsoft Teams est indépendante de l’architecture de Windows et Office est installé.

Le client Windows est déployé dans le dossier AppData situé dans le profil de l’utilisateur. Déploiement sur le profil d’utilisateur local permet au client d’être installé sans disposer de droits élevés. Le client Windows tire parti des emplacements suivants :

- %LocalAppData%\\Microsoft\\équipes

- %LocalAppData%\\Microsoft\\TeamsMeetingsAddin

- %AppData%\\Microsoft\\équipes

- %LocalAppData%\\SquirrelTemp

Lorsque les utilisateurs lancer un appel à l’aide du client Microsoft Teams pour la première fois, ils peuvent noter un avertissement vous demandant aux utilisateurs permettre la communication avec les paramètres du pare-feu Windows. Les utilisateurs peuvent demander à ignorer ce message, car l’appel fonctionne, même lorsque le message d’avertissement est rejeté.

![Capture d'écran d'une boîte de dialogue Alerte de sécurité Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configuration de pare-feu Windows sera modifiée même si l'invite est ignorée en sélectionnant Annuler. Deux règles de trafic entrant pour teams.exe seront créées avec une action de blocage pour les protocoles TCP et UDP.

### <a name="mac"></a>Mac

Les utilisateurs de Mac peuvent installer des équipes à l’aide d’un fichier d’installation PKG pour les ordinateurs Mac OS. L'accès administrateur est obligatoire pour installer le client Mac. Le client Mac OS est installé dans le dossier/applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Installer des équipes en utilisant le fichier PKG

1. À partir de la [page de téléchargement des équipes](https://teams.microsoft.com/downloads), sous **Mac**, cliquez sur **Télécharger**.
2. Double-cliquez sur le fichier PKG.
3. Suivez l’Assistant d’installation pour terminer l’installation.
4. Les équipes seront installés au dossier/applications. Il s’agit d’une installation d’échelle de l’ordinateur.

> [!NOTE]
> Pendant l’installation, la PKG vous invite à des informations d’identification d’administration. L’utilisateur doit entrer les informations d’identification d’administration, quel que soit ou non l’utilisateur est un administrateur.

Si un utilisateur disposant d’une installation DMG des équipes actuellement et remplacez-la par l’installation PKG souhaite, l’utilisateur doit :

1. Quittez l’application d’équipes.
2. Désinstaller l’application d’équipes.
3. Installez le fichier PKG.

Les administrateurs informatiques peuvent utiliser des équipes de déploiement pour distribuer les fichiers d’installation pour tous les Mac dans leur organisation, telles que Jamf Pro.

> [!NOTE]
> Si vous rencontrez des problèmes d’installation le PKG, faites-le nous savoir. Dans la section **des commentaires** à la fin de cet article, cliquez sur **commentaires sur le produit**.

<a name="web-client"></a>Client Web 
----------

Le client web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) est un client complète et fonctionnel qui peut être utilisé à partir de nombreux navigateurs. Le client web prend en charge les réunions et les appels à l’aide de webRTC, donc il n’existe aucun plug-in ou télécharger requises pour exécuter des équipes dans un navigateur web. Le navigateur doit être configuré pour autoriser les cookies tiers. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Le client web exécute la détection de version du navigateur lorsqu’ils se connectent à [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Si une version de navigateur non pris en charge est détectée, il bloque l’accès à l’interface web et est recommandé que l’utilisateur télécharger le client de bureau ou d’une application mobile.

<a name="mobile-clients"></a>Clients mobiles
--------------

Les applications mobiles Microsoft Teams sont disponibles pour Android et iOS et sont destinées aux utilisateurs atteindre la participation à des conversations en fonction de conversation et autorisent les appels audio d’égal à égal. Pour les applications mobiles, accédez aux magasins mobiles pertinents Google lire et l’App Store Apple. L’application Windows Phone a été retirée 20 juillet 2018 et peuvent ne plus fonctionner. 

Les plateformes mobiles prises en charge pour les applications mobiles Microsoft Teams sont les suivantes :

-   **Android** : 4.4 ou version ultérieure

-   **iOS**:  10.0 ou version ultérieure

> [!NOTE]
> La version mobile doit être disponible au public dans l’ordre des équipes fonctionnent comme prévu.

Les applications mobiles sont distribuées et mises à jour uniquement via la boutique d'applications de la plateforme mobile respective et ne peuvent pas être distribuées via des solutions MDM (gestion des périphériques mobiles) ni utilisées comme version de test.


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Get_clients_for_Microsoft_Teams_image4.png)      |Point de décision         |Existe-il des restrictions empêchant les utilisateurs d'installer le client Microsoft Teams appropriés sur leur appareil ?         |
|![Icône Étapes suivantes.](media/Get_clients_for_Microsoft_Teams_image5.png)     |Étapes suivantes         |Si votre organisation limite l'installation de logiciels, veillez à ce que ce processus soit compatible avec Microsoft Teams. Note : Les droits d'administration ne sont pas requis pour l'installation d'un client sur PC, mais le sont pour un Mac.         |

<a name="client-update-management"></a>Gestion des mises à jour du client
------------------------

Actuellement, les clients sont automatiquement mis à jour par le service de Microsoft Teams ; aucune intervention de l'administrateur informatique n'est requise. Si une mise à jour est disponible, le client la téléchargera automatiquement et lorsque l'application est inactive pendant un certain temps, le processus de mise à jour se lancera.

<a name="client-side-configurations"></a>Configurations côté client
---------------------------

Actuellement, aucune option prise en charge n'est disponible pour configurer le client via l'administration des clients, PowerShell, des objets de stratégie de groupe ou le registre.

<a name="notification-settings"></a>Paramètres des notifications
----------------------------

Aucune option n'est actuellement disponible pour les administrateurs informatiques pour configurer les paramètres des notifications côté client. Toutes les options de notification sont définies par l'utilisateur. La figure ci-après présente les paramètres client par défaut.

![Capture d'écran des paramètres Notifications.](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>Exemple de Script PowerShell
----------------------------

Cet exemple de script qui doit s’exécuter sur les ordinateurs clients dans le contexte d’un compte d’administrateur avec élévation de privilèges, créera une nouvelle règle de pare-feu entrant pour chaque dossier utilisateur trouvé dans c:\users. Lorsque cette règle trouve des équipes, il empêchera l’application d’équipes invite les utilisateurs à créer des règles de pare-feu lorsque les utilisateurs effectuent leur premier appel des équipes. 

```
$users = Get-Childitem c:\users
foreach ($user in $users) 
{
    $Path = "c:\users\" + $user.Name + "\appdata\local\Microsoft\Teams\Current\Teams.exe"
    if (Test-Path $Path) 
    {
            $name = "teams.exe " + $user.Name
            if (!(Get-NetFirewallRule -DisplayName $name))
        {
                New-NetFirewallRule -DisplayName “teams.exe” -Direction Inbound -Profile Domain -Program $Path -Action Allow
        }
    }
}
<#
        .ABOUT THIS SCRIPT
        (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.

        Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 

        The script will create a new inbound firewall rule for each user folder found in c:\users. 

        Requires PowerShell 3.0
        
#>

```
