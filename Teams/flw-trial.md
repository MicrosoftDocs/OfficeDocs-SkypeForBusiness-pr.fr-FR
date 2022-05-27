---
title: Gérer la version d’évaluation en première ligne dans Teams
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer un Teams de 90 jours pour la version d’évaluation des travailleurs de première ligne pour votre organisation.
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758295"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Gérer la version d’évaluation en première ligne dans Teams

> [!NOTE]
> Cette expérience d’essai sera bientôt disponible. Vous pouvez vérifier si cela est disponible pour votre organisation en recherchant un message dans le [centre de](https://go.microsoft.com/fwlink/p/?linkid=2070717) messages de votre centre de Administration Microsoft 365.

L’expérience d’essai en première ligne Microsoft Teams permet aux utilisateurs de votre organisation qui sont dans Teams de lancer une expérience de Teams pour l’ensemble de leur équipe de première ligne, tant que les autres membres se trouvent dans Azure Active Directory (Azure AD). Vous pouvez désactiver cette fonctionnalité pour les utilisateurs de votre organisation à l’aide du [module PowerShell AllowSelfServicePurchase](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

## <a name="what-services-are-included"></a>Quels services sont inclus

La version d’évaluation inclut tout ce qui se trouve dans la [licence Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3) avec les exceptions suivantes :

- La version d’évaluation en première ligne inclut Exchange Foundation plutôt que Exchange Kiosk. D’autres fonctionnalités de Teams peuvent manquer aux utilisateurs en raison de cette modification.

## <a name="eligibility"></a>Admissibilité

> [!NOTE]
> Vous pouvez vérifier si votre organisation fait partie du pilote d’évaluation en recherchant une annonce dans le [centre de](https://go.microsoft.com/fwlink/p/?linkid=2070717) messages de votre centre Administration Microsoft 365. Votre organisation doit faire partie du pilote d’essai pour que les utilisateurs puissent lancer ou participer à une version d’évaluation. Cette offre n’est pas valable pour les clients GCC, GCC HIGH, DoD ou EDU.

La version d’évaluation en première ligne peut accueillir un maximum de 300 utilisateurs par version d’évaluation.

Les utilisateurs peuvent démarrer une version d’évaluation de première ligne pour leur équipe s’ils :

- Disposez d’une licence active qui leur donne accès à Teams.
- Vous n’avez pas encore démarré d’essai de travail de première ligne.

> [!IMPORTANT]
> Si l’utilisateur qui a lancé la version d’évaluation quitte votre organisation avant la fin de la version d’évaluation, vous devez surveiller l’essai, consulter l’équipe pour voir qui tire parti de ces fonctionnalités et décider quels utilisateurs vous devrez mettre à niveau vers une licence payante.

Les utilisateurs peuvent participer à une version d’évaluation de travail de première ligne s’ils disposent d’une adresse e-mail de domaine Azure Active Directory gérée.

Les utilisateurs peuvent participer s’ils ont déjà commencé une version d’évaluation, mais ne peuvent pas lancer un autre essai.

> [!NOTE]
> Les utilisateurs sans accès existant à Teams ne peuvent être ajoutés à l’équipe d’évaluation qu’au moment de la création de l’équipe. Les utilisateurs Teams existants peuvent toujours être ajoutés à la version d’évaluation après la création de l’équipe.

## <a name="set-up-the-trial"></a>Configurer la version d’évaluation

Les utilisateurs éligibles peuvent démarrer une version d’évaluation de première ligne en se connectant à l’application Tâches dans Teams à partir de [l’application](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks) de bureau ou web. Pour l’instant, le démarrage d’une version d’évaluation de première ligne via un appareil mobile n’est pas pris en charge. Lorsqu’une version d’évaluation est lancée, l’ensemble de l’équipe reçoit automatiquement la licence d’évaluation de première ligne. Les utilisateurs disposant de licences payantes existantes qui leur donnent accès à Teams se verront également attribuer des licences d’évaluation, mais conserveront les fonctionnalités de leurs licences existantes tout au long de l’essai et conserveront leurs licences payantes existantes après la fin de l’essai. L’utilisateur qui a démarré la version d’évaluation recevra des notifications par e-mail tout au long de l’essai.

## <a name="manage-the-frontline-trials-experience"></a>Gérer l’expérience des essais en première ligne

Les administrateurs peuvent empêcher les utilisateurs finaux de démarrer la version d’évaluation de première ligne au sein de leur organisation à l’aide du module PowerShell **AllowSelfServicePurchase** . Cela concerne uniquement les licences d’évaluation. [Découvrez comment utiliser le module PowerShell AllowSelfServicePurchase](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell).

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>Gérer Teams pour les utilisateurs disposant de la licence d’évaluation de première ligne

Vous pouvez gérer les utilisateurs qui disposent de la licence d’évaluation de première ligne, tout comme vous gérez les utilisateurs disposant d’une licence payante régulière. Pour plus d’informations[Gérer les paramètres de Teams pour votre organisation](/microsoftteams/manage-teams-overview).

### <a name="remove-a-trial-license"></a>Supprimer une licence d’évaluation

Vous pouvez supprimer la licence d’évaluation de première ligne via PowerShell ou votre Centre d'administration Microsoft 365.

[Découvrez comment supprimer avec PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

[Découvrez comment supprimer dans le Centre d’administration](/microsoft-365/admin/add-users/delete-a-user).

## <a name="upgrade-users-from-frontline-trial"></a>Mettre à niveau des utilisateurs à partir d’une version d’évaluation de première ligne

Les utilisateurs peuvent vous contacter pour demander des licences à la fin de l’essai. Vous aurez besoin de privilèges d’administrateur pour mettre à niveau vos utilisateurs.

### <a name="when-to-upgrade"></a>Quand mettre à niveau

Vers la fin de la version d’évaluation de 90 jours, vous devez vérifier auprès de vos utilisateurs qui doivent continuer avec une licence payante. Veillez à le faire avant l’expiration de l’abonnement d’évaluation de première ligne pour éviter toute interruption des expériences des utilisateurs.

> [!IMPORTANT]
> Si la licence d’essai frontal se termine et qu’un utilisateur ne reçoit pas immédiatement une licence qui inclut Teams, il perd l’accès à Teams. Au bout de 30 jours, leurs données (fichiers, messages, etc.) sont supprimées. L’utilisateur demeure dans Azure Active Directory. Si une nouvelle licence est attribuée à l’utilisateur pour activer Teams fonctionnalités au cours de la période de 30 jours, tout son contenu dans Teams existera toujours.

### <a name="choose-an-upgrade-path"></a>Choisir un chemin de mise à niveau

> [!TIP]
> La version d’évaluation en première ligne est basée sur la [licence Microsoft 365 F3](https://www.microsoft.com/microsoft-365/enterprise/f3).

En fonction des abonnements dont votre organisation dispose actuellement, il existe trois façons de passer d’une version d’évaluation en première ligne à une licence payante :

- **Mettez à niveau un abonnement Microsoft 365 existant.** Utilisez cette option si votre organisation dispose d’abonnements à d’autres produits Office qui n’incluent pas Teams. Pour plus d’informations, consultez [Mettre à niveau vers un autre plan](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan). Pour afficher les utilisateurs actifs d’un abonnement existant, accédez à **Utilisateurs >** [Utilisateurs actifs](https://go.microsoft.com/fwlink/p/?linkid=834822) dans le centre d’administration Microsoft 365.

- **Ajoutez des utilisateurs à un abonnement Microsoft 365 existant.** Utilisez cette option si votre organisation n’a pas suffisamment de licences Teams payantes pour couvrir votre équipe de première ligne. Pour plus d’informations, consultez [Acheter ou supprimer des licences](/microsoft-365/commerce/licenses/buy-licenses). Pour ajouter des utilisateurs à un abonnement existant qui dispose déjà de suffisamment de licences disponibles, consultez [Déplacer les utilisateurs vers un autre abonnement](/microsoft-365/commerce/subscriptions/move-users-different-subscription). Pour afficher les utilisateurs actifs d’un abonnement existant, accédez à **Utilisateurs >** [Utilisateurs actifs](https://go.microsoft.com/fwlink/p/?linkid=834822) dans le centre d’administration Microsoft 365.

- **Acheter un nouvel abonnement Microsoft 365.** Utilisez cette option si votre organisation n’a pas d’abonnements existants pour Office produits, ou si votre organisation souhaite acheter un abonnement différent de son abonnement existant pour couvrir les utilisateurs de première ligne. Pour plus d’informations, consultez [Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline).

Si vous ne savez pas vers quel Microsoft 365 abonnement effectuer la mise à niveau, consultez [Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline). Si vous avez besoin d’aide supplémentaire pour choisir un abonnement ou si votre organisation a besoin de plus de 300 licences, contactez votre [partenaire Microsoft](https://www.microsoft.com/solution-providers/home) ou compte Microsoft représentant.

### <a name="assign-paid-licenses"></a>Attribuer des licences payantes

Pour attribuer vos licences nouvellement acquises, consultez [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).  

Après avoir attribué les nouvelles licences, retirez les licences exploratoires Teams. Pour plus d’informations, consultez [Retirer des licences aux utilisateurs](/microsoft-365/admin/manage/remove-licenses-from-users).

## <a name="faq"></a>FAQ

**Durée de l’essai** <br>
La première version d’évaluation dure 90 jours.

**Que doivent faire les administrateurs à la fin de l’expérience d’essai en première ligne de 90 jours ?** <br>
À la fin de la version d’évaluation de 90 jours, vous devez vérifier auprès de vos utilisateurs qui doivent continuer avec une licence payante. Vous devrez ensuite [mettre à niveau vos utilisateurs](#upgrade-users-from-frontline-trial).

**Que se passe-t-il si l’utilisateur qui a démarré la version d’évaluation quitte votre organisation ?** <br>
En tant qu’administrateur, vous devez surveiller la version d’évaluation pour le reste de la période de 90 jours et effectuer une mise à niveau vers des licences payantes pour les utilisateurs qui en ont besoin à la fin de l’essai.

**Qu’est-ce que la stratégie de rétention des données ?** <br>
Vous pouvez en savoir plus sur la conservation des données à partir des [informations d’abonnement Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?).

**Que se passe-t-il si un utilisateur rencontre une erreur lors du démarrage de la version d’évaluation en première ligne ?** <br>
Assurez-vous que votre organisation, l’utilisateur qui démarre la version d’évaluation et les utilisateurs ajoutés à la version d’évaluation répondent aux [critères d’éligibilité](#eligibility).