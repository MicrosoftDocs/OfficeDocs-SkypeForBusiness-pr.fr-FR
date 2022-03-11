---
title: 'Microsoft Teams Téléphone Standard : licences utilisateur virtuel'
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Découvrez comment attribuer des licences Teams Téléphone Standard gratuites – Utilisateur virtuel ou une licence utilisateur Teams Téléphone utilisateur standard aux comptes de ressources de votre organisation.
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435728"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams Téléphone Standard : licences utilisateur virtuel

Les organisations ayant Teams Téléphone Standard ou Teams Téléphone avec une licence forfait d’appels peuvent affecter une licence *Microsoft Teams Téléphone Standard* – Utilisateur virtuel ou un compte *Teams Téléphone Standard*  licence utilisateur des comptes de ressources. Un plan d’appel Microsoft n’est pas toujours nécessaire (voir Plan pour le Teams automatique et les files d’attente pour les conditions [préalables](../plan-auto-attendant-call-queue.md#prerequisites) lors du transfert d’appels vers un numéro de téléphone externe).

Tous les travailleurs automatiques et les files d’attente d’appels nécessitent un compte de ressource associé. Les comptes de ressources nécessitant un numéro de téléphone ont besoin soit d’une licence *Microsoft Teams Téléphone Standard* – Utilisateur virtuel, soit d’une licence *utilisateur Teams Téléphone Standard* payée pour pouvoir appliquer un numéro de téléphone au compte de ressource.

> [!TIP]
> Aucune licence n’est nécessaire pour les comptes de ressources qui seront utilisés avec des attendants automatiques imbrmbrés ou des files d’attente d’appels sans numéro de téléphone. Consultez le diagramme suivant pour vous y référencer.

:::image type="content" alt-text="Licences utilisateur virtuel." source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>Attribution de licences utilisateur virtuel

Votre organisation est attribuée Microsoft Teams Téléphone *licences Utilisateur* virtuel selon sa taille globale. Toute organisation qui possède au moins une licence avec Teams Système téléphonique, y compris Teams Téléphone Standard et Teams Téléphone avec des licences Plan d’appels, a 25 licences utilisateur virtuel disponibles sans frais. Lorsque vous ajoutez 1 Teams Téléphone 0 licences standard ou Teams Téléphone avec le plan d’appels au niveau de votre organisation, une nouvelle licence Microsoft Teams Téléphone *Standard –* Utilisateur virtuel devient disponible.

> [!NOTE]
> Teams Téléphone standard et Teams Téléphone’offre Forfait d’appels sont des licences de modules disponibles pour tous les Microsoft 365 abonnés. Teams Téléphone licences standard sont également incluses dans le cadre de Microsoft 365 E5 de projets.

Si votre organisation utilise les licences gratuites *Microsoft Teams Téléphone Standard –* Utilisateur virtuel pour créer un standard automatique ou des nodes de file d’attente d’appels, vous pouvez toujours utiliser les licences *Teams Téléphone Standard* payées avec un compte de ressource. La plupart des organisations auront suffisamment de licences utilisateur virtuel sur la base du plan de mise à l’échelle.

### <a name="license-allocation-example"></a>Exemple d’attribution de licence

Contoso, Inc. a acheté 600 licences qui incluent Système téléphonique (une pour chaque employé). Contoso est attribué un nombre initial de 25 plus 60 Microsoft Teams Téléphone *Standard – Utilisateur* virtuel, 85 au total. Son organisation dispose de 90 files d’attente et de files d’attente automatiques qui disposent de numéros de téléphone. Ils doivent attribuer toutes les *licences standard Microsoft Teams Téléphone* les utilisateurs virtuels et obtenir cinq licences standard Teams Téléphone *standard*.

Contoso doit envisager de reconfidenter le système de attendant automatique et de file d’attente d’appels. S’ils utilisent moins de numéros de téléphone et plus de numéros imbrmbrés qui n’ont pas besoin de numéro de téléphone, ils simplifient l’implémentation et réduisent les coûts.

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>Comment acheter Microsoft Teams Téléphone Standard – Licences utilisateur virtuel

1. Connectez-vous au Centre d’administration Microsoft 365.
2. Allez à **BillingPurchase** >  **servicesAdd-ons** > .
3. Faites défiler jusqu’à la fin pour trouver **la licence Microsoft Teams Téléphone Standard – Utilisateur** virtuel. **Sélectionnez Acheter maintenant**.

   > [!NOTE]
   > N’oubliez pas que vous devez **toujours acheter** la licence, même si son coût est nul.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>Modifier un compte de ressource existant pour utiliser une licence utilisateur Microsoft Teams Téléphone Standard – Utilisateur virtuel

Si vous décidez de basculer la licence de votre compte de ressource *d’une licence standard* Teams Téléphone à une *licence standard Microsoft Teams Téléphone – Utilisateur* virtuel :

1. Obtenez la nouvelle licence Microsoft Teams Téléphone Standard – Utilisateur virtuel.
2. Suivez les étapes liées dans le centre Administration Microsoft 365 pour [déplacer les utilisateurs vers un autre abonnement](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une *licence Teams Téléphone standard et* attribuez la licence *Microsoft Teams Téléphone Standard – Utilisateur* virtuel dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications apportées au compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressource peut ne plus fonctionner comme prévu. Dans ce cas, nous vous recommandons de créer un compte de ressource *pour la licence Microsoft Teams Téléphone Standard – Utilisateur* virtuel et de supprimer le compte de ressource rompu.

## <a name="related-information"></a>Informations connexes

[Standard automatique et mise à jour du service des files d’attente d’appels](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gérer les comptes de ressources dans Microsoft Teams](../manage-resource-accounts.md)
