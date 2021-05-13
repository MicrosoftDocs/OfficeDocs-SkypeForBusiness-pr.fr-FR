---
title: Migration d’Skype Entreprise Online Connector vers le module Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer d’Skype Entreprise Online Connector au module PowerShell Teams à gérer les Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469716"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migration d’Skype Entreprise Online Connector vers le module Teams PowerShell

Teams Le module PowerShell fournit un ensemble complet d’lets de commande pour la gestion Teams à partir de la ligne de commande PowerShell. Les administrateurs n’ont pas besoin Skype d’un connecteur For Business Online pour leur administration Teams entreprise.

> [!NOTE]
> Teams administrateur ont été informés via la publication du Centre de messages (MC244740, spécifiée le 16 mars 2021 ; MC250940, dated April 16 2021) about this change.
>
> Teams Le module PowerShell utilise l’authentification moderne, mais le client Windows gestion à distance (WinRM) sous-jacent doit être configuré pour autoriser l’authentification de base. Pour obtenir des instructions sur [l’Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) de l’authentification de base, voir Télécharger et installer.

> [!WARNING]
> Skype Entreprise Les connexions Connecteur en ligne seront refusées à partir du 17 mai 2021. Contactez le Support Microsoft pour obtenir de l’aide et une assistance pour la migration vers Teams module PowerShell.

## <a name="how-to-migrate"></a>Comment migrer

La migration d’Skype Entreprise Online Connector vers Teams module PowerShell est simple et simple. La procédure ci-dessous explique comment faire.

1. Installez la dernière version Teams module PowerShell. Pour consulter la procédure, [voir Installer Microsoft Teams PowerShell.](teams-powershell-install.md)
2. Désinstaller Skype Entreprise Online Connector. Pour ce faire, dans le Panneau de contrôle, sélectionnez Programmes et fonctionnalités, Skype Entreprise **Online, Windows PowerShell Module,** puis **Désinstaller.**
3. Dans vos scripts PowerShell, modifiez le nom du module référencé ```Import-Module``` dans

    `SkypeOnlineConnector` ou `LyncOnlineConnector` `MicrosoftTeams` à .

    Par exemple, `Import-Module -Name SkypeOnlineConnector` changez pour `Import-Module -Name MicrosoftTeams` .

4. Lorsque vous utilisez Teams PowerShell Module 2.0 ou version ultérieure, mettez à jour vos scripts qui font `New-CsOnlineSession` `Connect-MicrosoftTeams` référence. `Import-PsSession`n’est plus nécessaire pour établir une session PowerShell distante Skype Entreprise Online, comme cela est implicite lors de `Connect-MicrosoftTeams` l’utilisation.

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a>Support en ligne

Gagnez du temps en commençant votre demande de service en ligne. Nous vous aiderons à trouver une solution ou à vous mettre en relation avec le support technique.
1.  Pour ce faire, voir le Centre [https://admin.microsoft.com](https://admin.microsoft.com) d’administration. Si un message vous indique que vous n’êtes pas autorisé à accéder à cette page ou à effectuer cette action, cela indique que vous n’êtes pas un administrateur. Qui avez des autorisations d’administrateur dans mon entreprise ?
2.  Sélectionnez **l’aide nécessaire**? .
3.  Vous avez besoin **d’aide**? , indiquez-nous ce sur quoi vous avez besoin d’aide, puis appuyez sur Entrée.
4.  Si les résultats ne vous aident pas, sélectionnez **Contacter le support.**
5.  Entrez une description de votre problème, confirmez votre numéro de contact et votre adresse de courrier, sélectionnez votre méthode de contact préférée, puis **Contactez-moi.** Le temps d’attente attendu est indiqué dans le cas où vous avez besoin d’aide ? .

## <a name="related-topics"></a>Sujets associés

[Installer Microsoft Teams PowerShell](teams-powershell-install.md)

[Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notes de publication de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams des cmdlet](/powershell/teams/?view=teams-ps)

[Skype Entreprise des cmdlet](/powershell/skype/intro?view=skype-ps)
