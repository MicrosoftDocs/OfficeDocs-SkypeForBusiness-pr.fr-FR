---
title: Mises à jour de teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Découvrez les mises à jour du client de bureau Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba6201d0f1b52b7ebfd869ad699c2eb06eb664d8
ms.sourcegitcommit: 0d7f3c7a84584ec25a23190187215109c8756189
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37508799"
---
# <a name="teams-update-process"></a>Processus de mise à jour des équipes

Team Web App est mis à jour chaque semaine.

Les mises à jour du client de bureau teams sont divulguées toutes les deux semaines après un test interne rigoureux et une validation par le biais de notre programme d’adoption de technologie (TAP). Cette opération est généralement effectuée sur un mardi. Si une mise à jour critique est requise, teams ignorera ce planning et libérera la mise à jour dès qu’il sera disponible.

Le client de bureau est mis à jour automatiquement. Teams vérifie les mises à jour toutes les heures en coulisse, télécharge, puis attend que l’ordinateur soit inactif avant d’installer la mise à jour en silence.

Les utilisateurs peuvent également télécharger manuellement les mises à jour en cliquant sur **Rechercher les mises à jour** dans le menu déroulant **Profil** en haut à droite de l’application. Si une mise à jour est disponible, elle est téléchargée et installée en silence lorsque l’ordinateur est inactif.

Les utilisateurs doivent être connectés pour pouvoir télécharger les mises à jour. 

À compter du 31 juillet, 2019, les mises à jour du client teams utilisent une bande passante réseau nettement inférieure lors de la mise à jour. Cette option est activée par défaut et ne nécessite aucune action de la part des administrateurs ou des utilisateurs.

## <a name="what-about-updates-to-office-365-proplus"></a>À propos des mises à jour d’Office 365 ProPlus

Teams est installé par défaut avec les nouvelles installations d’Office 365 ProPlus, comme décrit dans la rubrique [déploiement de Microsoft teams avec Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

Teams suit son propre processus de mise à jour, tel que décrit ci-dessus, mais pas le processus de mise à jour des autres applications Office, telles que Word et Excel. Pour en savoir plus, voir [Présentation des canaux de mise à jour d’Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>À propos des mises à jour apportées aux équipes sur VDI

Les clients teams de l’infrastructure de bureau virtuel (VDI) ne sont pas automatiquement mis à jour de manière à ce qu’ils soient. Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau MSI comme décrit dans les instructions d' [installation d’teams sur VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Les administrateurs peuvent-ils déployer des mises à jour au lieu de la mise à jour automatique des équipes ?

Teams ne donne pas aux administrateurs la possibilité de déployer des mises à jour par le biais d’un mécanisme de remise.

## <a name="servicing-agreement"></a>Contrat de service

En tant que service en ligne moderne, le client teams se met à jour automatiquement toutes les deux semaines. Les équipes étant régies par la politique de cycle de vie moderne, il est probable que les utilisateurs restent dans la version la plus à jour du client de bureau. Cela permet aux utilisateurs de bénéficier des dernières fonctionnalités, des améliorations des performances, de la sécurité et de la fiabilité des services.

Pour vous aider à identifier le moment où les clients de bureau sont obsolètes, une alerte dans l’application s’affiche si la version actuelle de l’utilisateur est située entre 1 et 3 mois et si une nouvelle version est disponible. Ce message in-app encourage les utilisateurs à effectuer une mise à jour vers la version la plus récente d’teams ou, si nécessaire, à communiquer à leur administrateur informatique. Les utilisateurs des clients de bureau teams de plus de trois mois voient s’afficher une page de blocage qui vous permet d’accéder aux options de mise à jour, de communiquer à leur administrateur ou de continuer à utiliser teams sur le Web.

Les versions de client de bureau âgées de plus de trois mois lors de la première installation et/ou de la première série d’équipes disposent d’une période de grâce de 28 jours avant d’appliquer les informations de maintenance mentionnées ci-dessus. Pendant cette période, le processus de mise à jour automatique met à jour le client Teams. Si ce n’est pas le cas, les utilisateurs verront une alerte dans l’application afin de leur permettre de procéder manuellement à la mise à jour de la version la plus récente d’une équipe ou, le cas échéant, à leur administrateur. Cela inclut les utilisateurs qui utilisent le client de bureau teams dans le cadre de l’offre Office 365 ProPlus.

Pour le moment, les clients de bureau teams sur les clouds gouvernementaux ont une exception à ce contrat de service.

Pour plus d’informations sur**les** nouvelles versions, consultez le [Centre de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) ou accédez à **aide** > sur les nouveautés du client.
