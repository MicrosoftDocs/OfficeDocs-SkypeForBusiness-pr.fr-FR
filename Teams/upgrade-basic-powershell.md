---
title: Mise à niveau de base de PowerShell| Microsoft Teams| Accorder une stratégie Interop de mise à niveau
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez un stopgap pour la mise à niveau vers Microsoft Teams’administration si le Centre d’administration n’est pas allumé dans votre client.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a281a835240db1ee61959e468eb868e833878f16
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762942"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Mise à niveau de vos utilisateurs de Skype Entreprise Online vers Microsoft Teams

> [!Note]
> Les commandes décrites dans cet article sont conçues pour être utilisées dans le cadre de la liste de contrôle [Mise à](./upgrade-start-here.md) niveau de base.

Les aspects de la migration technique de votre mise à niveau impliquent d’informer vos utilisateurs que Skype Entreprise va mettre à niveau vers Teams puis les déplacer vers un **mode** Teams seul. Ces étapes peuvent être réalisées via une session Skype Entreprise’administration Windows PowerShell distance ou via le Microsoft Teams d’administration.

Nous travaillons activement au déploiement des [](manage-teams-skypeforbusiness-admin-center.md)outils de mise à niveau dans le Microsoft Teams d’administration, qui doivent bientôt être disponibles sur votre client. Dès qu’elle est disponible, vous trouverez des informations sur la migration de vos utilisateurs dans La définition de vos paramètres de coexistence et de mise [à niveau.](./setting-your-coexistence-and-upgrade-settings.md)

Si vous êtes prêt à mettre à niveau dès aujourd’hui, vous pouvez utiliser les commandes [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriées dans le tableau suivant.

| Étape de base de la mise à niveau # | Mode | Commande PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + Notify the Skype Entreprise User<br>(Utilisez cette commande si les utilisateurs sont actuellement en mode **Îles** (par défaut)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(par exemple, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype Entreprise + Informer l’utilisateur Skype Entreprise’utilisateur <br>(Utilisez cette commande si les utilisateurs sont actuellement en **Skype Entreprise** mode uniquement) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Uniquement | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |