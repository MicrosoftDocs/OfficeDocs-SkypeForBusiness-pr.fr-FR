---
title: licences de compte de ressources Téléphonie Microsoft Teams
author: DaniEASmith
ms.author: danismith
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
description: Découvrez comment attribuer des licences de compte de ressources Téléphonie Microsoft Teams aux comptes de ressources pour les standards automatiques et les files d’attente d’appels dans votre organisation.
ms.openlocfilehash: d3eacab8569981550520385c4aee297ae6835a59
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307759"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>licences de compte de ressources Téléphonie Microsoft Teams

Dans Microsoft Teams, tous les standards automatiques et les files d’attente d’appels nécessitent un compte de ressource associé. Chaque compte de ressource doit se voir attribuer une licence **Téléphonie Microsoft Teams compte de ressource** pour s’assurer qu’il est correctement identifié par le système et qu’il fonctionne correctement, *que le compte de ressource se voit attribuer ou non un numéro de téléphone*. Les organisations disposant d’un abonnement incluant Teams Phone se voient automatiquement allouer un certain nombre de licences de **compte de ressources téléphoniques Teams** sans frais supplémentaires.  Un plan d’appel Microsoft n’est pas nécessaire, sauf si vous souhaitez être en mesure d’appeler à l’aide de ce compte de ressource. Pour plus d’informations, consultez [Planifier le standard automatique teams et les files d’attente d’appels](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> Auparavant, une licence de **compte de ressource téléphonique Teams** (autrefois appelée licence **d’utilisateur virtuel** ) était nécessaire uniquement lors de l’attribution d’un numéro de téléphone à un compte de ressource. À présent, tous les comptes de ressources doivent se voir attribuer une licence de **compte de ressource téléphonique Teams** , qu’un numéro de téléphone leur soit attribué ou non. En outre, n’attribuez pas de licence **Téléphonie Teams standard** à un compte de ressource. Si vous avez actuellement des comptes de ressources configurés avec des licences **Téléphonie Teams standard**, vous devez basculer vers une licence **de compte de ressource téléphone Teams**, comme décrit ci-dessous.
 

## <a name="resource-account-license-allocation"></a>Allocation de licence de compte de ressource

Votre organisation dispose de licences de **compte de ressources téléphoniques Teams** en fonction de sa taille globale. Toute organisation disposant d’un abonnement avec des fonctionnalités de système téléphonique, telles que les licences **Téléphonie Teams standard** et **Téléphone Teams avec forfait d’appels**, se voit attribuer 25 licences **de compte de ressources téléphoniques Teams** disponibles gratuitement. 

Pour chaque licence utilisateur de 10 **Téléphonie Teams standard** ou **Téléphone Teams avec forfait d’appels** dans votre organisation, une licence de **compte de ressource téléphonique Teams** supplémentaire devient disponible.  La plupart des organisations disposent de suffisamment de licences de **compte de ressources téléphoniques Teams** en fonction de ce plan de mise à l’échelle. Dans le cas où davantage de licences de **compte de ressources téléphoniques Teams** sont requises, vous pouvez acheter davantage de licences de **compte de ressource téléphone Teams** au-delà de l’allocation standard via EA, EAS, EES, CSP, Web Direct, NCE – customer led et NCE – Partner led ou votre représentant de compte Microsoft.

### <a name="license-allocation-example"></a>Exemple d’allocation de licence

Contoso, Inc. a acheté 600 licences incluant le système téléphonique (une pour chaque employé). Contoso se fait attribuer 25 licences de **compte de ressources téléphoniques Teams** plus 60, soit 85 au total. Leur organisation a 90 files d’attente d’appels et standards automatiques. Ils doivent attribuer toutes les licences **de compte de ressources téléphoniques Teams** et acheter cinq licences de **compte de ressource de téléphone Teams** supplémentaires. 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Comment obtenir des licences de compte de ressources Téléphonie Microsoft Teams

1. Connectez-vous au [Centre d’administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Accédez à **Facturation** > [**Acheter des services**](https://go.microsoft.com/fwlink/p/?linkid=868433) > **Add-ons**.
3. Faites défiler la page pour rechercher la licence **Téléphonie Microsoft Teams compte de ressources**. Sélectionnez **Acheter maintenant**.

   > [!NOTE]
   > Gardez à l’esprit que même si vous êtes dans votre allocation, vous devez toujours **Acheter** la licence même si son coût est égal à zéro.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Modifier un compte de ressource existant pour utiliser une licence de compte de ressource Téléphonie Microsoft Teams

Si vous disposez de comptes de ressources existants utilisant une licence **Téléphonie Teams standard**, vous devez passer à l’utilisation d’une licence de **compte de ressource téléphonique Teams** :

1. Obtenez la nouvelle licence **de compte de ressource téléphonique Teams** .
2. Suivez les étapes liées dans la Centre d'administration Microsoft 365 [pour Déplacer des utilisateurs vers un autre abonnement](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une licence **Téléphonie Teams standard** et attribuez la licence **de compte de ressource téléphonique Teams** dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence et enregistrez à nouveau les paramètres du compte, le compte de ressource risque de ne plus fonctionner comme prévu, car les standards automatiques et les files d’attente d’appels de votre organisation ne fonctionnent plus.
>
> Si cela se produit, nous vous recommandons de créer un compte de ressource à l’aide de la licence **compte de ressource téléphone Teams** et de supprimer le compte de ressource rompu.

## <a name="related-information"></a>Informations connexes

[Mise à jour du service standard automatique et des files d’attente d’appels](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gérer les comptes de ressources dans Microsoft Teams](../manage-resource-accounts.md)
