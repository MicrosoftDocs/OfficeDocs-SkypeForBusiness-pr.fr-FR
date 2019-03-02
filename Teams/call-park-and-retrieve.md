---
title: Parcage et récupération d’appel dans Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Utilisez parcage d’appel et de récupération pour passer un appel en attente dans le service d’équipes dans le nuage.
ms.openlocfilehash: 48052768ce172fda88b3e034277c4454988b32db
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353473"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parcage et récupération d’appel dans Microsoft Teams

Mise en garde d’appels et de récupération est une fonctionnalité qui permet à un utilisateur de passer un appel en attente dans le service d’équipes dans le nuage. Lors de la mise en garde un appel, le service génère un code unique pour la récupération de l’appel. L’utilisateur qui a été mis en garde l’appel ou une autre personne peut ensuite utiliser ce code et une applications pris en charge ou périphérique pour récupérer l’appel. 

Les scénarios courants d’utilisation de parcage d’appel sont les suivants : 

- Un réceptionniste parcs élevage un appel d’une personne travaillant dans une fabrique. Le réceptionniste annonce puis l’appel et le numéro de code dans le système. L’utilisateur pour l’appel peut sélectionner un téléphone équipes en usine, puis entrez le code pour récupérer l’appel.
- Un utilisateur parcs élevage un appel sur un appareil mobile, car la batterie de l’appareil manque d’alimentation. L’utilisateur peut entrer puis de code pour récupérer l’appel à partir d’un téléphone de bureau équipes.
- Un parcs représentant prise en charge un client d’appel et envoie une annonce sur un canal d’équipes pour récupérer l’appel et aider le client à un expert. Un expert entre le code dans les clients des équipes pour récupérer l’appel

> [!IMPORTANT]
> Cette fonctionnalité est uniquement disponible en mode de déploiement équipes uniquement. Pour plus d’informations sur les modes de déploiement d’équipes, voir [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Pour mettre en garde et récupérer des appels, l’utilisateur doit être un utilisateur Enterprise Voice et un administrateur doit accorder à l’utilisateur une stratégie de parcage d’appel. Pour plus d’informations sur le modèle de licence, voir [Gestion des licences Office 365 pour les équipes Microsoft](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Le parcage d’appel et de récupérer la disponibilité des fonctionnalités

Parcage d’appel et de récupérer est actuellement pris en charge par les périphériques clients suivants. (Pris en charge en mode équipes uniquement, avec ou sans connectivité PSTN).

| Fonctionnalité | Bureau des équipes | Les équipes Mac application | Les équipes Web App (périmètre) |Les équipes mobile iOS/Android application | Téléphone IP d’équipes | Skype pour téléphone IP d’entreprise |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Mise en garde d’un appel | Oui | Oui | Oui | Oui | Bientôt disponible| Non |
| Récupérer un appel mis en garde | Oui | Oui | Oui | Oui | Bientôt disponible| Non |
| Sonnerie d’appel non récupérées précédent | Oui | Oui | Oui | Oui | Bientôt disponible| Non |

## <a name="configuring-call-park-and-retrieve"></a>Configuration de mise en garde d’appels et de récupération

Vous devez être un administrateur de configurer la mise en garde d’appels et de récupération, et la fonctionnalité est désactivée par défaut. Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parcage d’appel. Lorsque vous appliquez la même stratégie à un ensemble d’utilisateurs, ils seront en mesure de mettre en garde et récupérer des appels entre eux. Pour configurer la mise en garde d’appels pour les utilisateurs et créer des groupes d’utilisateurs appel park, suivez la procédure ci-dessous.

Pour plus d’informations sur la façon d’utiliser la mise en garde d’appels et de récupérer la fonctionnalité, voir [mise en garde d’un appel en équipe](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurer la mise en garde d’appels et récupérer l’aide de PowerShell

Utilisez l’applet de commande PowerShell [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) pour créer une stratégie de parcage d’appel.

Utilisez l’applet de commande PowerShell [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) pour accorder une stratégie de parcage d’appel.

Vous pouvez modifier le paramètre par défaut à l’aide de [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) comme suit :

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Résolution des problèmes

Si les utilisateurs ne peuvent pas voir le parc ou récupérer le bouton : 

- Vérifiez que l’utilisateur dispose de la stratégie de parcage d’appel activée. 

Si un utilisateur tente de récupérer un appel échoue, vérifiez les points suivants :

- Vérifiez que l’utilisateur utilise le client équipes ou un téléphone/appareil prenant en charge les équipes
- Regroupement – est l’utilisateur membre du groupe de parcage d’appel ?
- Mode (îles) – mise en garde d’appels et de récupération n’est pas disponible en mode îlot d’équipes.
- L’appel a déjà été récupéré ou interrompue.

## <a name="more-information"></a>Plus d’informations

[Mise en garde d’un appel en équipe](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).