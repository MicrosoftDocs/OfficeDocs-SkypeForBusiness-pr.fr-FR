---
title: Expérience de l’invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Cette article décrit la fonctionnalité Microsoft Teams disponible pour les invités.
ms.openlocfilehash: 25ea63de9bcdc85e0f7b81e382c2c9bcd057c629
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661889"
---
# <a name="guest-experience-in-teams"></a>Expérience de l’invité dans Microsoft Teams

Lorsqu'un invité est convié à rejoindre une équipe, il reçoit un e-mail de bienvenue. Le message inclut des informations sur l'équipe et explique ce à quoi s’attendre maintenant qu'il est membre. L’invité doit accepter l’invitation en sélectionnant **Ouvrir Microsoft Teams** dans l’e-mail avant de pouvoir accéder à l'équipe et à ses canaux.
    
![Capture d’écran affichant un exemple d’e-mail de bienvenue](media/guest-experience-image1.png)
    
Tous les membres de l'équipe voient un message dans le fil des canaux informant que le propriétaire de l'équipe a ajouté un invité et indiquant son nom. Tous les membres de l'équipe peuvent identifier facilement les utilisateurs qui sont invités. Une balise dans le coin supérieur droit du thread de canal indique le nombre d’invités de l’équipe et une étiquette **(Invité)** apparaît près du nom de chaque invité.

![Capture d’écran affichant la balise qui indique le nombre d’invités de l’équipe](media/guest-experience-image2.png)

Découvrez ces vidéos sur l’expérience de l’invité dans Teams :
- [Rejoindre une équipe en tant qu’invité](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Rejoindre une réunion Teams avec des invités](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Comparaison des fonctionnalités d’un membre de l’équipe et d’un invité

Le tableau suivant compare la fonctionnalité Teams disponible pour les membres d’une équipe dans une organisation et ses invités. Les administrateurs Teams contrôlent les fonctionnalités disponibles pour les invités.

| Fonctionnalité dans Teams | Utilisateur Teams dans l'organisation | Invité |
|:-----|:-----|:-----|
|Créer un canal  <br/>  *Les propriétaires d'équipe contrôlent ce paramètre.*  <br/> |&#x2713;|&#x2713;|
|Participer à une conversation privée  <br/> |&#x2713;|&#x2713;|
|Participer à une conversation dans un canal  <br/> |&#x2713;|&#x2713;|
|Publier, supprimer et modifier des messages  <br/> |&#x2713;|&#x2713;|
|Partager un fichier du canal  <br/> |&#x2713;|&#x2713;|
|Accéder aux fichiers SharePoint<br/> |&#x2713;|&#x2713;|
|Joindre des fichiers<br/> |&#x2713;|Conversations d’équipe uniquement|
|Télécharger des fichiers de conversation privés<br/> |&#x2713;|&#x2713;|
|Effectuer une recherche dans des fichiers<br/> |&#x2713;||
|Partager un fichier de conversation  <br/> |&#x2713;||
|Ajouter des applications (onglets, bots ou connecteurs)  <br/> |&#x2713;||
|Créer des réunions ou accéder à des plannings  <br/> |&#x2713;||
|Accéder au stockage OneDrive Entreprise  <br/> |&#x2713;||
|Créer des stratégies d'accès invité aux canaux/équipes et au niveau du client  <br/> |&#x2713;||
|Inviter un utilisateur extérieur au domaine Microsoft 365 ou Office 365 de l’organisation <br/>  *Les propriétaires d'équipe contrôlent ce paramètre.*  <br/> <br/> |&#x2713;||
|Créer une équipe  <br/> |&#x2713;||
|Découvrir et rejoindre une équipe publique  <br/> |&#x2713;||
|Afficher l'organigramme  <br/> |&#x2713;||
|Utiliser la traduction associée  <br/> |&#x2713;||
|Devenir un propriétaire d’équipe  <br/> |&#x2713;||

Le tableau suivant affiche les fonctionnalités d’appel et de réunion disponibles pour les invités par rapport à d’autres types d’utilisateurs.

| Fonctionnalités d'appel | Invité | Utilisateur E1 et E3 | Utilisateur vocal Entreprise et E5 |
| --------------- | ----- | -------------- | -------------- |
| Appel VOIP | Oui | Oui | Oui |
| Appel de groupe | Oui | Oui | Oui |
| Principaux contrôles d’appel pris en charge (mettre en attente, désactiver le son, activer/désactiver la vidéo, partage d’écran) | Oui | Oui | Oui |
| Transférer la cible | Oui | Oui | Oui |
| Peut transférer un appel | Oui | Oui | Oui |
| Peut effectuer un transfert consultatif | Oui | Oui | Oui |
| Peut ajouter d’autres utilisateurs à un appel via VOIP | Oui | Oui | Oui |
| Peut ajouter des utilisateurs à un appel via un numéro de téléphone | Non | Non | Oui |
| Transférer la cible | Non | Oui | Oui |
| Appeler la cible du groupe | Non | Oui | Oui |
| Cible sans réponse | Non | Oui | Oui |
| Peut être la cible d’un appel fédéré | Non | Oui | Oui |
| Peut passer un appel fédéré | Non | Oui | Oui |
| Peut immédiatement transférer ses appels | Non | Non | Oui |
| Peut faire sonner simultanément ses appels | Non | Non | Oui |
| Peut acheminer ses appels sans réponse | Non | Non | Oui |
| Les appels manqués peuvent être redirigés vers la messagerie vocale | Non | Non<sup>1</sup> |Oui |
| Dispose d’un numéro de téléphone pouvant recevoir des appels | Non | Non | Oui |
| Peut composer des numéros de téléphone | Non | Non | Oui |
| Peut accéder aux paramètres d’appel | Non | Non | Oui |
| Peut modifier le message d'accueil de la messagerie vocale | Non | Non<sup>1</sup> | Oui |
| Peut changer de sonnerie | Non | Non  | Oui |
| Prend en charge le mode téléscripteur | Non | Non | Oui |
| Peut avoir des délégués | Non | Non | Oui |
|  Peut être un délégué | Non | Non | Oui |

<sup>1</sup> Cette fonctionnalité sera bientôt disponible.

> [!NOTE]
> **Restrictions de l’accès des utilisateurs invités** : stratégie dans Azure Active Directory qui détermine les autorisations pour les invités de votre annuaire. Trois options de stratégie sont disponibles.
>  - Le paramètre **Les utilisateurs invités ont le même accès que les membres (le plus inclusif)** signifie que les invités disposent du même accès aux données d’annuaires que les utilisateurs réguliers dans votre annuaire.
>  - Le paramètre **Les utilisateurs invités ont un accès limité aux propriétés et à l’appartenance des objets d’annuaire** signifie que les invités n’ont pas d’autorisations pour certaines tâches d’annuaire, telles que l’énumération des utilisateurs, des groupes ou d’autres ressources d’annuaire à l’aide de Microsoft Graph.
>  - Le paramètre **L’accès des utilisateurs invités est limité aux propriétés et aux appartenances de leurs propres objets d’annuaire (le plus restrictif)** signifie que les invités peuvent uniquement accéder à leurs propres objets d’annuaire.
>
>Pour plus d’informations, voir [Quelles sont les autorisations par défaut de l’utilisateur dans Azure Active Directory ?](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>Sujets associés

[Quitter une organisation en tant qu’invité](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)
