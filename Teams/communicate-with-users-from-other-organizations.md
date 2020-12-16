---
title: Appel et conversation avec des utilisateurs d’autres organisations
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment appeler, discuter, rechercher, et ajouter des utilisateurs en dehors de l’organisation dans Microsoft Teams à l’aide de l’accès externe (fédération) et de l’accès invité.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031810"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a>Appeler et discuter avec des utilisateurs d’autres organisations dans Microsoft Teams
======================================================

Lorsque vous avez besoin de communiquer et de collaborer avec des personnes extérieures à votre organisation, Microsoft Teams vous propose deux solutions. La première est l’**accès externe** (fédération) qui permet de rechercher, d’appeler et de discuter avec des utilisateurs dans d’autres domaines (comme, par exemple, contoso.com). La deuxième, l’**accès invité**, vous permet d’ajouter des utilisateurs à vos équipes en tant qu’invités, à l’aide de leur adresse de messagerie. Vous pouvez collaborer avec des invités comme vous le feriez avec d’autres utilisateurs au sein de votre organisation.

Si vous le souhaitez, vous pouvez utiliser l’accès externe et l’accès invité ; l’un n’exclut pas l’autre.

À un niveau élevé, voici comment choisir (pour une comparaison détaillée, voir [Comparer l’accès externe et l’accès invité](#compare-external-and-guest-access)) :

## <a name="external-access"></a>Accès externe

Utilisez l’**accès externe** (fédération) lorsque vous avez besoin de permettre aux utilisateurs externes d’autres domaines de rechercher, appeler, discuter et configurer des réunions avec vous. Les utilisateurs externes ne peuvent pas accéder aux équipes ou aux ressources des équipes de votre organisation. Sélectionnez l’accès externe lorsque vous voulez communiquer avec des utilisateurs externes à votre organisation qui utilisent encore Skype Entreprise (en ligne ou en local) ou Skype (disponible début 2020). 

L’accès externe est activé par défaut dans Teams, ce qui signifie que votre organisation peut communiquer avec tous les domaines externes. L’administrateur Teams peut le désactiver ou spécifier les domaines à inclure (ou à exclure). Pour plus d’informations, consultez [Gérer les accès externes](manage-external-access.md). 

Si vous voulez que les utilisateurs externes aient accès aux équipes et aux canaux, [l’accès invité](#guest-access) sera sans doute préférable. 


## <a name="guest-access"></a>Accès invité

Utilisez l’**accès invité** pour ajouter un utilisateur individuel (quel que soit son domaine) à une équipe dans laquelle il pourra discuter, appeler, rencontrer et collaborer sur des fichiers de l’organisation (stockés dans SharePoint ou OneDrive Entreprise) à l’aide des applications Microsoft 365 ou Office 365 telles que Word, Excel ou PowerPoint. Les utilisateurs invités peuvent bénéficier de presque toutes les mêmes fonctionnalités Teams qu’un membre natif de l’équipe. Pour plus d’informations, consultez [Accès invité dans Teams](guest-access.md).

- Les invités sont ajoutés dans l’annuaire Active Directory de votre organisation.
- Pour communiquer avec un invité, celui-ci doit être connecté à Teams à l’aide de son compte invité. L’invité devra donc peut-être se déconnecter de son compte Teams pour pouvoir se connecter à votre compte Teams, ou changer d’organisation s’il s’agit du même compte.
- Les utilisateurs invités ont accès à davantage de ressources dans Teams, par exemple, des fichiers, des équipes et des canaux, que des utilisateurs disposant d’un accès externe (fédéré).
- L’administrateur Teams contrôle tout ce qu’un invité peut faire (ou ne peut pas faire) dans le centre d’administration Teams. Pour plus d’informations, consultez [Gérer l’accès invité](manage-guests.md).

Si vous êtes prêt à activer l’accès invité au sein de votre organisation, commencez par [Collaborer avec des invités au sein d’une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).


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
| Afficher le numéro de téléphone des participants à la réunion rendez-vous | Non<sup>5</sup> | Oui |
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
<sup>4</sup> Fonction prise en charge pour la conversation 1:1 entre utilisateurs Teams uniquement de deux organisations différentes. <br>
<sup>5</sup> Par défaut, les participants externes ne peuvent pas voir les numéros de téléphone des participants distants. Si vous voulez conserver la confidentialité de ces numéros de téléphone, sélectionnez **Tonalités** pour le **Type d’annonce d’entrée et de sortie** (cela permet d’éviter que les numéros soient lus par les Teams). Pour plus d’informations, consultez [Activer ou désactiver les annonces d’entrée et de sortie pour les réunions dans Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).

## <a name="related-topics"></a>Voir aussi

[Accès externe dans Teams](manage-external-access.md)

[Accès invité dans Teams](guest-access.md)

