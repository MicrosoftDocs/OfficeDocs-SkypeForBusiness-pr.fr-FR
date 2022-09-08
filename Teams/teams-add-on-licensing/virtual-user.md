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
- admindeeplinkMAC
description: Découvrez comment attribuer Téléphonie Microsoft Teams licences de compte de ressource à des comptes de ressources pour les standards automatiques et les files d’attente d’appels dans votre organisation.
ms.openlocfilehash: 56b461c2de32f32dd51d72c5468e31f51b107310
ms.sourcegitcommit: 09b77e83bc41914007606468e322d4ea47e2e8a4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67630424"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>licences de compte de ressource Téléphonie Microsoft Teams

Dans Microsoft Teams, tous les standards automatiques et les files d’attente d’appels nécessitent un compte de ressources associé. Chaque compte de ressource doit se voir attribuer une **licence de compte** de ressource Téléphonie Microsoft Teams pour s’assurer qu’il est correctement identifié par le système et fonctionne correctement, *que le compte de ressource se voit attribuer ou non un numéro de téléphone*. Les organisations disposant d’un abonnement incluant Teams Phone reçoivent automatiquement une certaine quantité de licences de **compte de ressources de téléphone Teams** sans frais supplémentaires.  Un plan d’appel Microsoft n’est pas nécessaire, sauf si vous souhaitez pouvoir composer un numéro à l’aide de ce compte de ressource. Pour plus d’informations, consultez [Planifier le standard automatique Teams et les files d’attente d’appels](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> Auparavant, une licence **de compte de ressource de téléphone Teams** (anciennement appelée licence **d’utilisateur virtuel** ) était nécessaire uniquement lors de l’affectation d’un numéro de téléphone à un compte de ressource. À présent, une licence de compte de ressource **téléphonique Teams** doit être attribuée à tous les comptes de ressources, qu’ils se voient attribuer ou non un numéro de téléphone. En outre, n’affectez pas de licence **Téléphonie Teams standard** à un compte de ressource. Si vous disposez actuellement de comptes de ressources configurés avec des licences **Téléphonie Teams standard**, vous devez basculer vers une licence **de compte de ressources de téléphone Teams**, comme décrit ci-dessous.
 

## <a name="resource-account-license-allocation"></a>Allocation de licences de compte de ressources

Votre organisation reçoit des licences de **compte de ressources de téléphone Teams** en fonction de sa taille globale. Toute organisation disposant d’un abonnement avec des fonctionnalités de système téléphonique, telles que **Téléphonie Teams standard** et **Teams Phone avec licences forfait d’appels**, dispose de 25 licences de **compte de ressources de téléphone Teams** disponibles gratuitement. 

Pour chaque 10 licences utilisateur de **Téléphonie Teams standard** ou **Teams Phone avec forfait d’appels** dans votre organisation, une licence de **compte de ressource téléphonique Teams** supplémentaire est disponible.  La plupart des organisations disposent de suffisamment de licences **de compte de ressources de téléphone Teams** en fonction de ce plan de mise à l’échelle. Si d’autres licences de **compte de ressources de téléphone Teams** sont nécessaires, vous pouvez acheter davantage de licences de **compte de ressources de téléphone Teams** au-delà de l’allocation standard par le biais de votre représentant de compte Microsoft.

### <a name="license-allocation-example"></a>Exemple d’allocation de licence

Contoso, Inc. a acheté 600 licences incluant Phone System (une pour chaque employé). Contoso dispose d’un nombre initial de 25 licences plus 60 licences de **compte de ressources de téléphone Teams** , soit 85 au total. Son organisation dispose de 90 files d’attente d’appels et de standards automatiques. Ils doivent attribuer toutes les licences **de compte de ressources de téléphone Teams** et acheter cinq licences supplémentaires de **compte de ressources de téléphone Teams** . 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Comment obtenir des licences de compte de ressource Téléphonie Microsoft Teams

1. Connectez-vous au [Centre d’administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Accédez **aux** > **modules complémentaires** Billing [**Purchase Services**](https://go.microsoft.com/fwlink/p/?linkid=868433) > .
3. Faites défiler la page pour rechercher la licence **de compte de ressource Téléphonie Microsoft Teams**. Sélectionnez **Acheter maintenant**.

   > [!NOTE]
   > Gardez à l’esprit que même si vous êtes dans votre allocation, vous devez toujours **acheter** la licence même si elle a un coût égal à zéro.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Modifier un compte de ressource existant pour utiliser une licence de compte de ressource Téléphonie Microsoft Teams

Si vous disposez de comptes de ressources existants à l’aide d’une licence **Téléphonie Teams standard**, vous devez basculer vers une licence **de compte de ressources de téléphone Teams** :

1. Obtenez la nouvelle licence **de compte de ressources de téléphone Teams** .
2. Suivez les étapes liées dans le Centre d'administration Microsoft 365 pour [déplacer les utilisateurs vers un autre abonnement](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une licence **Téléphonie Teams standard** et attribuez la licence **compte de ressource téléphonique Teams** dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications de compte, ajoutez la nouvelle licence et enregistrez à nouveau les paramètres du compte, le compte de ressource peut ne plus fonctionner comme prévu, comme les standards automatiques et les files d’attente d’appels de votre organisation ne fonctionnent plus.
>
> Si cela se produit, nous vous recommandons de créer un compte de ressource à l’aide de la licence **du compte de ressources de téléphone Teams** et de supprimer le compte de ressource rompu.

## <a name="related-information"></a>Informations connexes

[Mise à jour du service Standard automatique et Files d’attente d’appels](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gérer les comptes de ressources dans Microsoft Teams](../manage-resource-accounts.md)
