---
title: Teams mises à jour
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
description: Dans cet article, vous allez découvrir le processus de mise à jour du client Microsoft Teams bureau.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004c615d2b624f4e5942562e6abfed6e1aebf7cd
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717895"
---
# <a name="teams-update-process"></a>Teams de mise à jour

L’Teams Web App est mise à jour chaque semaine.

Teams mises à jour du client de bureau sont publiées toutes les deux semaines après un test interne strict et la validation via notre programme d’adoption des technologies.) La mise à jour a généralement lieu un mardi. Si une mise à jour critique est requise, Teams’ignorera ce planning et publiera la mise à jour dès qu’elle sera disponible.

Le client de bureau se met automatiquement à jour. Teams vérifie les mises à jour toutes les quelques heures en arrière-plan, les télécharge, puis attend que l’ordinateur soit inactif avant d’installer la mise à jour en mode silencieux.

Les utilisateurs peuvent également télécharger  manuellement les mises  à jour en sélectionnant Vérifier les mises à jour dans le menu déroulant Profil dans la partie supérieure droite de l’application. Si une mise à jour est disponible, elle est téléchargée et installée en mode silencieux lorsque l’ordinateur est inactif.

Les utilisateurs doivent être inscrits pour que les mises à jour soient téléchargées.

À compter du 31 juillet 2019, les mises Teams client utilisent une bande passante réseau inférieure pendant la mise à jour. Cette mise à jour est désactivée par défaut et ne nécessite aucune action de la part des administrateurs ou des utilisateurs.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Qu’en est-il des mises à jour Applications Microsoft 365 pour les grandes entreprises ?

Teams est installé par défaut avec de nouvelles installations de l Applications Microsoft 365 pour les grandes entreprises, comme décrit dans La mise en Microsoft Teams [avec Applications Microsoft 365 pour les grandes entreprises.](/DeployOffice/teams-install)

Teams suit son propre processus de mise à jour, comme indiqué ci-dessus. Teams suivez pas le processus de mise à jour pour les autres applications Office, telles que Word et Excel. Pour en savoir plus, consultez la [présentation des canaux de mise à jour pour Applications Microsoft 365 pour les grandes entreprises](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Qu’en est-il des mises à Teams sur VDI ?


Teams clients sur infrastructure VDI (Virtual Desktop Infrastructure) ne sont pas automatiquement mis à jour comme les clients de bureau non VDI Teams automatiques. Vous devez mettre à jour l’image VM en installant un nouvel ID MSI, comme décrit dans les instructions d’installation de [Teams VDI.](teams-for-vdi.md) Vous devez désinstaller la version actuelle pour la mettre à jour vers une version plus récente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Les administrateurs peuvent-ils déployer des mises à jour au lieu Teams mise à jour automatique ?

Teams ne permet pas aux administrateurs de déployer les mises à jour via tout mécanisme de remise.

## <a name="servicing-agreement"></a>Contrat de service

En tant que service en ligne moderne, le client Teams mise à jour automatique du client toutes les deux semaines. Étant Teams la politique de cycle de vie moderne, les utilisateurs doivent rester sur la version la plus à jour du client de bureau. Les mises à jour automatiques garantissent que les utilisateurs ont les fonctionnalités les plus récentes, les améliorations des performances, la sécurité et la fiabilité du service.

Pour identifier le moment où les clients de bureau ne sont plus à jour, une alerte dans l’application s’affiche si la version actuelle de l’utilisateur a entre un et trois mois et si une nouvelle version est disponible. Cette messagerie dans l’application encourage les utilisateurs à mettre à jour vers la dernière version d’Teams ou, si nécessaire, à s’adresser à leur administrateur informatique pour le faire. Les utilisateurs Teams clients de bureau de plus de trois mois voient une page de blocage qui leur permet d’accéder à la mise à jour dès maintenant, de consulter leur administrateur informatique ou de continuer à Teams sur le web.

Teams clients de bureau sur Government Clouds ont actuellement une exception au présent contrat de service jusqu’à nouvel ordre.

Pour plus d’informations sur les nouvelles versions, consultez le Centre de [messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) ou consultez l’aide sur les  >  **nouveautés** dans le client.
