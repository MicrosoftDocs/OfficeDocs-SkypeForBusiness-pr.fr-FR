---
title: Gérer Teams avec Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment gérer Microsoft Teams à l’aide de Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66f873b163222d3d9745e68881da2b8071f60eec
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396525"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gérer Teams avec Microsoft Teams PowerShell

Cet article vous montre comment utiliser Microsoft Teams PowerShell pour gérer Teams et Skype Entreprise.

Utilisez ces conseils conjointement avec la [référence d’applet de commande Microsoft Teams](/powershell/teams/?view=teams-ps) et [Skype Entreprise référence d’applet de commande](/powershell/skype/intro?view=skype-ps).

Pour gérer Teams dans le Centre d’administration Teams, consultez [Gérer Teams avec Azure Cloud Shell](#manage-teams-with-azure-cloud-shell).

## <a name="create-and-manage-teams-using-powershell"></a>Créer et gérer des équipes à l’aide de PowerShell

Les applets de commande permettant de créer et de gérer des équipes se trouvent dans le [module Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Les équipes sont soutenues par des groupes Office 365. Par conséquent, lorsque vous créez une équipe, vous créez un groupe. Il existe un ensemble d’applets de commande fournies pour fonctionner sur l’équipe principale et ses paramètres (, , ), la gestion des utilisateurs de l’équipe (``add-teamuser``, ``remove-teamuser``), ainsi que des applets de commande pour la gestion des canaux de l’équipe (``new-teamchannel``, ``remove-teamchannel``). ``set-team````get-team````new-team`` Toutes ces applets de commande peuvent être exécutées en tant qu’utilisateurs finaux, mais elles fonctionnent uniquement sur les équipes dont vous êtes propriétaire ou dont vous êtes membre. Si vous êtes administrateur général Administration ou Teams, vous serez en mesure d’agir sur toutes les équipes de votre organisation.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> [!NOTE]
> **L’ID de groupe** utilisé dans les applets de commande du module Microsoft Teams PowerShell est identique à la propriété **Identity** retournée par ``Get-UnifiedGroup`` le module Exchange PowerShell.

## <a name="manage-teams-with-azure-cloud-shell"></a>Gérer Teams avec Azure Cloud Shell

Cloud Shell est un interpréteur de commandes interactif, authentifié et accessible par navigateur qui vous permet de gérer vos ressources. Pour plus d’informations sur Cloud Shell, consultez [Azure Cloud Shell](/azure/cloud-shell/overview).

Pour accéder à Azure Cloud Shell et utiliser PowerShell pour gérer Teams, connectez-vous au Centre d’administration Teams.

1. Sélectionnez l’icône Cloud Shell dans le coin supérieur droit.

    ![Capture d’écran de l’en-tête du Centre d’administration Teams avec l’icône Cloud Shell.](media/cloud-shell-icon-select.png)

1. Lorsque vous y êtes invité, choisissez **PowerShell**.

    ![Capture d’écran de l’invite de Cloud Shell Azure.](media/cloud-shell.png)

1. Exécutez la commande suivante pour démarrer une session Teams PowerShell :

    ```powershell
    Connect-MicrosoftTeams
    ```

Une fois ces étapes terminées, vous êtes prêt à exécuter des commandes Teams PowerShell.

> [!IMPORTANT]
> Si vous souhaitez utiliser des applets de commande CS*, vous devez d’abord vous connecter à Teams à l’aide de la ``Connect-MicrosoftTeams -UseDeviceAuthentication`` commande.

## <a name="manage-policies-via-powershell"></a>Gérer les stratégies via PowerShell

> [!NOTE]
> - Skype Entreprise connecteur en ligne est consolidé dans Teams PowerShell. Il est actuellement disponible en préversion publique. Dans le temps, les applets de commande Skype Entreprise Online qui s’appliquent à Teams seront disponibles en mode natif dans le module Teams PowerShell. Les étapes d’installation sont disponibles dans l’article [Installer Teams PowerShell](teams-powershell-install.md) .
> - Les applets de commande seront disponibles dans votre session PowerShell une fois que vous vous connecterez à Skype Entreprise Online. Pour plus d’informations, consultez [Gérer Skype Entreprise Online avec Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Recherchez les applets de commande pour la gestion des stratégies dans le [module d’applet de commande Skype Entreprise](/powershell/module/teams).

Une stratégie est un groupe de paramètres qui peuvent être appliqués de manière granulaire à des utilisateurs individuels. Chaque type de stratégie a son propre ensemble d’applets de commande pour la création, l’affichage, la suppression et la mise à jour des stratégies elles-mêmes, puis l’affectation de ces stratégies aux utilisateurs. La structure générale est la suivante :

- Commandes **GET** (par exemple, ``Get-CsTeamsMeetingPolicy``) : renvoie les documents de stratégie que vous pouvez attribuer dans votre organisation, y compris les stratégies créées par Microsoft pour que vous les utilisiez ainsi que les stratégies personnalisées que vous avez créées.
  - Pour rechercher uniquement les stratégies personnalisées que vous avez créées dans votre organisation, utilisez ``-Filter "tag:*"``.

- **Nouvelles** commandes (par exemple, ``New-CsTeamsMeetingPolicy``) : crée de nouvelles stratégies que votre organisation doit affecter aux utilisateurs de votre organisation. Toutes les stratégies ne prennent pas en charge la création de stratégies personnalisées. Il s’agit souvent de s’assurer que les stratégies que vous utilisez dans votre organisation ont une combinaison de paramètres prise en charge.

- **Commandes SET** (par exemple) ``Set-CsTeamsMeetingPolicy``: définit des valeurs particulières sur une stratégie donnée. Certaines stratégies n’ont pas de commandes SET disponibles ou contiennent des paramètres qui ne peuvent pas être personnalisés dans la stratégie. Les descriptions de PowerShell vous indiquent quels paramètres ne peuvent pas être personnalisés.
  - Pour modifier la stratégie qui sera affectée par défaut aux utilisateurs de votre organisation qui n’ont pas de stratégie personnalisée affectée, exécutez ``Set-Cs<PolicyName> -Identity Global``.

- **Commandes REMOVE** (par exemple) ``Remove-CsTeamsMeetingPolicy``: supprime une stratégie personnalisée qui a été créée dans votre locataire. Si vous supprimez une stratégie personnalisée qui a été affectée à au moins un utilisateur de votre organisation, cet utilisateur revient à la stratégie globale.
  - Vous ne pouvez pas supprimer la stratégie globale de votre organisation, mais si vous souhaitez réinitialiser la stratégie globale de votre organisation aux paramètres par défaut fournis par Microsoft, exécutez ``Remove-Cs<PolicyName> -Identity Global``.

- **Commande GRANT** (par exemple) ``Grant-CsTeamsMeetingPolicy``: affecte une stratégie à un utilisateur particulier.
  - Pour supprimer une attribution de stratégie personnalisée et faire en sorte que l’utilisateur revient à la stratégie par défaut dans votre organisation, exécutez ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> Toutes les stratégies n’autorisent pas la création de stratégies personnalisées, et certaines stratégies ont des paramètres que vous ne pouvez pas personnaliser (vous pouvez donc afficher le paramètre, mais ne pouvez pas définir de valeur personnalisée pendant ``set-`` et ``new-``). La documentation de chaque applet de commande indique si les paramètres sont disponibles pour une utilisation par les clients.

Paramètres courants :

- **Identité** : pour ``Get-``, ``Set-````New-``et ``Remove-``, le paramètre **Identity** fait toujours référence à une instance de stratégie spécifique. Pour ``Grant``, le paramètre **Identity** fait référence à un objet utilisateur spécifique auquel la stratégie est appliquée.

## <a name="manage-configurations-via-powershell"></a>Gérer les configurations via PowerShell

Recherchez les applets de commande pour la gestion de votre configuration dans le [module d’applet](/powershell/module/skype) de commande Skype Entreprise.

Les configurations sont des compartiments de paramètres conservés dans le service qui ne peuvent pas être spécifiés au niveau de l’utilisateur. Les paramètres s’appliquent toujours à l’ensemble de l’organisation. Votre configuration globale est la seule configuration efficace de votre organisation. Chaque type de configuration est fourni avec deux applets de commande principales :

- ``Get-Cs<ConfigurationName>`` (par exemple, ``Get-CsTeamsClientConfiguration``):

- Commandes SET (par exemple) ``Set-CsTeamsClientConfiguration``: définissez des propriétés dans la configuration de ce type. Spécifiez les paramètres que vous souhaitez modifier.
    > [!NOTE]
    > Vous pouvez référencer la configuration que vous modifiez de deux manières : en spécifiant -**Identity Global** ou en exécutant ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.

## <a name="what-can-each-admin-role-do"></a>Que peut faire chaque rôle d’administrateur ?

Lire [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams](using-admin-roles.md) afin de comprendre quels rôles d’administrateur peuvent exécuter chaque applet de commande PowerShell.

## <a name="related-topics"></a>Rubriques connexes

[Installation de Teams PowerShell](teams-powershell-install.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Informations de référence sur les applets de commande Teams](/powershell/teams/?view=teams-ps)

[référence de l’applet de commande Skype Entreprise](/powershell/skype/intro?view=skype-ps)

[Utiliser des rôles d’administrateur pour gérer Teams](using-admin-roles.md)
