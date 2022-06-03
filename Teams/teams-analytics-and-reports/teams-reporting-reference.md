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
description: Dans cet article, vous allez découvrir les rapports Teams disponibles dans le Centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0891b9267039d8c07d437cb8e67eb2b982a0016
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883547"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Analyses et rapports Microsoft Teams

Une nouvelle expérience d’analytique et de création de rapports pour Microsoft Teams est disponible dans le Centre d’administration Microsoft Teams. Vous pouvez exécuter différents rapports pour obtenir des insights sur la façon dont les utilisateurs de votre organisation utilisent Teams. Par exemple, vous pouvez voir le nombre d’utilisateurs qui communiquent par le biais de messages de canal et de conversation, ainsi que les types d’appareils qu’ils utilisent pour se connecter à Teams. Votre organisation peut utiliser les informations des rapports pour mieux comprendre les modèles d’utilisation, prendre des décisions métier et orienter les efforts de formation et de communication.

## <a name="how-to-access-the-reports"></a>Comment accéder aux rapports

Pour accéder aux rapports, vous devez être administrateur général dans Microsoft 365 ou Office 365, lecteur général dans Microsoft 365 ou Office 365, administrateur du service Teams ou administrateur Skype Entreprise. Pour en savoir plus sur les rôles d’administrateur Teams et les rapports auxquels chaque rôle d’administrateur peut accéder, consultez [Utiliser les rôles d’administrateur Teams pour gérer Teams](../using-admin-roles.md).

Accédez au Centre d’administration Microsoft Teams, dans le volet de navigation de gauche, sélectionnez **Analyse & rapports**, puis, sous **Afficher les rapports**, choisissez le rapport que vous souhaitez exécuter.

> [!NOTE]
> Les rapports dans le Centre d’administration Microsoft Teams sont distincts des rapports d’activité pour Teams qui font partie des rapports Microsoft 365 dans le Centre d’administration Microsoft 365. Pour plus d’informations sur les rapports d’activité dans le Centre d’administration Microsoft 365, consultez [les rapports d’activité Teams dans le Centre d’administration Microsoft 365](../teams-activity-reports.md)

## <a name="teams-reporting-reference"></a>Informations de référence sur les rapports Teams

Voici une liste des rapports Teams disponibles dans le Centre d’administration Microsoft Teams et une vue d’ensemble de certaines des informations disponibles dans chaque rapport.

Nous améliorons continuellement l’expérience de création de rapports Teams et ajoutons des fonctionnalités et des fonctionnalités. Au fil du temps, nous allons créer des fonctionnalités supplémentaires dans les rapports et ajouter de nouveaux rapports dans le Centre d’administration Microsoft Teams.

