---
title: Planifier des événements en direct dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Découvrez les facteurs à prendre en compte avant de configurer des événements en temps réel dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 590246808849b2cf25bdc0fb114352977973410f
ms.sourcegitcommit: a0f2feb5d826fbb4414ac6644fdc3b65bbe224f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2018
ms.locfileid: "27156132"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>Planifier des événements en direct dans Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Lorsque vous planifiez les événements en direct équipes destiné à contenir des grandes réunions dans votre organisation, il existe plusieurs facteurs que vous devez prendre en compte avant de commencer à définir ascendants. 

## <a name="who-can-create-and-schedule-live-events"></a>Qui peut créer et planifier les événements live ? 
Les conditions préalables suivantes sont requises pour l’utilisateur planifier un événement live équipes.

Voici les licences qui doivent être affectés :  
- Une licence Office 365 entreprise E1, E3 ou E5 ou une licence Office 365 A3 ou A5. 
- Un Teams Microsoft, les Skype pour les entreprises et de licence Microsoft Stream.

Il est important de savoir qu’une licence Office 365 est nécessaire pour participer à un événement live en tant qu’utilisateur authentifié mais cela dépend de la méthode de production utilisée :

- **Production de début pour rapide**  L’utilisateur doit être affecté à une licence Microsoft Teams.
- **Production d’encodeur pour externe** L’utilisateur doit être affecté à une licence Microsoft Stream.

Pour plus d’informations sur les licences, voir [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).

