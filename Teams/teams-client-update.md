---
title: Mises à jour teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Dans cet article, vous allez découvrir le processus de mise à jour du client de bureau Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119243"
---
# <a name="teams-update-process"></a>Processus de mise à jour de Teams

L’application web Teams est mise à jour chaque semaine.

Les mises à jour du client de bureau Teams sont publiées toutes les deux semaines après un test interne strict et la validation via notre programme d’adoption des technologies (TAP). La mise à jour a généralement lieu un mardi. Si une mise à jour critique est requise, Teams contourne ce planning et publie la mise à jour dès qu’elle est disponible.

Le client de bureau se met automatiquement à jour. Teams vérifie les mises à jour toutes les quelques heures en arrière-plan, les télécharge, puis attend que l’ordinateur soit inactif avant d’installer la mise à jour en mode silencieux.

Les utilisateurs peuvent également télécharger  manuellement les mises  à jour en sélectionnant Vérifier les mises à jour dans le menu déroulant Profil dans la partie supérieure droite de l’application. Si une mise à jour est disponible, elle est téléchargée et installée en mode silencieux lorsque l’ordinateur est inactif.

Les utilisateurs doivent être inscrits pour que les mises à jour soient téléchargées.

À compter du 31 juillet 2019, les mises à jour du client Teams utilisent une bande passante réseau inférieure pendant la mise à jour. Cette mise à jour est désactivée par défaut et ne nécessite aucune action de la part des administrateurs ou des utilisateurs.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Qu’en est-il des mises à jour des applications Microsoft 365 pour les entreprises ?

Teams est installé par défaut avec de nouvelles installations des applications Microsoft 365 pour les entreprises, comme décrit dans Déployer Microsoft Teams avec les applications [Microsoft 365 pour les entreprises.](/DeployOffice/teams-install)

Teams suit son propre processus de mise à jour, comme indiqué ci-dessus. Teams ne suit pas le processus de mise à jour pour les autres applications Office, telles que Word et Excel. Pour en savoir plus, consultez [la présentation des canaux de mise à jour pour les applications Microsoft 365 pour les entreprises](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Qu’en est-il des mises à jour de Teams sur VDI ?


Les clients Teams sur infrastructure VDI (Virtual Desktop Infrastructure) ne sont pas automatiquement mis à jour comme les clients Teams non VDI. Vous devez mettre à jour l’image VM en installant un nouveau MSI, comme décrit dans les instructions d’installation de [Teams sur VDI.](teams-for-vdi.md) Vous devez désinstaller la version actuelle pour la mettre à jour vers une version plus récente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Les administrateurs peuvent-ils déployer des mises à jour au lieu de la mise à jour automatique de Teams ?

Teams ne permet pas aux administrateurs de déployer les mises à jour via n’importe quel mécanisme de remise.

## <a name="servicing-agreement"></a>Contrat de service

En tant que service en ligne moderne, le client Teams se met à jour automatiquement toutes les deux semaines. Teams étant régi par la stratégie de cycle de vie moderne, les utilisateurs doivent rester sur la version la plus récente du client de bureau. Les mises à jour automatiques garantissent que les utilisateurs ont les fonctionnalités les plus récentes, les améliorations des performances, la sécurité et la fiabilité du service.

Pour identifier le moment où les clients de bureau ne sont plus à jour, une alerte dans l’application s’affiche si la version actuelle de l’utilisateur a entre un et trois mois et si une nouvelle version est disponible. Cette messagerie dans l’application encourage les utilisateurs à mettre à jour vers la dernière version de Teams ou, si nécessaire, à s’adresse à leur administrateur informatique pour le faire. Les utilisateurs de clients de bureau Teams de plus de trois mois voient une page de blocage qui propose des options de mise à jour dès maintenant, de consulter leur administrateur informatique ou de continuer à accéder à Teams sur le web.

Les versions du client de bureau de plus de trois mois à la première installation et/ou première version de Teams ont une période de grâce de 28 jours avant de rencontrer les informations de service ci-dessus. Pendant cette période, le processus de mise à jour automatique met à jour le client Teams. S’il n’y a pas de mise à jour, les utilisateurs voient une alerte dans l’application les inciter à se mettre à jour manuellement vers la dernière version de Teams. Les utilisateurs peuvent être invités à contacter leur administrateur informatique pour faire la mise à jour. Cela inclut les utilisateurs qui utilisent le client de bureau Teams dans le cadre de l’offre groupée Applications Microsoft 365 pour les entreprises.

Les clients de bureau Teams sur les nuages gouvernementaux ont actuellement une exception au présent contrat de service jusqu’à nouvel ordre.

Pour plus d’informations sur les nouvelles versions, consultez le Centre de [messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) ou consultez l’aide sur les  >  **nouveautés** dans le client.
