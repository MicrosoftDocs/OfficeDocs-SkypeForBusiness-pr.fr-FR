---
title: Processus de mise à jour des équipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Découvrez comment le client de bureau équipes est mis à jour.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08381341903d21deb42ca83b3769c49f67d18b14
ms.sourcegitcommit: 2449c6dbda4a63aefe5291558cfa41ad7ccf9e39
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970275"
---
# <a name="teams-update-process"></a>Processus de mise à jour des équipes

L’application web équipes est mis à jour toutes les semaines.

Les équipes client de bureau sont mises à jour toutes les deux semaines après rigoureux interne et la validation par le biais de notre programme TAP (Technology Adoption). Cela est généralement réalisée un mardi. Si une mise à jour critique est requise, les équipes seront contourner cette planification et version de la mise à jour dès qu’elle est disponible.

Le client de bureau se met à jour automatiquement. Vérifie les équipes met à jour toutes les quelques heures en arrière-plan, télécharge et puis attend que l’ordinateur doit être inactif avant la mise à jour en mode silencieux.

Les utilisateurs peuvent télécharger manuellement les mises à jour en cliquant sur **vérifier les mises à jour** dans le menu déroulant **profil** sur la partie supérieure droite de l’application. Si une mise à jour est disponible, il sera téléchargé et installé en mode silencieux lorsque l’ordinateur est inactif.

Les utilisateurs doivent être connectés les mises à jour à télécharger.

## <a name="what-about-updates-to-office-365-proplus"></a>Qu’advient-il des mises à jour pour Office 365 ProPlus ?

Les équipes est installé par défaut avec les nouvelles installations d’Office 365 ProPlus, comme décrit dans [Déployer les équipes Microsoft Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

Les équipes suit son propre processus de mise à jour, comme indiqué ci-dessus et non le processus de mise à jour pour les autres applications de bureaux, telles que Word et Excel.

## <a name="what-about-updates-to-teams-on-vdi"></a>Qu’advient-il des mises à jour des équipes sur VDI ?

Clients équipes sur l’Infrastructure VDI (Virtual Desktop) ne sont pas automatiquement mis à jour la façon dont les clients non - VDI équipes. Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau fichier MSI, comme décrit dans les instructions pour [Installer les équipes sur VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Vous devez désinstaller la version actuelle de mise à jour vers une version plus récente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Administrateurs peuvent déployer des mises à jour au lieu des équipes de mise à jour automatique ?

Les équipes ne donne pas d’administrateurs de déployer des mises à jour par le biais de tout mécanisme de livraison.
