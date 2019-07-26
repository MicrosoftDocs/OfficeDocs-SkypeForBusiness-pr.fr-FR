---
title: 'Système téléphonique-licences utilisateur virtuelles '
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
description: En savoir plus sur les licences utilisateur virtuelles gratuites.
ms.openlocfilehash: 73edbae2fce7cdb2ed1fd5c499d58153d91e7086
ms.sourcegitcommit: 5f3c8ea2b3d68704885d212c8f2787c6bc7d1cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/25/2019
ms.locfileid: "35907672"
---
# <a name="phone-systemvirtual-user-license"></a>Système téléphonique-licence utilisateur virtuel 

À compter du 2 juillet, 2019, une organisation avec les utilisateurs titulaires d’une licence de système téléphonique peut désormais obtenir et attribuer un système téléphonique gratuit (ou une licence utilisateur de système téléphonique payant aux comptes de ressources). Vous n’avez plus besoin d’un plan d’appels. Tous les standards automatiques ou files d’attente d’appels nécessitent un compte de ressources associé. Les comptes de ressources qui ont besoin d’un numéro de téléphone doivent disposer d’un système téléphonique gratuit – licence d’utilisateur virtuel ou licence utilisateur de système téléphonique payant avant qu’un numéro de téléphone puisse être appliqué au compte de ressources.

> [!TIP]
> Aucune licence n’est nécessaire pour les comptes de ressources qui seront utilisés avec des standards automatiques imbriqués ou des files d’attente d’appels sans numéro de téléphone. Pour en savoir plus, consultez le diagramme suivant: 

![Licences utilisateur virtuelles](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>Attribution de licence utilisateur virtuel

Votre organisation dispose d’un système téléphonique attribué: les licences utilisateur virtuelles en fonction de la taille globale. 25 licences utilisateur virtuelles sont disponibles pour toute organisation qui dispose d’au moins une licence qui inclut un système téléphonique ou un système téléphonique ajouté. Lorsque vous ajoutez 10 licences utilisateur de système téléphonique au sein de votre organisation, un système téléphonique supplémentaire est fourni avec une licence d’utilisateur virtuel.

> [!NOTE]
> Le système téléphonique est une licence de complément disponible avec les licences Office 365 F1, E1, E3 et Office Premium. Le système téléphonique est également fourni dans le cadre de licences Office 365 E5.

Si votre organisation utilise le système téléphonique gratuit disponible – les licences utilisateur virtuelles dans la création de nœuds de files d’attente ou de file d’attente d’appels, vous pouvez toujours utiliser les licences du système téléphonique payant avec un compte de ressources. La plupart des organisations disposeront de licences utilisateur virtuelles suffisantes en fonction de l’offre de mise à l’échelle. 

### <a name="license-allocation-example"></a>Exemple d’attribution de licence

Contoso, Inc. a acheté des licences 600 incluant un système téléphonique (pour chaque employé), afin qu’elles soient allouées au 25 initial et à un système téléphonique 60 supplémentaire-licences utilisateur virtuelles. Contoso possède au total un système téléphonique 85-licences utilisateur virtuelles. Son organisation dispose d’une file d’attente d’appels 90 et de standards automatiques disposant de numéros de téléphone. Ils doivent affecter tout le système téléphonique (licences utilisateur virtuelles et obtenir cinq licences de système téléphonique standard). 

Contoso doit envisager de reconcevoir le standard automatique et le système de files d’attente d’appels pour utiliser moins de numéros de téléphone et des nœuds imbriqués qui n’ont pas besoin d’un numéro de téléphone ou d’une licence. Le fait de supprimer des numéros de téléphone inutiles simplifie l’implémentation et réduit les coûts. 

## <a name="how-to-acquire-phone-systemvirtual-user-licenses"></a>Acquisition d’un système téléphonique-licences utilisateurs virtuelles 

1. Connectez-vous au centre d’administration Microsoft 365.
2. Accédez aux **** > **abonnements de complément**  > **services d’achat**de facturation
3. Faites défiler jusqu’à la fin pour trouver la licence **«système téléphonique-utilisateur virtuel»** . Sélectionnez **acheter maintenant**.

> [!WARNING]
> Gardez à l’esprit que vous devez encore **acheter** la licence même si le montant est nul. 

## <a name="change-an-existing-resource-account-to-use-a-phone-systemvirtual-user-license"></a>Modifier un compte de ressources existant pour utiliser un système téléphonique-licence utilisateur virtuel

Si vous décidez de basculer entre les licences sur votre compte de ressources à partir d’une licence de système téléphonique et celle d’un système téléphonique, utilisez une licence d’utilisateur virtuel: 

1. Téléchargez le nouveau système téléphonique – licence utilisateur virtuel. 
2. Suivez les étapes liées du centre d’administration 365 Microsoft pour [déplacer des utilisateurs vers un autre abonnement](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription). 

> [!WARNING]
> Supprimez toujours une licence de système téléphonique complet et attribuez-la à la licence de l’utilisateur virtuel pour la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez de nouveau les paramètres du compte, le compte de ressources risque de ne plus fonctionner comme prévu. Si tel est le cas, nous vous recommandons de créer un compte de ressources pour le système téléphonique-licence d’utilisateur virtuel et de supprimer le compte de ressource endommagé. 

## <a name="related-information"></a>Informations connexes

[Mise à jour du service de files d’attente et de file d’attente automatique](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Gérer les comptes de ressources dans Microsoft Teams](../manage-resource-accounts.md)
