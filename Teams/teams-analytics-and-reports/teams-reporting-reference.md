---
title: Analyses et rapports Microsoft Teams
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
- ms.teamsadmincenter.analyticsandreports.overview
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Dans cet article, vous allez découvrir les Teams disponibles dans le Microsoft Teams d’administration.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 807b4e545580cf54b762aacfccde47992d508f82
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046060"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Analyses et rapports Microsoft Teams

Une nouvelle expérience d’analyse et de rapport pour Microsoft Teams est disponible dans le Centre Microsoft Teams’administration. Vous pouvez exécuter différents rapports pour obtenir des informations sur la façon dont les utilisateurs de votre organisation utilisent Teams. Par exemple, vous pouvez voir combien d’utilisateurs communiquent par le biais de messages de canal et de conversation, ainsi que les types d’appareils qu’ils utilisent pour se connecter à Teams. Votre organisation peut utiliser les informations des rapports pour mieux comprendre les modèles d’utilisation, aider à prendre des décisions professionnelles et informer les efforts de formation et de communication.

## <a name="how-to-access-the-reports"></a>Comment accéder aux rapports

Pour accéder aux rapports, vous devez être un administrateur global dans Microsoft 365 ou Office 365, un lecteur global dans Microsoft 365 ou Office 365, un administrateur de service Teams ou un administrateur de Skype Entreprise. Pour en savoir plus sur Teams rôles d’administrateur et les rapports auquel chaque rôle d’administrateur peut accéder, voir Utiliser Teams rôles d’administrateur pour [gérer les Teams.](../using-admin-roles.md)

Dans le Microsoft Teams d’administration, dans le panneau de navigation de gauche, sélectionnez Analyse **&** rapports, puis sous Afficher les **rapports,** sélectionnez le rapport que vous voulez exécuter.

> [!NOTE]
> Les rapports du Microsoft Teams d’administration sont différents des rapports d’activité Teams qui font partie des rapports Microsoft 365 dans le Centre d'administration Microsoft 365. Pour plus d’informations sur les rapports d’activité du Centre d'administration Microsoft 365, voir Teams [rapports d’activité dans le Centre d'administration Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Teams référence de rapport

Voici une liste des rapports Teams disponibles dans le Centre d’administration Microsoft Teams et une vue d’ensemble de certaines des informations disponibles dans chaque rapport.

Nous améliorons continuellement l’expérience de Teams en matière de rapports et d’ajout de fonctionnalités. Au fil du temps, nous allons créer des fonctionnalités supplémentaires dans les rapports et ajouter de nouveaux rapports dans le Microsoft Teams d’administration.

|Rapport  |Quelles données sont mesurées ? |
|---------|---------|
|[Rapport d’utilisation Teams](teams-usage-report.md)  |  Utilisateurs actifs<br/>Utilisateurs actifs dans les équipes et les canaux<br/>Canaux actifs<br/>Messages<br/>Paramètre de confidentialité des équipes<br/>Invités dans une équipe   |
|[Rapport d’activité d’utilisateur Teams](user-activity-report.md)  | Messages publiés par un utilisateur dans une conversation d’équipe<br/>Messages publiés par un utilisateur dans une conversation privée<br/>  Appels 1:1 pour participation d’un utilisateur<br/> Nombre d’utilisateurs de la réunion organisés <br/>Nombre d’utilisateurs ayant participé à la réunion<br/>Durée de partage audio, vidéo et écran des réunions<br/>   Date de dernière activité d’un utilisateur     |
|[Rapport d’utilisation Teams sur des périphériques](device-usage-report.md)   |  Utilisateurs Windows<br/>Utilisateurs Mac<br/>Utilisateurs d’iOS<br/>Utilisateurs de téléphones Android     |
|[Rapport d’utilisation des événements en direct Teams](teams-live-event-usage-report.md)   |  Nombre total de vues<br>Heure de début<br>Statut de l’événement<br>Organisateur<br>Présentateur<br>Producteur<br>Paramètre d’enregistrement<br>Type de production    |
|[Teams Rapport sur le blocage d’utilisateurs PSTN](pstn-blocked-users-report.md)   |  Nom d’affichage<br>Téléphone numéro<br>Raison<br>Type d’action<br>Date et heure de l’action   |
|[Teams Rapport sur les pools de minutes PSTN](pstn-minute-pools-report.md) |  Pays ou région<br>Fonctionnalité (licence) <br>Nombre total de minutes<br>Minutes utilisées<br>Minutes disponibles|
|[Teams Rapport d’utilisation PSTN - Forfaits d’appels](pstn-usage-report.md#calling-plans)|  Horodament<br>Nom d'utilisateur<br>Téléphone numéro<br>Type d’appel <br>Appelé à<br>Pour le pays ou la région <br>Appelé depuis <br>À partir du pays ou de la région<br>Charge<br>Devise<br>Durée<br>Nationaux/Internationaux<br>ID d’appel<br>Type de nombre<br>Pays ou région<br>ID de conférence<br>Fonctionnalité (licence)|
|[Teams Rapport d’utilisation PSTN - Routage direct](pstn-usage-report.md#direct-routing)  |  Horodament<br>Nom d’affichage<br>Adresse SIP<br>Téléphone numéro <br>Type d’appel<br>Appelé à<br>Heure de début<br>Heure d’invitation<br>Heure d’échec<br>Heure de fin<br>Durée<br>Type de nombre<br>Contournement de média<br>SBC FQDN<br>Région Azure<br>Type d’événement<br>Code SIP final<br>Sous-code Microsoft final<br>Phrase SIP finale<br>ID de corrélation  |
|[Teams de licence de protection des informations](information-protection-license-report.md)  | <br>Si les utilisateurs ont des licences valides pour envoyer leurs messages via des notifications de modification</br><br>Nombre total d’événements de notification de modification déclenchés par un utilisateur</br><br>Quelles applications écoutent les événements de notification de modification à l’échelle de l’organisation ?</br>|


[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour anonymisation des données Teams’activité des utilisateurs et Teams’utilisation de l’appareil, vous devez être administrateur général. Cela a pour effet de masquer les informations identifiables telles que le nom d’affichage, le courrier électronique et l’ID AAD dans les rapports et leurs exportations.

1. Dans Centre d'administration Microsoft 365, sélectionnez  l’Paramètres Paramètres organisation, puis sous l’onglet \>  **Services,** sélectionnez **Rapports.**
    
2. Sélectionnez **Rapports,** puis choisissez **d’afficher les identificateurs anonymes.** Ce paramètre est appliqué aux rapports d’utilisation dans Centre d'administration Microsoft 365 ainsi qu’Teams centre d’administration.
  
3. Sélectionnez **Enregistrer les modifications.**

> [!NOTE]
> L’activation de ce paramètre a pour Teams [rapports](user-activity-report.md) d’activité des utilisateurs et les Teams [d’utilisation des](device-usage-report.md) appareils. Cela n’affecte pas les autres rapports d’utilisation disponibles Teams centre d’administration.
