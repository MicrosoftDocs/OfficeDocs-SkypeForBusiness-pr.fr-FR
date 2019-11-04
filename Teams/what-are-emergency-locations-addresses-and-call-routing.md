---
title: Que sont les emplacements, les lieux et le routage d’appel d’urgence ?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Découvrez les emplacements d’urgence, les lieux et le routage des appels d’urgence, et la manière de les planifier et de les affecter à vos utilisateurs. '
ms.openlocfilehash: 4dbfe8d2a10c24ae66967030007328d2b9422e34
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925385"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>Que sont les emplacements, les lieux et le routage d’appel d’urgence ?

Lorsque vous configurez des plans d’appel, vous devez attribuer un emplacement d’urgence à chaque numéro de téléphone lorsque vous obtenez le numéro de téléphone ou lorsque vous l’attribuez à un utilisateur afin de prendre en charge les appels d’urgence. Pour pouvoir affecter un emplacement d’urgence à un numéro de téléphone, vous devez ajouter et valider un emplacement d’urgence. La validation vérifie que l’emplacement d’urgence est reconnu et qu’il est dans un format approprié qui peut être utilisé par les services de réponse d’urgence. Si vous le souhaitez, vous pouvez ajouter un emplacement au sein de l’emplacement d’urgence afin de fournir un emplacement plus précis pour l’utilisateur. Par exemple, il peut s’agir d’un étage, d’une aile ou d’un bureau lié à un emplacement d’urgence spécifique. Bien qu’il soit possible de valider les emplacements d’urgence, les lieux ne le sont pas.
  
## <a name="what-are-emergency-locations"></a>Que sont les emplacements d'urgence ?

Un emplacement d’urgence est requis pour les numéros de téléphone actifs et lorsqu’il est requis dépend du pays/de la région. Aux États-Unis, un emplacement d’urgence est requis lorsque le numéro est attribué à un utilisateur. Pour les autres pays (par exemple, en Europe, Moyen Orient et Afrique (EMEA), un emplacement d’urgence est requis lorsque vous recevez le numéro de téléphone d’une équipe ou d’un autre fournisseur ou opérateur de services vers Teams.
  
Un emplacement d’urgence pourra être appelé adresse postale, adresse postale ou adresse physique avec l’emplacement facultatif. Il s’agit de l’adresse postale ou rue d’un lieu d’activité pour votre organisation. Par exemple, l’adresse *12345 North rue, Redmond, WA 98052* est utilisée pour diriger les appels d’urgence vers les autorités de répartition compétentes et pour faciliter la localisation de l’appelant d’urgence. Il est probable que vous ayez besoin de plus d’un emplacement d’urgence si votre entreprise possède plusieurs emplacements d’entreprise physiques.
  
La validation d’une adresse de secours implique de vérifier qu’elle est légitime et correctement mise en forme pour les services de réponse d’urgence. Il est possible d’ajouter et d’enregistrer un emplacement d’urgence qui n’est pas validé, mais seuls les emplacements validés peuvent être associés à un utilisateur. Après validation et enregistrement d’un emplacement d’urgence, vous pouvez l’affecter à un utilisateur. Pour modifier un emplacement d’urgence enregistré et validé, vous devez en créer un autre.
  
## <a name="what-are-places"></a>Emplacements géographiques

Une place est associée à un emplacement d’urgence pour fournir un emplacement plus précis au sein d’un bâtiment. Il s’agit généralement d’un étage, d’une aile de bâtiment ou d’un numéro de bureau à l’endroit où se trouve l’utilisateur. Vous pouvez avoir un nombre illimité de lieux associés à une adresse de secours.
  
Lorsque vous affectez un emplacement d’urgence à un utilisateur, il s’agit en fait d’un ID d’emplacement qui est référencé lors de l’affectation de l’emplacement. L’ID d’emplacement inclut l’adresse de secours référencée (rue ou adresse postale). Par défaut, un emplacement d’urgence est inclus dans les cas où les lieux de construction ne sont pas nécessaires.
  
## <a name="what-is-emergency-call-routing"></a>Qu'est-ce que le routage d'appel d'urgence ?

Les emplacements d’urgence et les emplacements d’urgence sont utilisés lors du processus de routage des appels d’urgence vers le centre de répartition approprié lors de la distribution des premiers répondants d’urgence. Lorsque l’utilisateur d’une équipe compose un numéro d’urgence, la façon dont l’appel est acheminé vers le point de connexion de la sécurité publique (PSAPI) est variable par pays ou région. Dans certains pays (par exemple, les États-Unis et le Royaume-Uni), les appels sont d’abord prédéfinis pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de répartition approprié. Dans d’autres pays ou régions, les appels sont dirigés directement vers le centre de répartition qui dessert le numéro de téléphone associé à l’appelant d’urgence.
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>Création, ajout et affectation d’emplacements d’urgence et de lieux à vos utilisateurs

1. **Planifiez les emplacements d’urgence**. La première étape consiste à planifier vos emplacements d’urgence. Dressez la liste de vos adresses physiques. Ensuite, en fonction de cela, déterminez si des emplacements pour les lieux d’urgence sont nécessaires et, le cas échéant. Par exemple, dans le cas d’une entreprise possédant trois immeubles de bureau avec quatre étages, il est probable qu’il y ait trois emplacements d’urgence, les étages 1 à 4 étant indiqués comme emplacement pour chacun d’eux.
    
2. **Ajoutez vos emplacements d’urgence**. L’étape suivante consiste à ajouter vos emplacements d’urgence. Pour en savoir plus, reportez-vous à [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md).
    
    > [!IMPORTANT]
    > La validation d’une rue ou d’une adresse postale implique de vérifier qu’elle est légitime et correctement mise en forme. Il est possible qu’une adresse de secours partiellement correcte (par exemple, le nom de la ville, par exemple) puisse rester valide. Le processus de validation utilise toutes les parties d’une adresse donnée pour déterminer s’il contient suffisamment d’informations pour acheminer l’appel vers le centre de répartition d’urgence approprié. Si tel est le cas, il sera renvoyé comme validé et peut être attribué à un numéro de téléphone.
  
3. **Obtenez des numéros de téléphone**. L’étape suivante consiste à obtenir des numéros de téléphone pour vos utilisateurs. À cet effet, vous pouvez obtenir de nouveaux numéros de téléphone auprès d'Office 365 ou en « portant » ou en transférant vos numéros de téléphone existants vers Office 365. Pour consulter les étapes complètes, voir [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
    
4. **Attribution de numéros de téléphone**. La dernière étape consiste à permettre aux utilisateurs de passer et de recevoir des appels téléphoniques. Vous devez donc attribuer un numéro de téléphone à chaque utilisateur. Pour attribuer un numéro de téléphone, reportez-vous à la section [affectation, modification ou suppression du numéro de téléphone d’un utilisateur](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Si vous avez besoin d’obtenir plus de numéros de téléphone, [Contactez l’assistance téléphonique PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

    
## <a name="related-topics"></a>Rubriques connexes

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Conditions générales d’utilisation des appels d’urgence](emergency-calling-terms-and-conditions.md)