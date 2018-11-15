---
title: Vue d’ensemble de PowerShell équipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: article
ms.service: msteams
description: Découvrez comment utiliser les contrôles de PowerShell pour gérer Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84de597cc5cc6a00227cf48d9d8559f9dcb3778e
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531609"
---
# <a name="teams-powershell-overview"></a>Vue d’ensemble de PowerShell équipes

Microsoft Teams possède un ensemble d’outils pour les administrateurs informatiques à gérer le produit via le Microsoft Teams & Skype pour Business Admin Center, les contrôles de PowerShell et API de graphique. Ce guide explique comment nous structure notre applets de commande PowerShell pour les administrateurs informatiques à utiliser et fournit des pointeurs vers la documentation supplémentaire. Notez que les différents rôles d’administrateur équipes ont accès aux applets de commande différents. Pour plus d’informations, voir [utiliser les équipes Microsoft rôles d’administrateur pour gérer les équipes](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Les modules devez-vous utiliser ?

Les contrôles de PowerShell pour gérer Microsoft Teams se trouvent dans deux modules PowerShell différents : le [module PowerShell d’équipes Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3) (aperçu public) et le [Skype pour le module PowerShell Business](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Le module PowerShell équipes contient toutes les applets de commande que vous avez besoin pour créer et gérer les équipes elle-même, tandis que la Skype pour le module PowerShell Business contient les contrôles de gestion des stratégies, les configurations et autres outils d’équipes. Les documents de référence pour les contrôles PowerShell indique quel module contient l’applet de commande que vous êtes étudier. (Éventuellement, les deux modules sont combinés.)

## <a name="what-can-each-admin-role-do"></a>Que peut faire chaque rôle d’administration ?

Lecture des [équipes de Microsoft utiliser les rôles d’administrateur pour gérer les équipes](using-admin-roles.md) pour comprendre les rôles d’administration différents d’applets de commande PowerShell sera en mesure de tirer parti.

## <a name="creating-and-managing-teams-via-powershell"></a>Création et gestion des équipes via PowerShell

Les applets de commande pour la création et la gestion des équipes se trouvent dans le [module PowerShell d’équipes Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3). 

Les équipes sont sauvegardés par groupes O365, donc lorsque vous créez une équipe, vous créez un groupe. Il existe un ensemble d’applets de commande fournies pour l’exploitation de l’équipe de base et de ses paramètres (``new-team``, ``get-team``, ``set-teamfunsettings``), ainsi que des applets de commande pour gérer les canaux de l’équipe (``new-teamchannel``, ``remove-teamchannel``). Toutes ces applets de commande peuvent être exécutée en tant que les utilisateurs finaux, mais qu’elles fonctionnent uniquement sur les équipes que vous possédez ou que vous êtes membre. Si vous êtes un administrateur Global ou un administrateur de Service d’équipes, vous serez en mesure d’agir sur toutes les équipes de votre organisation.

> **GroupId** utilisé dans les applets de commande PowerShell d’équipes Microsoft module est identique à la propriété **Identity** retournée par ``Get-UnifiedGroup`` dans le module PowerShell Exchange.

## <a name="managing-policies-via-powershell"></a>Gestion des stratégies via PowerShell

Les applets de commande pour la gestion des stratégies se trouvent dans le [Skype pour le module de commande d’entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Une stratégie est un groupe de paramètres qui peuvent être appliqués granulaire à des utilisateurs individuels. Chaque type de stratégie possède son propre ensemble d’applets de commande pour la création, l’affichage, la suppression et mise à jour des stratégies elles-mêmes et assignation de ces stratégies aux utilisateurs. La structure générale est la suivante :

- Les commandes GET (par exemple, ``Get-CsTeamsMeetingPolicy``) : retourner les documents de stratégie qui sont disponibles pour assigner dans votre organisation, à la fois les stratégies créées par Microsoft, vous pouvez utiliser et les stratégies personnalisées que vous avez créé.
   > Si vous souhaitez trouver uniquement les stratégies personnalisées que vous avez créés dans votre organisation, vous pouvez utiliser ``-Filter "tag:*"``.

- NOUVELLES commandes (par exemple, ``New-CsTeamsMeetingPolicy``) : vous permettent de créer des stratégies pour votre organisation qui sont ensuite disponibles pour être attribuées aux utilisateurs de votre organisation. Pas de toutes les stratégies de prise en charge la création de stratégies personnalisées. Il s’agit souvent pour garantir que les stratégies que vous utilisez dans votre organisation ont une combinaison de paramètres pris en charge.

- JEU de commandes (par exemple, ``Set-CsTeamsMeetingPolicy``) : vous permet de définir des valeurs spécifiques d’une stratégie donnée. Certaines stratégies n’ont pas commandes set disponibles, ou contenir des paramètres qui ne peuvent pas être personnalisées dans la stratégie. Chaque description PowerShell appelle les paramètres ne peuvent pas être personnalisées. 
   > Pour modifier la stratégie sera par défaut attribuée aux utilisateurs de votre organisation qui ne possèdent pas affectée à une stratégie personnalisée, exécutez ``Set-Cs<PolicyName> -Identity Global``.

- SUPPRIMER les commandes (par exemple, ``Remove-CsTeamsMeetingPolicy``) : vous pouvez utiliser cette applet de commande pour supprimer une stratégie personnalisée qui a été créée dans votre client. Si vous supprimez une stratégie personnalisée qui a été attribuée au moins un utilisateur dans votre organisation, que l’utilisateur revient à la stratégie globale.
   > Vous ne pouvez pas supprimer véritablement la stratégie globale dans votre organisation, mais si vous souhaitez rétablir les paramètres par défaut fournis par Microsoft la stratégie globale de votre organisation, vous pouvez exécuter ``Remove-Cs<PolicyName> -Identity Global``.

- Commande GRANT (par exemple, ``Grant-CsTeamsMeetingPolicy``) : vous permet d’affecter une stratégie à un utilisateur particulier.
   > Pour supprimer une affectation de stratégie personnalisée et qu’un utilisateur revient à la stratégie par défaut dans votre organisation, exécutez ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.

> [!TIP]
> Pas toutes les stratégies permettent à créer des stratégies personnalisées et des stratégies possèdent des paramètres que vous ne pouvez pas personnaliser (afin que vous pouvez afficher le paramètre mais que vous ne pouvez pas définir une valeur personnalisée pendant ``set-`` et ``new-``). La documentation de l’applet de commande spécifique appelle si les paramètres ne sont pas disponibles pour une utilisation par les clients.

Paramètres courants :

- **Identité**: pour ``Get-``, ``Set-``, ``New-``, et ``Remove-``, le paramètre **Identity** sera toujours faire référence à une instance de stratégie spécifique. Pour ``Grant``, le paramètre **Identity** fait référence à un objet utilisateur spécifique auquel la stratégie est appliquée.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Gestion des configurations via PowerShell

Les applets de commande pour la gestion de votre configuration se trouvent dans le [Skype pour le module de commande d’entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Les configurations sont des compartiments de paramètres conservés dans le service ne peut pas être spécifié à un niveau de l’utilisateur. Paramètres s’appliquent toujours à toute l’organisation. Votre configuration globale est effectif uniquement dans votre organisation. Chaque type de configuration est fourni avec deux cmdlets principales :

- ``Get-Cs<ConfigurationName>``(par exemple, ``Get-CsTeamsClientConfiguration``) : 

- JEU de commandes (par exemple, ``Set-CsTeamsClientConfiguration``) : définir les propriétés dans la configuration de ce type. Spécifiez les paramètres que vous souhaitez modifier.
   > Vous pouvez faire référence à la configuration que vous modifiez dans une des deux façons : en spécifiant -**Identity Global**, ou en exécutant ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Autres outils de PowerShell

Vous trouverez des instructions détaillées sur l’utilisation de tous les contrôles de PowerShell pour gérer Microsoft Teams et Skype pour les entreprises, notamment des descriptions détaillées des paramètres de chaque stratégie, dans la [référence d’applet de commande Microsoft équipes](https://docs.microsoft.com/powershell/teams/?view=teams-ps) et [Skype pour Référence de l’entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>En savoir plus

- [Référence d’applet de commande Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Skype pour la référence de l’entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Utiliser les rôles d’administration Microsoft Teams pour gérer des équipes](using-admin-roles.md)