|Rapport  |Quelles données sont mesurées ? |
|---------|---------|
|[Rapport d’utilisation Teams](teams-usage-report.md)  |  Utilisateurs actifs<br/>Utilisateurs actifs dans les équipes et les canaux<br/>Canaux actifs<br/>Messages<br/>Paramètre de confidentialité des équipes<br/>Invités d’une équipe   |
|[Rapport d’activité d’utilisateur Teams](user-activity-report.md)  | Messages qu’un utilisateur a publiés dans une conversation d’équipe<br/>Messages qu’un utilisateur a publiés dans une conversation privée<br/>  1:1 appelle un utilisateur qui a participé à<br/> Nombre de réunions organisées par l’utilisateur <br/>Nombre de réunions aux cours aux cours des utilisateurs<br/>Temps de partage audio, vidéo et d’écran des réunions<br/>   Date de la dernière activité d’un utilisateur     |
|[Rapport d’utilisation Teams sur des périphériques](device-usage-report.md)   |  Utilisateurs Windows<br/>Utilisateurs Mac<br/>Utilisateurs iOS<br/>Utilisateurs de téléphone Android     |
|[Rapport d’utilisation des événements en direct Teams](teams-live-event-usage-report.md)   |  Nombre total de vues<br>Heure de début<br>État de l’événement<br>Organisateur<br>Présentateur<br>Producteur<br>Paramètre d’enregistrement<br>Type de production    |
|[Rapport des utilisateurs bloqués rtc Teams](pstn-blocked-users-report.md)   |  Nom d’affichage<br>Numéro de téléphone<br>Raison<br>Type d’action<br>Date et heure de l’action   |
|[Rapport des pools de minutes RTC Teams](pstn-minute-pools-report.md) |  Pays ou région<br>Fonctionnalité (licence) <br>Nombre total de minutes<br>Minutes utilisées<br>Minutes disponibles|
|[Rapport d’utilisation rtc Teams - Forfaits d’appels](pstn-usage-report.md#calling-plans)|  Horodatage<br>Nom d'utilisateur<br>Numéro de téléphone<br>Type d’appel <br>Appelé à<br>Vers le pays ou la région <br>Appelé à partir de <br>À partir d’un pays ou d’une région<br>Frais<br>Devise<br>Durée<br>National/International<br>ID d’appel<br>Type de nombre<br>Pays ou région<br>ID de conférence<br>Fonctionnalité (licence)|
|[Rapport d’utilisation rtc Teams - Routage direct](pstn-usage-report.md#direct-routing)  |  Horodatage<br>Nom d’affichage<br>Adresse SIP<br>Numéro de téléphone <br>Type d’appel<br>Appelé à<br>Heure de début<br>Heure d’invitation<br>Temps d’échec<br>Heure de fin<br>Durée<br>Type de nombre<br>Contournement de média<br>Nom de domaine complet SBC<br>Région Azure<br>Type d’événement<br>Code SIP final<br>Sous-code Microsoft final<br>Phrase SIP finale<br>ID de corrélation  |
|[Rapport de licence de protection des informations Teams](information-protection-license-report.md)  | <br>Indique si les utilisateurs disposent de licences valides pour envoyer leurs messages via des notifications de modification</br><br>Nombre total d’événements de notification de modification déclenchés par un utilisateur<br><br>Les applications qui écoutent les événements de notification de modification à l’échelle de l’organisation<br>|
|[Rapport d’utilisation des visites virtuelles Teams](virtual-visits-usage-report.md)  | Nombre de rendez-vous virtuels<br>Nombre de rendez-vous Bookings<br>Nombre de rendez-vous intégrés aux dossiers de santé électroniques Teams (DSE)<br>Durée moyenne d’un rendez-vous<br>Temps d’attente moyen des participants dans la salle d’attente<br>Heure de début<br>ID de réunion<br>Temps d’attente de la salle d’attente<br>Durée<br>Statut<br>Type de produit<br>Participants<br>SMS envoyés
|[Rapport des rendez-vous virtuels du connecteur DSE Teams](../expand-teams-across-your-org/healthcare/ehr-admin-reports.md) | Heure de début<br>Durée<br>Principal (nom de l’organisateur de la réunion)<br>E-mail du principal (e-mail de l’organisateur de la réunion)<br>Service<br>Préposés<br>Temps d’attente de la salle d’attente<br>Indique si le rendez-vous est dans la limite d’allocation
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour rendre les données dans l’activité des utilisateurs Teams et le rapport d’utilisation des appareils Teams anonymes, vous devez être administrateur général. Cela masque les informations identifiables telles que le nom d’affichage, l’e-mail et l’ID Microsoft Azure Active Directory dans les rapports et leurs exportations.

1. Dans le Centre d’administration Microsoft 365, accédez à **Paramètres de l’organisation Paramètres** \> et, sous **l’onglet Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis choisissez **d’afficher les noms d’utilisateur, de groupe et de site masqués dans tous les rapports**. Ce paramètre est appliqué à la fois aux rapports d’utilisation dans le Centre d’administration Microsoft 365 et au Centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.

> [!NOTE]
> L’activation de ce paramètre dé-identifie les informations dans le [rapport d’activité des utilisateurs Teams](user-activity-report.md) et les rapports [d’utilisation des appareils Teams](device-usage-report.md) . Cela n’affecte pas les autres rapports d’utilisation disponibles dans le Centre d’administration Teams.
> Ce paramètre s’applique également aux rapports d’utilisation de Microsoft 365 dans le Centre d’administration Microsoft 365, Microsoft Graph et Power BI.
