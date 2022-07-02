---
title: Mise à niveau de base de PowerShell| Microsoft Teams| Accorder une stratégie d’interopérabilité de mise à niveau
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez un stopgap pour la mise à niveau vers Microsoft Teams si le centre Administration n’a pas été allumé dans votre locataire.
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606033"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Mise à niveau de vos utilisateurs de Skype Entreprise Online vers Microsoft Teams

> [!Note]
> Les commandes décrites dans cet article sont conçues pour être utilisées dans le cadre de la liste de contrôle [Upgrade Basic](./upgrade-start-here.md) .

Les aspects de la migration technique de votre mise à niveau impliquent d’informer vos utilisateurs que Skype Entreprise seront mis à niveau vers Teams, puis de les déplacer vers un mode **Teams uniquement**. Ces étapes peuvent être effectuées via une Skype Entreprise session Windows PowerShell distante ou par le biais du Centre d’administration Microsoft Teams.

Nous déployons activement des outils de mise à niveau dans le [Centre d’administration Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md), et il devrait être bientôt disponible sur votre locataire. Dès qu’elle est disponible, vous trouverez des informations sur la migration de vos utilisateurs dans [Définir vos paramètres de coexistence et de mise à niveau](./setting-your-coexistence-and-upgrade-settings.md).

Si vous êtes prêt à effectuer une mise à niveau aujourd’hui, vous pouvez utiliser les commandes [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriées dans le tableau suivant.

| Étape de mise à niveau de base # | Mode | Commande PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Îles + Avertir l’utilisateur Skype Entreprise<br>(Utilisez cette commande si les utilisateurs sont actuellement en mode **Îles** (par défaut)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(par exemple, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype Entreprise uniquement + Notifier l’utilisateur Skype Entreprise <br>(Utilisez cette commande si les utilisateurs sont actuellement en **mode Skype Entreprise uniquement**) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams uniquement | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |