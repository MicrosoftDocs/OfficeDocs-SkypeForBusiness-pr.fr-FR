---
title: Mises à niveau automatisées | Mise à niveau de Skype entreprise vers équipes
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Vue d’ensemble des mises à niveau automatisées de Skype entreprise vers teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b42785d4f8d765e7d9600c2e195e48d7ec60d8ba
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780653"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Mises à niveau automatisées de Skype entreprise Online vers Microsoft teams

Microsoft propose des mises à jour automatiques aux équipes pour permettre aux petites entreprises de passer des appels de Skype entreprise Online avant le 31 juillet 2021. La mise à niveau automatisée réduit le nombre de tâches techniques requises pour les clients et permet d’insister sur le niveau de préparation de l’organisation, la sensibilisation des utilisateurs et la formation des équipes.

Une mise à niveau réussie de Skype entreprise vers Microsoft teams nécessite une planification pour la compatibilité technique et des utilisateurs. Lorsque vous êtes prêt à commencer, Microsoft propose un [plan d’action de mise à niveau](upgrade-basic.md) présentant les principales activités recommandées et les ressources associées pour mettre en place le passage de Skype entreprise à Teams.

## <a name="notifications-for-scheduled-customers"></a>Notifications pour les clients planifiés

Les clients Skype entreprise Online éligibles pour les mises à niveau automatisées d’équipes recevront une série de notifications de mise à niveau débutant 30 jours avant la date de mise à niveau prévue. Ces notifications sont transmises en tant que *plan pour les modifications apportées* au centre de messages d’administration, de mise à niveau des messages électroniques vers les utilisateurs finaux dans les indicateurs d’administration globale et dans l’application.

Ces notifications indiquent la date planifiée de la mise à niveau automatisée, qui sera liée aux ressources de mise à niveau et à la formation pour favoriser l’adoption et l’utilisation des équipes, et permettra aux clients de différer leur mise à niveau automatique d’un délai de 30 jours supplémentaire dans le cas où ils ne sont pas prêts à effectuer la mise à niveau à partir de la date prévue

## <a name="the-automated-upgrade-experience"></a>L’interface de mise à niveau automatique

Les mises à niveau automatisées s’exécutent à la date de mise à niveau prévue, qui est communiquée dans les messages électroniques de notification, le centre de messages, ainsi que le portail d’administration Teams. Le délai d’exécution de la mise à niveau est d’environ 15 minutes pour que les utilisateurs finaux aient toujours accès à la fonctionnalité Skype entreprise online. Lorsque la mise à niveau est terminée et que les utilisateurs se connectent à Skype entreprise Online, les utilisateurs peuvent uniquement utiliser teams pour la messagerie, les réunions et les appels.

## <a name="the-post-upgrade-experience"></a>L’interface après la mise à niveau

Au terme de la mise à niveau automatisée, le **mode de coexistence** est défini sur équipes uniquement et peut uniquement être modifié en mode de coexistence différent de Microsoft. Les administrateurs doivent vérifier [uniquement les considérations du mode équipe](teams-only-mode-considerations.md) avant la mise à niveau. Le tableau ci-dessous fournit une présentation générale de l’interface utilisateur de teams.


|  |  |
|---------|---------|
|**Discussions et appels**     | <UL><LI>Les appels et les discussions sont lancés et reçus dans teams<LI>Les utilisateurs peuvent interpartir (discussion/appel) avec n’importe quel utilisateur Skype entreprise<LI>Les utilisateurs ne peuvent pas communiquer avec des utilisateurs de Skype pour Consumer<LI>Les utilisateurs sont redirigés vers teams s’ils essaient de se connecter à Skype entreprise      </UL>  |
|**Meetings**     |  <UL><LI>Les utilisateurs planifient toutes les nouvelles réunions dans Teams (plugin remplacé)    </UL>   |
|**Données migrées**     |<UL><LI>Les contacts existants dans Skype entreprise, y compris le fédéré (mais aucune liste de distribution);<LI>Réunions Skype entreprise existantes (sur-locaux et en ligne) sont converties en réunions teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Ajournement de votre mise à niveau automatique

Le succès de transitions entre Skype entreprise Online et Microsoft teams nécessite une planification technique et une compatibilité utilisateur pour garantir que votre organisation est prête à tirer parti des fonctionnalités et des performances accrues de teams. Néanmoins, lors de la planification de votre mise à niveau, il est possible que votre organisation ne soit pas encore prête à effectuer une mise à niveau vers Microsoft teams pour le moment.

Si vous recevez une notification relative à la mise à niveau automatique planifiée vers teams et que vous voulez différer vers une date ultérieure, l’administrateur global peut se connecter au portail d’administration teams et cliquer sur le bouton de *Report* . Cette opération va entraîner la mise à jour automatique de 30 jours. Lorsque vous actualisez le portail d’administration teams après un report, une notification incluant votre nouvelle date de mise à jour automatique s’affiche.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Demandes de mise à niveau vers Skype entreprise

Nous autorisons la mise à niveau ponctuelle d’teams vers SfBO, pour permettre aux clients de préparer davantage la mise à niveau vers Teams. Les clients dont la mise à niveau vers une version antérieure seront réactivés pour la mise à niveau automatisé 60 jours après leur date de mise à niveau.

## <a name="related-content"></a>Contenu associé

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Déclassement de Skype Entreprise Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considérations relatives au mode Teams uniquement](teams-only-mode-considerations.md)

