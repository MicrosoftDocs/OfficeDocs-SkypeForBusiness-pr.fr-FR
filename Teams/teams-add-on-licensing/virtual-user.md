---
title: licences de compte de ressource Téléphonie Microsoft Teams
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
description: Découvrez comment attribuer des licences de compte de ressources de téléphone Teams gratuites ou des licences utilisateur Téléphonie Teams standard payantes aux comptes de ressources de votre organisation.
ms.openlocfilehash: 07b47b2ec5b24b1edbfb599dc5a61e96169a02a2
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615400"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>licences de compte de ressource Téléphonie Microsoft Teams

Les organisations avec Téléphonie Teams standard ou Teams Phone avec forfait d’appels sous licence peuvent attribuer une licence *de compte* de ressource Téléphonie Microsoft Teams gratuite ou une licence d’utilisateur *Téléphonie Teams standard* payante aux comptes de ressources. Un plan d’appel Microsoft n’est pas toujours requis (voir [Plan for Teams Auto Attendant et call queues](../plan-auto-attendant-call-queue.md#prerequisites) for prerequisites when transfering calls to an external phone number).

Tous les standards automatiques et les files d’attente d’appels nécessitent un compte de ressource associé. Les comptes de ressources qui nécessitent un numéro de téléphone ont besoin d’une licence *de compte* de ressource Téléphonie Microsoft Teams gratuite ou d’une licence d’utilisateur *Téléphonie Teams standard* payante avant qu’un numéro de téléphone puisse être appliqué au compte de ressource.

> [!TIP]
> Aucune licence n’est nécessaire pour les comptes de ressources qui seront utilisés avec des standards automatiques imbriqués ou des files d’attente d’appels qui n’ont pas de numéro de téléphone attribué. Consultez le diagramme suivant pour obtenir des informations de référence.

## <a name="resource-account-license-allocation"></a>Allocation de licences de compte de ressources

Votre organisation est allouée Téléphonie Microsoft Teams licences *de compte de* ressource en fonction de sa taille globale. Toute organisation disposant d’au moins une licence avec des fonctionnalités du système téléphonique Teams, y compris Téléphonie Teams standard et Teams Phone avec licences forfait d’appels, dispose de 25 licences de compte de ressources disponibles gratuitement. Lorsque vous ajoutez 10 Téléphonie Teams standard ou Teams Phone avec des licences d’utilisateur forfait d’appels dans votre organisation, une autre *licence de compte de ressource Téléphonie Microsoft Teams* devient disponible.

> [!NOTE]
> Téléphonie Teams standard et Teams Phone avec forfait d’appels sont des licences complémentaires disponibles pour tous les abonnés Microsoft 365. Téléphonie Teams standard licences sont également incluses dans Microsoft 365 E5 plans.

Si votre organisation utilise les licences *de compte* de ressource Téléphonie Microsoft Teams gratuites pour créer des nœuds de standard automatique ou de file d’attente d’appels, vous pouvez toujours utiliser les licences *de Téléphonie Teams standard* payantes avec un compte de ressources. La plupart des organisations disposent de suffisamment de licences de compte de ressources en fonction du plan de mise à l’échelle.

### <a name="license-allocation-example"></a>Exemple d’allocation de licence

Contoso, Inc. a acheté 600 licences incluant Phone System (une pour chaque employé). Contoso reçoit 25 licences initiales plus 60 *Téléphonie Microsoft Teams compte de* ressources, soit 85 au total. Leur organisation dispose de 90 files d’attente d’appels et de standards automatiques qui ont des numéros de téléphone. Ils doivent attribuer toutes les licences *de compte* de ressources Téléphonie Microsoft Teams et obtenir cinq licences *Téléphonie Teams standard* à prix régulier.

Contoso doit envisager de remanier le standard automatique et le système de file d’attente des appels. S’ils utilisent moins de numéros de téléphone et plus de nœuds imbriqués qui n’ont pas besoin d’un numéro de téléphone, ils simplifient l’implémentation et réduisent les coûts.

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>Comment acheter des licences de compte de ressource Téléphonie Microsoft Teams

1. Connectez-vous au Centre d’administration Microsoft 365.
2. Accédez **aux** > **modules complémentaires** Billing **Purchase Services** > .
3. Faites défiler la page pour rechercher la licence **de compte de ressource Téléphonie Microsoft Teams**. Sélectionnez **Acheter maintenant**.

   > [!NOTE]
   > Gardez à l’esprit que vous devez toujours **acheter** la licence même si elle a un coût de zéro.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Modifier un compte de ressource existant pour utiliser une licence de compte de ressource Téléphonie Microsoft Teams

Si vous décidez de basculer la licence sur votre compte de ressource d’une licence *Téléphonie Teams standard* vers une licence *de compte de ressource Téléphonie Microsoft Teams* :

1. Obtenez la nouvelle licence *de compte de ressource Téléphonie Microsoft Teams*.
2. Suivez les étapes liées dans le Centre d'administration Microsoft 365 pour [déplacer les utilisateurs vers un autre abonnement](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une licence *de Téléphonie Teams standard* complète et attribuez la licence *de compte de ressource Téléphonie Microsoft Teams* dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications apportées au compte, ajoutez la nouvelle licence, puis enregistrez à nouveau les paramètres du compte, le compte de ressource peut ne plus fonctionner comme prévu. Si cela se produit, nous vous recommandons de créer un compte de ressource pour la *licence Téléphonie Microsoft Teams compte de* ressources et de supprimer le compte de ressource rompu.

## <a name="related-information"></a>Informations connexes

[Mise à jour du service Standard automatique et Files d’attente d’appels](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gérer les comptes de ressources dans Microsoft Teams](../manage-resource-accounts.md)
