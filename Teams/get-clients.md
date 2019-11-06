---
title: Obtenir des clients pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les différents clients disponibles pour Microsoft Teams, notamment les clients Web, de bureau (Windows et Mac) et mobiles (Android, iOS).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f7a1cd3002135e2327ca4953ddfbb5b0393242d
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "37979697"
---
# <a name="get-clients-for-microsoft-teams"></a>Obtenir des clients pour Microsoft Teams 


Microsoft teams est disponible pour les clients de bureau (Windows, Mac et Linux), Web et mobiles (Android et iOS). Ces clients requièrent une connexion Internet active et ne prennent pas en charge le mode hors connexion.

> [!NOTE]
> À compter du 29 novembre 2018, vous ne pourrez plus utiliser l’application Microsoft Teams pour Windows 10 S (Preview) disponible auprès du Microsoft Store. Au lieu de cela, vous pouvez désormais télécharger et installer le client de bureau teams sur des appareils exécutant le mode Windows 10 S. Pour télécharger le client de bureau, accédez [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)à. Les versions MSI du client de bureau Teams ne sont pas encore disponibles pour les appareils exécutant le mode Windows 10 S.
>
> Pour plus d’informations sur le mode Windows 10 S, voir [Présentation du mode Windows 10 en s](https://www.microsoft.com/windows/s-mode). 

## <a name="desktop-client"></a>Client de bureau 

> [!Tip]
> Regardez la session suivante pour en savoir plus sur les avantages du client bureau Windows, comment il le planifier et comment déployer : [Windows Teams Client de bureau](https://aka.ms/teams-clients)

Le client de bureau Microsoft teams est une application autonome qui est également [disponible dans Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install). Teams est disponible pour Windows (7 +), versions 32-bit et 64 bits, macOS (10.10 +) et Linux (au `.deb` `.rpm` format.). Sous Windows, Teams requiert .NET Framework 4.5 ou version ultérieure ; le programme d’installation Teams propose de l’installer pour vous si vous ne l’avez pas. Sur Linux, les responsables de package tels que apt et yum essaient d’installer une configuration requise pour vous. Néanmoins, si ce n’est pas le cas, vous devez installer la configuration requise avant d’installer teams sur Linux.

Les clients de bureau fournissent la prise en charge de communications en temps réel (audio, vidéo, et partage de contenu) pour les réunions d'équipe, les appels de groupes et les appels en tête-à-tête.

Les clients de bureau peuvent être téléchargés et installés par les utilisateurs finaux directement à partir de [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) s'ils disposent des autorisations locales appropriées (les droits d'administration ne sont pas requis pour installer le client Teams sur un PC, mais le sont pour un Mac).

Les administrateurs informatiques peuvent choisir la méthode de distribution des fichiers d’installation sur les ordinateurs de leur organisation. Quelques exemples incluent System Center Configuration Manager (Windows) ou JAMF Pro (macOS). Pour obtenir le package MSI de distribution Windows, voir [installer Microsoft Teams à l’aide de MSI](msi-deployment.md).  

> [!NOTE]
> La distribution du client via ces systèmes sert uniquement à l'installation initiale des clients Microsoft Teams, non pour les mises à jour futures.

### <a name="windows"></a>Windows

L’installation de Microsoft Teams pour Windows fournit des programmes d’installation téléchargeables dans architecture 32 bits et 64 bits.

> [!NOTE]
> L'architecture (32 bits ou 64 bits) de Microsoft Teams est indépendante de Windows et ignore celle d'Office installée.

Le client Windows est déployé vers le dossier AppData situé dans le profil de l’utilisateur. Le déploiement au profil local de l’utilisateur permet au client d’être installé sans exiger des droits élevés. Le client Windows exploite les emplacements suivants :

- %LocalAppData%\\Microsoft\\Teams

- % LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- % LocalAppData%\\SquirrelTemp

Lorsque les utilisateurs lancent un appel à l'aide du client Microsoft Teams la première fois, un message d'avertissement concernant les paramètres de pare-feu Windows peut s'afficher et requérir l'autorisation de la communication.  Les utilisateurs peuvent être invités à ignorer ce message, car l’appel fonctionnera, même lorsque l’avertissement est fermé.

![Capture d'écran d'une boîte de dialogue Alerte de sécurité Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configuration de pare-feu Windows sera modifiée même si l'invite est ignorée en sélectionnant Annuler. Deux règles de trafic entrant pour teams.exe seront créées avec une action de blocage pour les protocoles TCP et UDP.

### <a name="mac"></a>Mac

Les utilisateurs de Mac peuvent installer Teams à l’aide d’un fichier d’installation PKG pour ordinateurs macOS. L’accès administrateur est requis pour installer le client Mac. Le client macOS est installé dans le dossier /Applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Installer Teams en utilisant le fichier PKG

1. À partir de la [page de téléchargement Teams](https://teams.microsoft.com/downloads), sous **Mac**, cliquez sur **Télécharger**.
2. Double-cliquez sur le fichier PKG.
3. Suivez les indications de l'Assistant Installation pour effectuer l'installation.
4. Teams sera installé dans le dossier /Applications. Il s’agit d’une installation à l’échelle de l’ordinateur.

> [!NOTE]
> Pendant l’installation, le PKG invite à entrer des informations d’identification d’administrateur. L’utilisateur doit entrer les informations d’identification d’administrateur, peu importe si l’utilisateur est un administrateur.

Si un utilisateur a une installation DMG de Teams et souhaite la remplacer par l’installation PKG, l’utilisateur doit :

1. Quitter l’application Teams.
2. Désinstaller l’application Teams.
3. Installez le fichier PKG.

Les administrateurs informatiques peuvent utiliser le déploiement géré de Teams pour distribuer les fichiers d’installation pour tous les Macs dans leur organisation, tels que Jamf Pro.

> [!NOTE]
> Si vous rencontrez des problèmes en installant le PKG, faites-le nous savoir. Dans la section **Commentaires** à la fin de cet article, cliquez sur **Adresser un commentaire**.

### <a name="linux"></a>*

Les utilisateurs seront en mesure d’installer des packages Linux `.deb` natifs dans et `.rpm` formats.

> [!NOTE] 
> Microsoft teams sur un client Linux est disponible en version d’évaluation limitée. Signaler des bogues à l’aide `Report a Problem` du client. Pour connaître les problèmes connus, voir [problèmes connus](Known-issues.md).

#### <a name="install-teams-using-deb-package"></a>Installation d’équipes à l’aide d’une DEB

1. Téléchargez le package à https://aka.ms/getteamspartir de. (Le client Linux est en version d’évaluation limitée et sera bientôt lancé. Si vous ne voyez pas le client Linux sur la page téléchargements, cela signifie qu’il n’a pas encore été lancé.)
2. Installez l’une des options suivantes :  
    - Ouvrez l’outil de gestion des packages approprié et examinez le processus d’installation de l’application Linux auto-guidée.
    - Ou, si vous aimez le terminal, tapez :`sudo apt install **teams download file**`

Vous pouvez lancer des équipes par le biais d’activités ou `Teams`par le biais d’un terminal en tapant. 

#### <a name="install-teams-using-rpm-package"></a>Installer teams à l’aide du package RPM

1. Téléchargez le package à https://aka.ms/getteamspartir de. (Le client Linux est en version d’évaluation limitée et sera bientôt lancé. Si vous ne voyez pas le client Linux sur la page téléchargements, cela signifie qu’il n’a pas encore été lancé.)
2. Installez l’une des options suivantes :
    - Ouvrez l’outil de gestion des packages approprié et examinez le processus d’installation de l’application Linux auto-guidée.
    - Ou, si vous aimez le terminal, tapez :`sudo yum install **teams download file**`

Vous pouvez lancer des équipes par le biais d’activités ou `Teams`par le biais d’un terminal en tapant.

## <a name="web-client"></a>Client Web 

Le client Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) est complet et fonctionnel, et peut être utilisé par divers navigateurs. Le client web prend en charge les Réunions et Appels à l’aide de webRTC, aucun plug-in ou téléchargement n’est donc requis pour exécuter Teams dans un navigateur web. Le navigateur doit également être configuré de manière à autoriser les cookies tiers. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Le client web effectue la détection de la version navigateur lors de la connexion à [ https://teams.microsoft.com ](https://go.microsoft.com/fwlink/?linkid=855753). En cas de version non prise en charge, il bloquera l'accès à l'interface Web et recommandera de télécharger le client de bureau ou l'application mobile.

## <a name="mobile-clients"></a>Clients mobiles

Les applications mobiles Microsoft Teams sont disponibles pour Android et iOS et sont destinées aux utilisateurs en déplacement pour participer aux chats basées sur la conversation et autorisent les appels audio privés. Pour les applications mobiles, accédez à Google Play et l’Apple App Store. L’application Windows Phone a été retirée le 20 juillet 2018 et peut ne plus fonctionner. 

Les plateformes mobiles prises en charge pour les applications mobiles Microsoft Teams sont les suivantes :

-   **Android** : 4.4 ou version ultérieure

-   **iOS**:  10.0 ou version ultérieure

> [!NOTE]
> La version mobile doit être disponible au public pour que Teams fonctionne comme prévu.

Les applications mobiles sont distribuées et mises à jour par le biais du magasin d’applications de la plateforme mobile correspondante uniquement. La distribution des applications mobiles via le GPM ou le chargement hors Windows Store n’est pas prise en charge par Microsoft. Une fois l’application mobile installée sur une plate-forme mobile prise en charge, l’application mobile teams est prise en charge, à condition que la version soit dans les trois mois de la version actuelle.


| | | |
|---------|---------|---------|
|![Icône illustrant un point de décision](media/Get_clients_for_Microsoft_Teams_image4.png)      |Point de décision         |Existe-il des restrictions empêchant les utilisateurs d'installer le client Microsoft Teams appropriés sur leur appareil ?         |
|![Icône montrant les étapes suivantes](media/Get_clients_for_Microsoft_Teams_image5.png)     |Étapes suivantes         |Si votre organisation limite l'installation de logiciels, veillez à ce que ce processus soit compatible avec Microsoft Teams. Note : Les droits d'administration ne sont pas requis pour l'installation d'un client sur PC, mais le sont pour un Mac.         |

## <a name="client-update-management"></a>Gestion des mises à jour du client

Pour le moment, les clients sont mis à jour automatiquement par le service Microsoft teams sans qu’aucune intervention de l’administrateur informatique ne soit requise. Si une mise à jour est disponible, le client télécharge automatiquement la mise à jour et lorsque celle-ci est inactif pendant un certain temps, le processus de mise à jour commence.

## <a name="client-side-configurations"></a>Configurations côté client

Actuellement, aucune option prise en charge n'est disponible pour configurer le client via l'administration des clients, PowerShell, des objets de stratégie de groupe ou le registre.

## <a name="notification-settings"></a>Paramètres des notifications

Aucune option n'est actuellement disponible pour les administrateurs informatiques pour configurer les paramètres des notifications côté client. Toutes les options de notification sont définies par l'utilisateur. La figure ci-après présente les paramètres client par défaut.

![Capture d'écran des paramètres Notifications.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a>Exemple de Script PowerShell

Cet exemple de script qui doit s’exécuter sur des ordinateurs clients dans le contexte d’un compte d’administrateur élevé, crée une nouvelle règle de pare-feu entrant pour chaque dossier utilisateur trouvé dans c:\users. Lorsque Teams détecte cette règle, il permet d’empêcher l’application Teams d’inviter les utilisateurs à créer des règles de pare-feu lorsque les utilisateurs passent leur premier appel à partir de Teams. 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
