---
title: Interface utilisateur pour les invités dans Microsoft teams
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
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Cet article décrit les fonctionnalités de Microsoft teams disponibles aux utilisateurs invités.
ms.openlocfilehash: 95d0fec7a1af8f735c66cc76fc27ecd3cf8bf956
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346205"
---
# <a name="guest-experience-in-teams"></a>Convivialité dans teams

Lorsqu’un invité est invité à rejoindre une équipe, il reçoit un message électronique de bienvenue. Ce message inclut des informations sur l’équipe et ce à quoi vous devez vous attendre. L’invité doit accepter l’invitation en sélectionnant **Ouvrir Microsoft teams** dans le message électronique avant de pouvoir accéder à l’équipe et à ses canaux.
    
![Capture d’écran montrant un exemple de message électronique de bienvenue](media/guest-experience-image1.png)
    
Tous les membres de l'équipe voient un message dans le fil des canaux informant que le propriétaire de l'équipe a ajouté un invité et indiquant son nom. Tous les membres de l'équipe peuvent identifier facilement les utilisateurs qui sont invités. Une balise située dans le coin supérieur droit du thread de canal indique le nombre d’invités figurant sur l’équipe et **l’étiquette de l’invité située** en regard du nom de chaque invité.

![Capture d’écran montrant un indicateur indiquant le nombre d’invités dans l’équipe](media/guest-experience-image2.png)

Regardez ces vidéos sur l’interface de l’invité dans teams :
- [Rejoindre une équipe en tant qu’invité](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Rejoindre une réunion en équipe avec des invités](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>Comparaison entre le membre d’équipe et les fonctionnalités d’invité

Le tableau suivant compare les fonctionnalités d’équipes disponibles pour les membres de l’équipe d’une organisation et ses invités. Les administrateurs d’équipes contrôlent les fonctionnalités disponibles pour les invités.

|**Fonctionnalité dans Teams**|**Utilisateur de Teams dans l'organisation**|**Utilisateur invité**|
|:-----|:-----|:-----|
|Créer un canal  <br/>  *Les propriétaires d'équipe contrôlent ce paramètre.*  <br/> |&#x2713;|&#x2713;|
|Participer à une conversation privée  <br/> |&#x2713;|&#x2713;|
|Participer à une conversation dans un canal  <br/> |&#x2713;|&#x2713;|
|Publier, supprimer et modifier des messages  <br/> |&#x2713;|&#x2713;|
|Partager un fichier dans un canal  <br/> |&#x2713;|&#x2713;|
|Accéder aux fichiers SharePoint<br/> |&#x2713;|&#x2713;|
|Joindre des fichiers<br/> |&#x2713;|&#x2713;|
|Télécharger des fichiers de conversation privée<br/> |&#x2713;|&#x2713;|
|Effectuer une recherche dans les fichiers<br/> |&#x2713;||
|Partager un fichier dans une conversation  <br/> |&#x2713;||
|Ajouter des applications (onglets, bots ou connecteurs)  <br/> |&#x2713;||
|Créer des réunions ou des échéanciers d’accès  <br/> |&#x2713;||
|Accès au stockage OneDrive entreprise  <br/> |&#x2713;||
|Créer des stratégies d'accès invité qui s'appliquent à l'ensemble du client et aux équipes/canaux  <br/> |&#x2713;||
|Inviter un utilisateur en dehors du domaine de l’organisation Microsoft 365 ou Office 365 <br/>  *Les propriétaires d'équipe contrôlent ce paramètre.*  <br/> <br/> |&#x2713;||
|Créer une équipe  <br/> |&#x2713;||
|Rechercher et rejoindre une équipe publique  <br/> |&#x2713;||
|Afficher l'organigramme  <br/> |&#x2713;||
|Utiliser la traduction intraligne  <br/> |&#x2713;||
|Devenir le propriétaire de l’équipe  <br/> |&#x2713;||

Le tableau suivant répertorie les fonctionnalités d’appel et de réunion accessibles aux invités par rapport aux autres types d’utilisateurs.

| Fonction d’appel | Dactylo | Utilisateurs E1 et E3 | E5 et utilisateur voix entreprise |
| --------------- | ----- | -------------- | -------------- |
| Appels VOIP | Oui | Oui | Oui |
| Appels de groupe | Oui | Oui | Oui |
| Commandes d’appel principales prises en charge (mise en attente, muet, vidéo activées, partage d’écran) | Oui | Oui | Oui |
| Destination du transfert | Oui | Oui | Oui |
| Peut transférer un appel | Oui | Oui | Oui |
| Possibilité de transférer des conseils | Oui | Oui | Oui |
| Peut ajouter d’autres utilisateurs à un appel via le protocole VOIP | Oui | Oui | Oui |
| Peut ajouter des utilisateurs par numéro de téléphone à un appel | Non | Non | Oui |
| Destination directe | Non | Oui | Oui |
| Cible du groupe d’appels | Non | Oui | Oui |
| Cible sans réponse | Non | Oui | Oui |
| Peut être la cible d’un appel fédéré | Non | Oui | Oui |
| Possibilité d’effectuer un appel fédéré | Non | Oui | Oui |
| Peut immédiatement transférer ses appels | Non | Non | Oui |
| Peuvent sonner simultanément dans leurs appels | Non | Non | Oui |
| Peut acheminer les appels sans réponse | Non | Non | Oui |
| Les appels en absence peuvent être dirigés vers la boîte vocale | Non | No<sup>1</sup> |Oui |
| Avoir un numéro de téléphone capable de recevoir des appels | Non | Non | Oui |
| Peut composer des numéros de téléphone | Non | Non | Oui |
| Peut accéder aux paramètres de l’appel | Non | Non | Oui |
| Peut changer le message d’accueil de la boîte vocale | Non | No<sup>1</sup> | Oui |
| Possibilité de modifier les sonneries | Non | Non  | Oui |
| Prend en charge TTY | Non | Non | Oui |
| Peuvent avoir des délégués | Non | Non | Oui |
|  Il peut s’agir d’un délégué | Non | Non | Oui |

<sup>1</sup> cette fonction sera disponible prochainement.

> [!NOTE]
> La stratégie de **restrictions d’accès des utilisateurs invités** dans Azure Active Directory (Azure AD) détermine les autorisations relatives aux invités dans votre annuaire. Trois options de stratégie sont disponibles.
>  - Le paramètre **Les utilisateurs invités ont le même accès que les membres (le plus inclusif)** signifie que les invités disposent du même accès aux données d’annuaires que les utilisateurs réguliers dans votre annuaire.
>  - Le paramètre **Les utilisateurs invités ont un accès limité aux propriétés et à l’appartenance des objets d’annuaire** signifie que les invités n’ont pas d’autorisations pour certaines tâches d’annuaire, telles que l’énumération des utilisateurs, des groupes ou d’autres ressources d’annuaire à l’aide de Microsoft Graph.
>  - Le paramètre **L’accès des utilisateurs invités est limité aux propriétés et aux appartenances de leurs propres objets d’annuaire (le plus restrictif)** signifie que les invités peuvent uniquement accéder à leurs propres objets d’annuaire.
>
>Pour plus d’informations, voir [Quelles sont les autorisations par défaut de l’utilisateur dans Azure Active Directory ?](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>Sujets associés

[Laisser une organisation en tant qu’utilisateur invité](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)