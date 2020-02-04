---
title: Parcage et récupération d’appel dans Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.callparkpolicies.overview
ms.custom:
- Phone System
description: Utiliser le parc d’appels et la récupération pour mettre un appel en attente dans le service équipes du Cloud.
ms.openlocfilehash: 4bd77fcd90cb17f0ca5b09f784d6532d552df473
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695619"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parcage et récupération d’appel dans Microsoft Teams

Le parc et la récupération des appels est une fonctionnalité qui permet à un utilisateur de mettre un appel en attente dans le service équipes du Cloud. Lorsqu’un appel est parqué, le service génère un code unique pour la récupération des appels. L’utilisateur qui a parqué l’appel ou quelqu’un d’autre peut alors utiliser ce code et une application ou un appareil pris en charge pour récupérer l’appel. 

Voici quelques-uns des scénarios les plus courants d’utilisation du parc d’appel : 

- Un réceptionniste est un appel pour une personne qui travaille dans une fabrique. La réceptionniste annonce ensuite l’appel et le numéro de code sur le système d’adresses publiques. L’utilisateur pour lequel l’appel est destiné peut alors décrocher un téléphone d’équipe sur le plancher et entrer le code permettant de récupérer l’appel.
- Un utilisateur a un appel sur un appareil mobile, car la batterie de l’appareil est épuisée. L’utilisateur peut ensuite entrer le code permettant de récupérer l’appel à partir d’un téléphone de bureau Teams.
- Un représentant du support technique Centre un appel client et envoie une annonce à un canal d’équipe pour permettre à un expert de récupérer l’appel et d’aider le client. Un expert entre le code dans les clients teams pour récupérer l’appel

> [!IMPORTANT]
> Cette fonctionnalité n’est disponible que dans le mode déploiement d’équipes. Pour plus d’informations sur les modes de déploiement d’équipes, voir comprendre les modes de déploiement de [Microsoft teams et de Skype entreprise et l’interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Pour parcer et récupérer des appels, l’utilisateur doit être un utilisateur d’entreprise voix et un administrateur doit lui accorder une stratégie de parc d’appels. Pour plus d’informations sur le modèle de gestion des licences, voir gestion [des licences Office 365 pour Microsoft teams](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Parc d’appels et récupération de la disponibilité des fonctionnalités

Le parc et la récupération des appels sont actuellement pris en charge par les clients et appareils suivants. (Pris en charge en mode équipes uniquement, avec ou sans connectivité PSTN.)

| Faculté | Bureau teams | Application Mac teams | Team Web App (Edge) |Application mobile iOS/Android teams | Téléphone IP teams | Téléphone IP Skype entreprise |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Parc d’un appel | Oui | Oui | Oui | Oui | Bientôt disponible| Non |
| Extraire un appel parqué | Oui | Oui | Oui | Oui | Bientôt disponible| Non |
| Retour de la sonnerie des appels annulé | Oui | Oui | Oui | Oui | Bientôt disponible| Non |

## <a name="configuring-call-park-and-retrieve"></a>Configuration du parc et de la récupération des appels

Vous devez être administrateur pour configurer le parc d’appels et la récupération, et la fonctionnalité est désactivée par défaut. Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels. Lorsque vous appliquez la même politique à un ensemble d’utilisateurs, ces derniers peuvent se parcer et récupérer les appels entre eux. Pour configurer le parc d’appels pour les utilisateurs et créer des groupes d’utilisateurs de parc d’appels, suivez la procédure [assigner une stratégie de parc d’appels](#assign-a-call-park-policy) ci-dessous.

Pour plus d’informations sur l’utilisation de la fonctionnalité de parc et de récupération d’appel, voir [Park a Call in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Activer une stratégie de parc d’appels

Pour activer une stratégie de parc d’appels, procédez comme suit :

1. Accédez**** > **** au > Centre d' **administration Microsoft teams**.
2. Sélectionnez **nouvelle stratégie**.
3. Attribuez un nom à la stratégie, puis basculez **autoriser le parc d’appels** sur **activé**.
4. Sélectionnez **Save (enregistrer**).

### <a name="assign-a-call-park-policy"></a>Assigner une stratégie de parc d’appels

Pour attribuer une stratégie de parc d’appels à un ou plusieurs utilisateurs, procédez comme suit :

1. Accédez**** > **** au > Centre d' **administration Microsoft teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurer le parc d’appels et récupérer avec PowerShell

Utilisez l’applet de cmdlet PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) pour créer une stratégie de parc d’appels.

Utilisez l’applet de passe PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) pour accorder une stratégie de parc d’appels.

Vous pouvez modifier le paramètre par défaut en utilisant [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) comme suit :

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Résolution des problèmes

Si les utilisateurs ne peuvent pas voir le bouton parc ou récupérer : 

- Vérifiez que la stratégie de parc d’appels est activée pour l’utilisateur. 

Si un utilisateur tente de récupérer un appel et échoue, vérifiez les points suivants :

- Vérifier que l’utilisateur utilise le client teams ou un appareil/téléphone compatible teams
- Regroupement : il s’agit de l’utilisateur membre du groupe de parc d’appels, qui est basé sur le fait que la même stratégie de parc d’appels d’équipes est affectée. 
- Mode île : le parc d’appels et la récupération ne sont pas disponibles en mode îlot d’équipe.
- L’appel a déjà été récupéré ou arrêté.

## <a name="more-information"></a>Plus d’informations

[Parcez un appel dans teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).
