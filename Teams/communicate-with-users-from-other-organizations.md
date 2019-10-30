---
title: Communiquer avec des utilisateurs d’autres organisations dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Découvrez comment communiquer avec des utilisateurs d’autres organisations dans Microsoft Teams à l’aide de l’accès externe (fédération) et de l’accès invité.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: a777baed1d5cc35788b2c4f63741317e34eb7905
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754370"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>Communiquer avec des utilisateurs d’autres organisations dans Microsoft Teams
======================================================

Lorsque vous avez besoin de communiquer et de collaborer avec des personnes extérieures à votre organisation, Microsoft Teams vous propose deux manières de procéder. La première, **accès externe** (fédération), permet de rechercher, d’appeler des utilisateurs et de discuter avec eux dans d’autres domaines (par exemple, contoso.com). La deuxième, **accès invité**, vous permet d’ajouter des utilisateurs à vos équipes, comme invités, à l’aide de leur adresse e-mail. Vous pouvez collaborer avec des invités comme vous le feriez avec d’autres utilisateurs dans votre organisation.

À un niveau élevé, voici comment choisir (pour une comparaison détaillée, voir [Comparer l’accès externe et l’accès invité](#compare-external-and-guest-access)) :

## <a name="external-access"></a>Accès externe

Utilisez l’**accès externe** (fédération) lorsque vous avez besoin d’une solution qui permet aux utilisateurs externes dans d’autres domaines de rechercher, appeler, discuter et configurer des réunions avec vous. Les utilisateurs externes n’ont pas accès aux équipes ou ressources d’équipe de votre organisation. Sélectionnez l’accès externe lorsque vous voulez communiquer avec des utilisateurs externes qui utilisent encore Skype Entreprise (en ligne ou en local) ou Skype (à paraître début 2020). 

L’accès externe est activé par défaut dans Teams. Ainsi, votre organisation peut communiquer avec tous les domaines externes. L’administrateur Teams peut le désactiver ou spécifier les domaines à inclure (ou à exclure). Pour plus d’informations, voir [Gérer l’accès externe](manage-external-access.md). 

Si vous voulez que les utilisateurs externes aient accès aux équipes et aux canaux, [l’accès invité](#guest-access) sera sans doute préférable. 


## <a name="guest-access"></a>Accès invité

Utiliser **l’accès invité** pour ajouter un utilisateur individuel (quel que soit le domaine) à une équipe, où les participants peuvent discuter, appeler, se rencontrer et collaborer sur des fichiers d’organisation (stockés dans SharePoint ou OneDrive Entreprise) à l’aide d’applications Office 365 telles que Word, Excel ou PowerPoint. Les utilisateurs invités peuvent bénéficier de presque toutes les mêmes fonctionnalités Teams qu’un membre d’équipe natif. Pour plus d’informations, lisez [Accès invité dans Teams](guest-access.md).

- Les invités sont ajoutés dans l’annuaire Active Directory de votre organisation.
- Pour communiquer avec un invité, celui-ci doit être connecté à Teams à l’aide de son compte invité. En d’autres termes, un invité peut avoir besoin de se déconnecter de son compte Teams pour se connecter au vôtre.
- Les utilisateurs invités ont accès à davantage de ressources dans Teams, par exemple, des fichiers, des équipes et des canaux, que des utilisateurs disposant d’un accès externe (fédéré).
- L’administrateur Teams contrôle tout ce qu’un invité peut (ou ne peut pas) faire dans le centre d’administration Teams. Pour plus d’informations, voir [Gérer l’accès invité](manage-guests.md).

Si vous êtes prêt à activer l’accès invité au sein de votre organisation, commencez par le [liste de vérification de l’accès invité](guest-access-checklist.md).


## <a name="compare-external-and-guest-access"></a>Comparer l’accès externe et l’accès invité

| Fonctionnalité | Utilisateurs de l’accès externe | Utilisateurs de l’accès invité |
|---------|-----------------------|--------------------|
| L’utilisateur peut converser avec une personne d’une autre entreprise | Oui |Oui |
| L’utilisateur peut appeler une personne d’une autre entreprise | Oui | Oui |
| L’utilisateur peut voir si une personne d’une autre entreprise est disponible pour un appel ou une conversation | Oui | Oui <sup>1</sup> |
| L’utilisateur peut rechercher des utilisateurs sur des clients externes | Oui <sup>2</sup> | Non |
| L’utilisateur peut partager des fichiers | Non | Oui |
| L’utilisateur peut accéder aux ressources Teams | Non | Oui |
| L’utilisateur peut être ajouté à une conversation de groupe | Non | Oui |
| L’utilisateur peut être invité à une réunion | Oui | Oui |
| Des utilisateurs supplémentaires peuvent être ajoutés à une conversation avec un utilisateur externe | No<sup>3</sup> | S/O |
| L’utilisateur est identifié comme partie externe | Oui | Oui |
| La présence s’affiche. | Oui | Oui |
| Le message d’absence du bureau apparaît | Non | Oui |
| Un utilisateur individuel peut être bloqué | Non | Oui |
| les @mentions sont prises en charge | Oui <sup>4</sup> | Oui |
| Passer des appels privés | Oui | Oui |
| Autoriser la vidéo sur IP | Oui | Oui |
| Mode de partage d’écran | Oui <sup>4</sup> | Oui |
| Autoriser la conférence maintenant | Non | Oui |
| Modifier des messages envoyés | Oui <sup>4</sup> | Oui |
| Possibilité de supprimer des messages envoyés | Oui <sup>4</sup> | Oui |
| Utiliser Giphy dans la conversation | Oui <sup>4</sup> | Oui |
| Utiliser des mèmes dans la conversation | Oui <sup>4</sup> | Oui |
| Utiliser des autocollants dans la conversation | Oui <sup>4</sup> | Oui |
||||

<sup>1</sup> À condition que l’utilisateur ait été ajouté en tant qu’invité et soit connecté en tant qu’invité au client invité.<br>
<sup>2</sup> Uniquement par adresse e-mail ou SIP (Session Initiation Protocol).<br>
<sup>3</sup> La conversation externe (fédérée) est 1:1 uniquement.<br>
<sup>4</sup> Fonction prise en charge pour la conversation 1:1 entre utilisateurs Teams uniquement de deux organisations différentes. *Ceci est une préversion ou une fonctionnalité d'une publication anticipée.*

## <a name="related-topics"></a>Voir aussi

[Accès externe dans Teams](manage-external-access.md)

[Accès invité dans Teams](guest-access.md)

