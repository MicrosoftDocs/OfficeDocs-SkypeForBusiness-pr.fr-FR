---
title: Base PowerShell mise à niveau | Les équipes Microsoft | Stratégie de mise à niveau Grant interopérabilité
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisoires pour la mise à niveau vers les équipes si le centre d’administration n’a pas activée dans votre client
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f81e796d893ef17138398c8a5739a4284bcfc4a3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459739"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Mettre à niveau vos utilisateurs Skype pour Business Online vers Microsoft Teams

> [!Note]
> Les commandes décrites dans cet article sont conçus pour être utilisés dans le cadre de la liste de contrôle [De mise à niveau de base](https://aka.ms/UpgradeBasic) .

Les aspects techniques de migration de votre mise à niveau en avertir les utilisateurs que Skype pour les entreprises sera mise à niveau vers les équipes et puis en les déplaçant vers un mode **d’équipes uniquement** . Ces étapes peuvent être accomplies via un Skype pour la session Windows PowerShell à distance Business ou via le centre d’administration Microsoft Teams.

Nous allons présentant activement mise à niveau d’outils dans le [Centre d’administration de Microsoft équipes](manage-teams-skypeforbusiness-admin-center.md), et il doit être disponible prochainement sur votre client. Dès qu’elle est disponible, vous trouverez des informations sur la migration de vos utilisateurs dans la [définition de votre coexistence et les paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).

Si vous êtes prêt à mettre à niveau dès aujourd'hui, vous pouvez utiliser les commandes [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriés dans le tableau suivant.

| Mise à niveau de base étape # | Mode | Commande PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Îles + avertir le Skype pour l’utilisateur d’entreprise<br>(Utilisez cette commande si des utilisateurs sont actuellement en mode **(îles)** (par défaut)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(par exemple, $SipAddress = 'TestUser@contoso.com')*<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5) | Skype pour les entreprises uniquement + avertir le Skype pour l’utilisateur d’entreprise <br>(Utilisez cette commande si des utilisateurs sont actuellement en mode **Skype pour les entreprises uniquement** ) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Équipes uniquement | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |