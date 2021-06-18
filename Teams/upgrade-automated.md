---
title: Mises à niveau automatisées| Mise à niveau de Skype Entreprise vers Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Vue d’ensemble des mises à niveau automatisées de Skype Entreprise vers Teams
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
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120539"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Mises à niveau automatisées de Skype Entreprise Online vers Microsoft Teams

Microsoft propose des mises à niveau automatisées vers Teams pour aider les petites entreprises à assurer la réussite de la transition de Skype Entreprise Online avant le 31 juillet 2021 - retrait du service. La mise à niveau automatisée réduit le nombre de tâches techniques requises pour les clients et permet de se concentrer davantage sur la préparation de l’organisation, la sensibilisation des utilisateurs et la formation Teams.

Une mise à niveau réussie de Skype Entreprise vers Microsoft Teams nécessite une planification pour la disponibilité des utilisateurs et techniques. Lorsque vous êtes prêt à commencer, Microsoft propose un [plan d’action](upgrade-basic.md) de mise à niveau comportant les principales activités recommandées et les ressources associées pour implémenter le passage réussi de Skype Entreprise à Teams.

## <a name="notifications-for-scheduled-customers"></a>Notifications pour les clients programmés

Les clients Skype Entreprise Online éligibles aux mises à niveau automatisées vers Teams recevront une série de notifications de mise à niveau à compter de 30 jours avant leur date de mise à niveau prévue. Ces notifications seront remises en tant que plan pour la modification des publications dans le Centre de messages d’administration, la mise à niveau des messages électroniques vers l’administrateur général et les indicateurs dans l’application aux utilisateurs finaux. 

Ces notifications communiqueront la date prévue de la mise à niveau automatisée, fourniront des liens vers des ressources et des formations de mise à niveau pour contribuer à l’adoption et l’utilisation de Teams, et donneront aux clients la possibilité de différer leur mise à niveau automatique de 30 jours supplémentaires au cas où ils ne se préparez pas à mettre à niveau d’ici la date prévue.

## <a name="the-automated-upgrade-experience"></a>L’expérience de mise à niveau automatisée

Les mises à niveau automatisées s’exécutent à la date de mise à niveau prévue qui est communiquée dans les messages électroniques de notification, le Centre de messages ainsi que le portail d’administration Teams. La mise à niveau prend environ 15 minutes pendant laquelle les utilisateurs finaux auront toujours accès aux fonctionnalités de Skype Entreprise Online. Une fois la mise à niveau terminée et la connexion des utilisateurs de Skype Entreprise Online, les utilisateurs peuvent uniquement utiliser Teams pour la messagerie, les réunions et les appels.

## <a name="the-post-upgrade-experience"></a>L’expérience après la mise à niveau

Une fois votre mise à niveau automatisée terminée, le **mode coexistence** est réglé sur Teams uniquement et ne peut être modifié que par Microsoft dans un autre mode de coexistence. Les administrateurs doivent examiner [les considérations en mode Teams uniquement avant](teams-only-mode-considerations.md) la mise à niveau. Le tableau ci-dessous fournit une vue d’ensemble de l’expérience utilisateur de Teams uniquement.


|  |  |
|---------|---------|
|**Conversation et appel**     | <UL><LI>Tous les appels et conversations sont initiés et reçus dans Teams<LI>Les utilisateurs peuvent interoper (conversation/appel) avec n’importe quel utilisateur Skype Entreprise<LI>Les utilisateurs ne peuvent pas communiquer avec les utilisateurs qui utilisent Skype pour les consommateurs<LI>Les utilisateurs sont redirigés vers Teams s’ils essaient de se connecter à Skype Entreprise      </UL>  |
|**Réunions**     |  <UL><LI>Les utilisateurs programment toutes les nouvelles réunions dans Teams (plug-in remplacé)    </UL>   |
|**Données migrées**     |<UL><LI>Contacts existants de Skype Entreprise, y compris fédérés (mais aucune liste de distribution)<LI>Les réunions Skype Entreprise existantes (tant sur site qu’en ligne) sont converties en réunions Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Report de votre mise à niveau automatisée

La réussite des transitions de Skype Entreprise Online à Microsoft Teams nécessite une planification technique et la préparation des utilisateurs pour s’assurer que votre organisation est prête à tirer parti des fonctionnalités et performances étendues de Teams. Toutefois, comme vous planifiez votre mise à niveau, il est possible que votre organisation ne soit pas encore prête à mettre à niveau vers Teams pour le moment.

Si vous recevez une notification concernant votre mise à niveau automatisée programmée vers Teams et que vous souhaitez reporter à une date ultérieure, l’administrateur global peut se connecter au portail d’administration de Teams et cliquer sur le bouton Différer.  Cette faisant, la date de mise à niveau automatisée sera repoussée de 30 jours. Lorsque vous actualisez le portail d’administration de Teams après le report, une notification incluant votre nouvelle date de mise à niveau automatique s’affiche.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Demandes de rétrogradation vers Skype Entreprise

Nous auto auto autorions des mises à niveau de Teams vers SfBO afin de permettre aux locataires de se préparer davantage à la mise à niveau vers Teams. Les locataires qui ont rétrogradé seront de nouveau engagés pour la mise à niveau automatique 60 jours après leur date de mise à niveau vers une version ultérieure.

## <a name="related-content"></a>Contenu associé

- [Prise en main de votre mise à niveau de Microsoft Teams](upgrade-start-here.md)
- [Déclassement de Skype Entreprise Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considérations relatives au mode Teams uniquement](teams-only-mode-considerations.md)