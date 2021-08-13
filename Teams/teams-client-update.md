---
title: Mises à jour de Teams
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
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 96077e5b50dff12f29f6e1ccf903cd0f7de96352dacf0d8b3c2cc7406750737e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321136"
---
# <a name="teams-update-process"></a>Processus de mise à jour de Teams

L’application web Teams est mise à jour chaque semaine.

Les mises à jour du client de bureau Teams sont publiées toutes les deux semaines après des tests et validations internes rigoureux via notre programme d’adoption des technologies (TAP). La mise à jour a généralement lieu un mardi. Si une mise à jour critique est requise, Teams contourne ce planning et publie la mise à jour dès que celle-ci est disponible.

Le client de bureau se met à jour automatiquement. Teams recherche les mises à jour toutes les quelques heures en arrière-plan, les télécharge, puis attend que l’ordinateur soit inactif avant d’installer la mise à jour en mode silencieux.

Les utilisateurs peuvent également télécharger manuellement les mises à jour en sélectionnant **Rechercher les mises à jour** dans le menu déroulant **Profil** en haut à droite de l’application. Si une mise à jour est disponible, elle est téléchargée et installée en mode silencieux lorsque l’ordinateur est inactif.

Les utilisateurs doivent être connectés pour que les mises à jour soient téléchargées.

À compter du 31 juillet 2019, les mises à jour du client Teams utilisent une bande passante réseau inférieure pendant la mise à jour. Cette mise à jour est activée par défaut et ne nécessite aucune action de la part des administrateurs ou des utilisateurs.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Qu’en est-il des mises à jour des applications Microsoft 365 pour les entreprises ?

Teams est installé par défaut avec de nouvelles installations de Microsoft 365 Apps for enterprise, comme décrit dans [Déployer Microsoft Teams avec Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).

Teams suit son propre processus de mise à jour, comme indiqué ci-dessus. Teams ne suit pas le processus de mise à jour pour les autres applications Office, telles que Word et Excel. Pour en savoir plus, consultez [Vue d’ensemble des canaux de mise à jour pour Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus).

## <a name="what-about-updates-to-teams-on-vdi"></a>Qu’en est-il des mises à jour de Teams sur VDI ?


Les clients Teams sur une infrastructure VDI (Virtual Desktop Infrastructure) ne sont pas automatiquement mis à jour de la même façon que les clients Teams non VDI. Vous devez mettre à jour l’image de machine virtuelle en installant une nouvelle identité MSI comme décrit dans les instructions pour [Installer Teams sur VDI](teams-for-vdi.md). Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Les administrateurs peuvent-ils déployer des mises à jour au lieu de la mise à jour automatique Teams ?

Teams n’offre pas aux administrateurs la possibilité de déployer des mises à jour par le biais d’un mécanisme de distribution.

## <a name="servicing-agreement"></a>Contrat de maintenance

En tant que service en ligne moderne, le client Teams se met à jour automatiquement toutes les deux semaines. Étant donné que Teams est régi par la politique de cycle de vie moderne, il est prévu que les utilisateurs restent sur la version la plus récente du client de bureau. Les mises à jour automatiques garantissent que les utilisateurs disposent des dernières fonctionnalités, améliorations des performances, sécurité et fiabilité des services.

Pour identifier le moment où les clients de bureau sont obsolètes, une alerte dans l’application s’affiche si la version actuelle de l’utilisateur a entre un et trois mois, et s’il existe une nouvelle version disponible. Cette messagerie dans l’application encourage les utilisateurs à effectuer une mise à jour vers la dernière version de Teams ou, si nécessaire, à contacter leur administrateur informatique pour ce faire. Les utilisateurs sur les clients de bureau Teams qui ont plus de trois mois voient une page de blocage qui donne les options de mise à jour maintenant, de contacter leur administrateur informatique ou de continuer à utiliser Teams sur le web.

Les clients de bureau Teams sur les clouds publics ont actuellement une exception à ce contrat de maintenance jusqu’à nouvel ordre.

Pour plus d’informations sur les nouvelles versions, consultez [Centre de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) ou accédez à **Aide** > **les nouveautés** dans le client.