L’utilisateur doit avoir :
- Planifier des réunions privées dans les équipes activés (*- AllowPrivateMeetingScheduling TeamsMeetingPolicy le paramètre = True*).
- Live planification d’événements dans les équipes activés (*- AllowBroadcastScheduling TeamsMeetingBroadcastPolicy le paramètre = True*).
- Autorisations pour créer des événements en temps réel dans Microsoft Stream (pour la [production de codage externe](#production)).

> [!IMPORTANT]
> Office 365 invités, les utilisateurs fédérés et anonymes ne peuvent pas être invitées en tant que producteurs ou présentateurs dans les événements live équipes. Invité Office 365 et les utilisateurs fédérés peuvent regarder uniquement anonymement événements en direct. 
 
## <a name="who-can-watch-live-events"></a>Qui peut voir les événements en direct ?

|**Visibilité de participant**       |**Guide de démarrage rapide**  |**Codage externe**  |
|------------------------------|-----------------|----------------------|
|Public (utilisateurs anonymes)      |  Oui            |  Non                  |
|Utilisateurs invités                   |  Aucun<sup>1</sup> |  Non                  |
|Tout le monde dans une entreprise fédérée |  Aucun<sup>1</sup> |  Non                  |
|Tout le monde de société           |  Oui            |  Oui                 |
|Propres groupes / personnes      |  Oui            |  Oui                 |

<sup>1</sup> peut surveiller uniquement les événements en direct en tant qu’utilisateurs anonymes.

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Événements en direct équipes et la diffusion de réunion Skype
Le tableau suivant met en évidence les fonctionnalités principales et les fonctionnalités offertes par les événements en direct et les différences entre la diffusion de réunion Skype. 

|**Fonctionnalité**   |**Diffusion de réunion Skype** |**Événements live équipes (démarrage rapide)** |**Événements live équipes (codage externe)** |
|---------|---------|---------|---------|
|Taille maximale d’audience |10 000 participants |10 000 participants * |10 000 participants * |
|Durée maximale d’événement en direct |4 heures |4 heures |4 heures |
|Création de l’événement en direct |   Portail du service de diffusion de réunion de Skype |Les équipes, Yammer via des équipes | Les équipes, Yammer via des équipes de flux |
|Engagement de l’audience – Yammer |& #x 2714 ; |& #x 2714 ; (expérience intégrée) |& #x 2714 ; (expérience intégrée) |
|Engagement de l’audience – modéré de Q & r |& #x 2714 ;  |& #x 2714 ; |& #x 2714 ; |
|Client producteur sur Windows |& #x 2714 ; (Skype pour les entreprises) |& #x 2714 ; (Équipes) |& #x 2714 ; (Incorporer des équipes via le flux de flux) |
|Client producteur sur Mac |X  | & #x 2714 ; (Équipes) |& #x 2714 ; (Incorporer des équipes via le flux de flux) |
|Nombre de participants dans l’interface utilisateur producteur |X  |& #x 2714 ; (Équipes) |& #x 2714 ; (Incorporer des équipes via le flux de flux) |
|Permet à plusieurs présentateurs |& #x 2714 ; (Skype pour les entreprises) |& #x 2714 ; (Équipes) |N/A  |
Inviter un présentateur au cours de la réunion |& #x 2714 ; (Skype pour les entreprises) |X |N/A |
|Jointure présentateur sur le Web et Mobile |& #x 2714 ; (Skype pour les entreprises)  |X |N/A |
|Présentateur – accès PSTN |X |& #x 2714 ; (Équipes) |N/A |
|Présenter un écran |X |& #x 2714 ; (Équipes) |N/A |
|Présenter un fichier PowerPoint (PPT partage) |& #x 2714 ; |X (atténué via le partage d’écran) |N/A |
|Enregistrement de la réunion en fonction de nuage |& #x 2714 ; |& #x 2714 ; |& #x 2714 ; |
|Automatique publier un enregistrement dans le flux de Microsoft |X |X |& #x 2714 ; |
|Traduction et légendes en temps réel |& #x 2714 ; |& #x 2714 ; (bientôt disponible) |X |
|Légendes dans enregistrements live |& #x 2714 ; |& #x 2714 ; (bientôt disponible) |& #x 2714 ; |
|Contrôles DVR Attendee (pause, arrière) |& #x 2714 ; |& #x 2714 ; |& #x 2714 ; |
|Partenaire eCDN prise en charge |& #x 2714 ; (La ruche, Kollective, Ramp) |& #x 2714 ; (La ruche, Kollective, Ramp) |& #x 2714 ; (La ruche, Kollective, Ramp) |
|Rapport de participation à une diffusion postérieures aux producteurs |& #x 2714 ; |& #x 2714 ; |X |
|Analyse du public ressenti – vote Live et sondages |& #x 2714 ; (Pulse Microsoft) |X |X |

> [!IMPORTANT]
> Les limites définies peuvent être modifiés.

## <a name="regional-availability"></a>Disponibilité régionale
Vous pouvez utiliser événements live équipes dans plusieurs régions du monde. Les informations suivantes affichent la disponibilité pour les participants et les membres de l’équipe événement. 

> [!IMPORTANT]
> La région pour l’événement est automatiquement sélectionnée en fonction de l’organisateur et l’organisation Office 365.

**Disponible dans ces régions.**
- Amérique
- Europe/Afrique
- Asie-Pacifique
- Accédez au Canada Local

**Exclusions et considérations**
- **Accédez variables locales :** Royaume-Uni, en Inde et autres variables atteindre des équipes Microsoft locales ne sont pas pris en charge actuellement.
- **Chine :** Les participants et les membres de l’équipe événement ne sera pas en mesure d’utiliser des événements en direct équipes car Azure CDN n’est pas accessible en Chine. Une solution de contournement consiste à utiliser une connexion VPN, qui obtient le client connecté au CDN via le réseau d’entreprise du client de la société.

## <a name="next-steps"></a>Étapes suivantes
Accédez à [configurer pour les événements live équipes](set-up-for-teams-live-events.md).

### <a name="related-topics"></a>Rubriques connexes
- [Quelles sont les équipes live événements ?](what-are-teams-live-events.md)
- [Configurer des équipes événements en direct](set-up-for-teams-live-events.md)
- [Configurer les paramètres d’événements en direct dans les équipes](configure-teams-live-events.md)

