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
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: c46f0718bd0bcf0d18cc47d2f8fc68f0ae7792e7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012280"
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


