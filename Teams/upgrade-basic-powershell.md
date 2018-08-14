---
title: Mise à niveau des commandes PowerShell base - Microsoft Teams
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisoires pour la mise à niveau vers les équipes si le centre d’administration n’a pas activée dans votre client
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b65cd7a7b9ef91194b2045193a98672bfd25326
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001718"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Mettre à niveau vos utilisateurs Skype pour Business Online vers Microsoft Teams

> [!Note]
> Les commandes décrites dans cet article sont conçus pour être utilisés dans le cadre de la liste de contrôle [De mise à niveau de base](https://aka.ms/UpgradeBasic) .

Les aspects techniques de migration de votre mise à niveau en avertir les utilisateurs que Skype pour les entreprises sera mise à niveau vers les équipes et puis en les déplaçant vers un mode **d’équipes uniquement** . Ces étapes peuvent être effectuées via un Skype pour la session Windows PowerShell à distance Business ou par le biais du Microsoft Teams & Skype entreprise centre d’administration. 
 
Nous allons présentant activement mise à niveau d’outils dans les [équipes Microsoft & Skype entreprise centre d’administration](manage-teams-skypeforbusiness-admin-center.md)et il doit être disponible prochainement sur votre client. Dès qu’elle est disponible, vous trouverez des informations sur la migration de vos utilisateurs dans la [définition de votre coexistence et les paramètres de mise à niveau](https://aka.ms/SkypeToTeams-SetCoexistence). 
 
Si vous êtes prêt à mettre à niveau dès aujourd'hui, vous pouvez utiliser les commandes [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) répertoriés dans le tableau suivant. 
 
 |Mise à niveau de base étape # | Mode | Commande PowerShell |
|-------|--------|------|
| [5](upgrade-basic.md#step-5) |Îles + avertir le Skype pour l’utilisateur d’entreprise<br>(Utilisez cette commande si des utilisateurs sont actuellement en mode **(îles)** (par défaut)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>_(par exemple, $SipAddress = 'TestUser@contoso.com')_<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5)  | Skype pour les entreprises uniquement + avertir le Skype pour l’utilisateur d’entreprise <br>(Utilisez cette commande si des utilisateurs sont actuellement en mode **Skype pour les entreprises uniquement** ) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Équipes uniquement | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


