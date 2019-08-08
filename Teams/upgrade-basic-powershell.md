---
title: PowerShell de mise à niveau de base | Microsoft teams | Accorder une stratégie d’interopérabilité de mise à niveau
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Stopgap pour la mise à niveau vers teams si le centre d’administration ne s’est pas allumé dans votre client
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 945422f6bb61fca8d2b17379a7c9bf4695e7dd09
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236540"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Mise à niveau de vos utilisateurs de Skype entreprise Online vers Microsoft teams

> [!Note]
> Les commandes décrites dans cet article sont conçues pour être utilisées dans le cadre de la liste de vérification de base de la [mise à niveau](https://aka.ms/UpgradeBasic) .

Les aspects de migration techniques de votre mise à niveau impliquent de notifier vos utilisateurs de la mise à niveau vers teams de Skype entreprise, puis de les déplacer vers le mode **équipes uniquement** . Ces étapes peuvent être effectuées par le biais d’une session Windows PowerShell distante Skype entreprise ou du centre d’administration Microsoft Teams.

Le déploiement des outils de mise à niveau dans le [Centre d’administration de Microsoft teams](manage-teams-skypeforbusiness-admin-center.md), nous vous conseillons de le faire bientôt sur votre client. Dès qu’il est disponible, vous pouvez trouver des informations sur la migration de vos utilisateurs dans le cadre de [la configuration de votre coexistence et de vos paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence).

Si vous êtes prêt à effectuer la mise à niveau vers la version actuelle, vous pouvez utiliser les commandes [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriées dans le tableau suivant.

| Étape de mise à niveau de base # | Veille | Commande PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Îles + informer l’utilisateur de Skype entreprise<br>(Utilisez cette commande si les utilisateurs sont actuellement en mode **îlot** (par défaut)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(par exemple, $SipAddress = 'TestUser@contoso.com')*<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5) | Skype entreprise uniquement + informer l’utilisateur de Skype entreprise <br>(Utilisez cette commande si les utilisateurs sont actuellement en mode **Skype entreprise uniquement** ) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Équipes uniquement | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
