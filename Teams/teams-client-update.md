---
title: Mises à jour de teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
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
ms.openlocfilehash: e0fe542c6df89946ad73f14cf9104f973e292aa3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243841"
---
# <a name="teams-update-process"></a>Processus de mise à jour des équipes

Team Web App est mis à jour chaque semaine.

Les mises à jour du client de bureau teams sont divulguées toutes les deux semaines après un test interne rigoureux et une validation par le biais de notre programme d’adoption de technologie (TAP). Cette opération est généralement effectuée sur un mardi. Si une mise à jour critique est requise, teams ignorera ce planning et libérera la mise à jour dès qu’il sera disponible.

Le client de bureau est mis à jour automatiquement. Teams vérifie les mises à jour toutes les heures en coulisse, télécharge, puis attend que l’ordinateur soit inactif avant d’installer la mise à jour en silence.

Les utilisateurs peuvent également télécharger manuellement les mises à jour en cliquant sur **Rechercher les mises à jour** dans le menu déroulant **Profil** en haut à droite de l’application. Si une mise à jour est disponible, elle est téléchargée et installée en silence lorsque l’ordinateur est inactif.

Les utilisateurs doivent être connectés pour pouvoir télécharger les mises à jour. 

À compter du 9 juillet, 2019, les mises à jour du client teams utilisent une bande passante réseau nettement inférieure au cours de la mise à jour. Cette option est activée par défaut et ne nécessite aucune action de la part des administrateurs ou des utilisateurs.


## <a name="what-about-updates-to-office-365-proplus"></a>À propos des mises à jour d’Office 365 ProPlus

Teams est installé par défaut avec les nouvelles installations d’Office 365 ProPlus, comme décrit dans la rubrique [déploiement de Microsoft teams avec Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

Teams suit son propre processus de mise à jour, tel que décrit ci-dessus, mais pas le processus de mise à jour des autres applications Office, telles que Word et Excel. Pour en savoir plus, voir [Présentation des canaux de mise à jour d’Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>À propos des mises à jour apportées aux équipes sur VDI

Les clients teams de l’infrastructure de bureau virtuel (VDI) ne sont pas automatiquement mis à jour de manière à ce qu’ils soient. Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau MSI comme décrit dans les instructions d' [installation d’teams sur VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Les administrateurs peuvent-ils déployer des mises à jour au lieu de la mise à jour automatique des équipes?

Teams ne donne pas aux administrateurs la possibilité de déployer des mises à jour par le biais d’un mécanisme de remise.
