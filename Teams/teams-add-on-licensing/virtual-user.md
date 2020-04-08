---
title: Système téléphonique Microsoft 365-licences utilisateur virtuelles
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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
description: En savoir plus sur les licences utilisateur virtuelles gratuites.
ms.openlocfilehash: f2ecaddc6fd1dcc4bbb179fde3f495a0eea29353
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190813"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Système téléphonique Microsoft 365-licence utilisateur virtuel 

Les organisations disposant d’une licence de système téléphonique peuvent attribuer un système téléphonique Microsoft 365 gratuit-licence utilisateur virtuel ou une licence utilisateur de système téléphonique payant aux comptes de ressources. Un plan d’appels n’est pas obligatoire. Tous les standards automatiques ou files d’attente d’appels nécessitent un compte de ressources associé. Les comptes de ressources qui requièrent un numéro de téléphone doivent disposer d’un système téléphonique Microsoft 365 gratuit-licence d’utilisateur virtuel ou d’une licence utilisateur de système téléphonique payant avant qu’un numéro de téléphone puisse être appliqué au compte de ressources.

> [!TIP]
> Aucune licence n’est nécessaire pour les comptes de ressources qui seront utilisés avec des standards automatiques imbriqués ou des files d’attente d’appels sans numéro de téléphone. Pour en savoir plus, consultez le diagramme suivant : 

![Licences utilisateur virtuelles](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Attribution de licence utilisateur virtuel

Votre organisation est allouée par le système téléphonique Microsoft 365 : les licences utilisateur virtuelles en fonction de la taille globale. Toute organisation qui dispose d’au moins une licence, y compris système téléphonique ou doté d’un système téléphonique, a 25 licences utilisateur virtuelles disponibles sans frais. Lorsque vous ajoutez 10 licences utilisateur de système téléphonique au sein de votre organisation, un système téléphonique Microsoft 365 supplémentaire est disponible pour les utilisateurs virtuels.

> [!NOTE]
> Le système téléphonique est une licence de complément disponible avec Office 365 E1 et E3. Le système téléphonique est également inclus dans le cadre des licences Office 365 E5 et Microsoft 365 Business Voice.

Si votre organisation utilise la version gratuite du système téléphonique Microsoft 365, les licences utilisateur virtuelles permettant de créer des nœuds de files d’attente ou de file d’attente d’appels, vous pouvez toujours utiliser les licences du système téléphonique payant avec un compte de ressources. La plupart des organisations disposeront de licences utilisateur virtuelles suffisantes en fonction de l’offre de mise à l’échelle. 

### <a name="license-allocation-example"></a>Exemple d’attribution de licence

Contoso, Inc. a acheté des licences 600 incluant un système téléphonique (pour chaque employé). Contoso est associé à un système téléphonique Microsoft 365 60 initial, c’est-à-dire aux licences utilisateur virtuelles, 85 au total. Son organisation dispose d’une file d’attente d’appels 90 et de standards automatiques disposant de numéros de téléphone. Ils doivent affecter tout le système téléphonique Microsoft 365, ainsi que les licences utilisateur virtuelles et obtenir cinq licences de système téléphonique à prix réduit. 

Contoso doit envisager de reconcevoir le standard automatique et le système de files d’attente d’appels. S’ils utilisent moins de numéros de téléphone et des nœuds imbriqués qui n’ont pas besoin d’un numéro de téléphone, ils simplifient l’implémentation et réduisent les coûts. 

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Achat du système téléphonique Microsoft 365-licences utilisateur virtuelles 

1. Connectez-vous au Centre d’administration Microsoft 365.
2. Accédez aux **Billing** > **modules complémentaires**  > **services d’achat**de facturation
3. Faites défiler jusqu’à la fin pour trouver le **système téléphonique Microsoft 365-licence utilisateur virtuel** . Sélectionnez **acheter maintenant**.

> [!NOTE]
> Gardez à l’esprit que vous devez toujours **acheter** la licence, même si elle a un coût égal à zéro. 

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Modification d’un compte de ressources existant pour utiliser un système téléphonique Microsoft 365-licence utilisateur virtuel

Si vous décidez de basculer la licence sur votre compte de ressources à partir d’une licence de système téléphonique vers un système téléphonique Microsoft 365-licence utilisateur virtuel : 

1. Téléchargez le nouveau système téléphonique Microsoft 365-licence utilisateur virtuel. 
2. Suivez les étapes liées du centre d’administration 365 Microsoft pour [déplacer des utilisateurs vers un autre abonnement](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Supprimez toujours une licence de système téléphonique complet et attribuez-la à une licence d’utilisateur virtuel Microsoft 365. Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressources risque de ne plus fonctionner comme prévu. Si tel est le cas, nous vous recommandons de créer un compte de ressources pour le système téléphonique Microsoft 365-licence d’utilisateur virtuel et de supprimer le compte de ressource endommagé. 

## <a name="related-information"></a>Informations connexes

[Mise à jour du service de files d’attente et de file d’attente automatique](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gérer les comptes de ressources dans Microsoft Teams](../manage-resource-accounts.md)
