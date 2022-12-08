---
title: Analyses et rapports Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
- m365initiative-meetings
description: Dans cet article, vous allez découvrir les rapports Teams disponibles dans le centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a688a3356ce31dd478c35082195ace8f6be4d47
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307659"
---
# <a name="microsoft-teams-analytics-and-reporting"></a>Analyses et rapports Microsoft Teams

Une nouvelle expérience d’analytique et de création de rapports pour Microsoft Teams est disponible dans le centre d’administration Microsoft Teams. Vous pouvez exécuter différents rapports pour obtenir des insights sur la façon dont les utilisateurs de votre organisation utilisent Teams. Par exemple, vous pouvez voir combien d’utilisateurs communiquent via des messages de canal et de conversation, ainsi que les types d’appareils qu’ils utilisent pour se connecter à Teams. Votre organisation peut utiliser les informations des rapports pour mieux comprendre les modèles d’utilisation, aider à prendre des décisions métier et informer les efforts de formation et de communication.

## <a name="how-to-access-the-reports"></a>Comment accéder aux rapports

Pour accéder aux rapports, vous devez être administrateur général dans Microsoft 365 ou Office 365, lecteur général dans Microsoft 365 ou Office 365, administrateur de service Teams ou administrateur Skype Entreprise. Pour en savoir plus sur les rôles d’administrateur Teams et sur les rapports auxquels chaque rôle d’administrateur peut accéder, consultez [Utiliser les rôles d’administrateur Teams pour gérer Teams](../using-admin-roles.md).

Accédez au Centre d’administration Microsoft Teams, dans le volet de navigation de gauche, sélectionnez **Analytique & rapports**, puis sous Afficher les **rapports**, choisissez le rapport que vous souhaitez exécuter.

> [!NOTE]
> Les rapports du centre d’administration Microsoft Teams sont distincts des rapports d’activité pour Teams qui font partie des rapports Microsoft 365 dans le Centre d'administration Microsoft 365. Pour plus d’informations sur les rapports d’activité dans le Centre d'administration Microsoft 365, consultez [Microsoft 365 Rapports dans le Centre d’administration](/microsoft-365/admin/activity-reports/activity-reports).

## <a name="teams-reporting-reference"></a>Informations de référence sur les rapports Teams

Voici une liste des rapports Teams disponibles dans le centre d’administration Microsoft Teams dans différents environnements et une vue d’ensemble de certaines des informations disponibles dans chaque rapport.

Nous améliorons continuellement l’expérience de création de rapports Teams et nous ajoutons des fonctionnalités et des fonctionnalités. Au fil du temps, nous allons créer des fonctionnalités supplémentaires dans les rapports et ajouter de nouveaux rapports dans le centre d’administration Microsoft Teams.

|Rapport  |Public |GCC |GCCH |Dod |Quelles données sont mesurées ? |
|---------|---------|---------|---------|---------|---------|
|[Rapport d’utilisation Teams](teams-usage-report.md)  |Oui|Oui|Oui|Oui|  Utilisateurs actifs<br/>Utilisateurs actifs dans les équipes et les canaux<br/>Canaux actifs<br/>Messages<br/>Paramètre de confidentialité des équipes<br/>Invités actifs dans une équipe  <br/>Utilisateurs externes actifs (dans les canaux partagés)<br/>Détails spécifiques au canal partagés au sein d’une équipe (nouveau)|
|[Rapport d’activité d’utilisateur Teams](user-activity-report.md)  |Oui|Oui|Oui|Oui|Utilisateurs internes et externes actifs (dans les canaux partagés)<br/> Messages qu’un utilisateur a publiés dans une conversation d’équipe<br/>Messages publiés par un utilisateur dans une conversation privée<br/>  1:1 appelle un utilisateur a participé à<br/> Nombre de réunions organisées par l’utilisateur <br/>Nombre de réunions à laquelle l’utilisateur a participé<br/>Temps de partage audio, vidéo et écran des réunions<br/>   Date de la dernière activité d’un utilisateur  <br>Interactions de canal partagé d’un utilisateur (nouveau)</br>   |
|[Rapport d’utilisation Teams sur des périphériques](device-usage-report.md)   |Oui|Oui|Oui|Oui|  Utilisateurs Windows<br/>Utilisateurs Mac<br/>Utilisateurs iOS<br/>Utilisateurs de téléphone Android     |
|[Rapport d’utilisation des applications Teams (nouveau)](app-usage-report.md)   |Oui|Oui|Non|Non|  Nombre total d’utilisateurs actifs de l’application<br/>Nombre total d’équipes actives utilisant l’application<br/>Nombre total d’applications installées (nouveau)<br/>Nombre total d’applications inactives <br/>Utilisation totale des applications 1P vs 3P vs LoB (nouveau)     |
|[Rapport d’utilisation des événements en direct Teams](teams-live-event-usage-report.md)   |Oui|Oui|Non|Non|  Nombre total de vues<br>Heure de début<br>État de l’événement<br>Organisateur<br>Présentateur<br>Producteur<br>Paramètre d’enregistrement<br>Type de production    |
|[Rapport des utilisateurs bloqués RTC Teams](pstn-blocked-users-report.md)   |Oui|Oui|Non|Non|  Nom d’affichage<br>Numéro de téléphone<br>Raison<br>Type d’action<br>Date et heure de l’action   |
|[Rapport de pools de minutes RTC Teams](pstn-minute-pools-report.md) |Oui|Oui|Non|Non|  Pays ou région<br>Fonctionnalité (licence) <br>Nombre total de minutes<br>Minutes utilisées<br>Minutes disponibles|
|[Rapport d’utilisation RTC Teams - Forfaits d’appels](pstn-usage-report.md#calling-plans)|Oui|Oui|Non|Non|  Horodatage<br>Nom d'utilisateur<br>Numéro de téléphone<br>Type d’appel <br>Appelé à<br>Vers le pays ou la région <br>Appelé à partir de <br>À partir d’un pays ou d’une région<br>Frais<br>Devise<br>Durée<br>National/International<br>ID d’appel<br>Type de nombre<br>Pays ou région<br>ID de conférence<br>Fonctionnalité (licence)|
|[Rapport d’utilisation RTC Teams - Routage direct](pstn-usage-report.md#direct-routing)  |Oui|Oui|Non|Non|  Horodatage<br>Nom d’affichage<br>Adresse SIP<br>Numéro de téléphone <br>Type d’appel<br>Appelé à<br>Heure de début<br>Heure d’invitation<br>Heure de l’échec<br>Heure de fin<br>Durée<br>Type de nombre<br>Contournement de média<br>Nom de domaine complet SBC<br>Région Azure<br>Type d’événement<br>Code SIP final<br>Sous-code Microsoft final<br>Expression SIP finale<br>ID de corrélation  |
|[Rapport de licence de protection des informations Teams](information-protection-license-report.md)  |Oui|Oui|Non|Non| <br>Si les utilisateurs disposent de licences valides pour envoyer leurs messages via des notifications de modification</br><br>Nombre total d’événements de notification de modification déclenchés par un utilisateur<br><br>Quelles applications écoutent les événements de notification de modification à l’échelle de l’organisation<br>|
|[Rapport d’utilisation Rendez-vous virtuels Teams](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)|Oui|Oui|Non|Non| Nombre de rendez-vous virtuels<br>Nombre de rendez-vous Bookings<br>Nombre de rendez-vous intégrés aux dossiers médicaux électroniques (DSE) Teams<br>Durée moyenne d’un rendez-vous<br>Temps d’attente moyen des participants dans la salle d’attente<br>Heure de début<br>ID de réunion<br>Temps d’attente de la salle d’attente<br>Durée<br>Statut<br>Type de produit<br>Participants<br>Service<br>SMS envoyés<br>Si le rendez-vous a utilisé une fonctionnalité de Rendez-vous virtuels avancée|
|[Rapport d’activité Rendez-vous virtuels avancé Teams](/microsoft-365/frontline/advanced-virtual-appointments-activity-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Oui|Oui|Non|Non|Nombre d’utilisateurs utilisant des fonctionnalités de Rendez-vous virtuels avancées<br>Nombre d’utilisateurs qui utilisent des notifications sms<br>Nombre d’utilisateurs qui utilisent la conversation dans la salle d’attente (bientôt disponible)<br>Nombre d’utilisateurs qui effectuent des rendez-vous à la demande|
|[Rapport Rendez-vous virtuels du connecteur DSE Teams](/microsoft-365/frontline/ehr-connector-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json) |Oui|Oui|Non|Non| Heure de début<br>Durée<br>Principal (nom de l’organisateur de la réunion)<br>E-mail du principal (e-mail de l’organisateur de la réunion)<br>Service<br>Préposés<br>Temps d’attente de la salle d’attente<br>Si le rendez-vous est dans la limite d’allocation|
[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="make-the-user-specific-data-anonymous"></a>Rendre les données spécifiques de l’utilisateur anonymes

Pour que les données du rapport d’activité utilisateur Teams soient anonymes, vous devez être administrateur général. L’administrateur général peut masquer les informations d’identification (à l’aide de hachages MD5), telles que le nom d’affichage, le nom du groupe, l’adresse e-mail et l’ID AAD dans le rapport et son exportation.

1. Dans Centre d'administration Microsoft 365, accédez à **Paramètres Paramètres** \> **Paramètres de l’organisation**, puis sous l’onglet **Services**, choisissez **Rapports**.
    
2. Sélectionnez **Rapports**, puis **affichez les noms des utilisateurs, des groupes et des sites masqués dans tous les rapports**. Ce paramètre est appliqué aux rapports d’utilisation dans Centre d'administration Microsoft 365 ainsi qu’au centre d’administration Teams.
  
3. Sélectionnez **Enregistrer les modifications**.

> [!NOTE]
> L’activation de ce paramètre permet d’identifier les informations de nom d’utilisateur, de groupe et de site dans le [rapport d’activité des utilisateurs Teams](user-activity-report.md), le [rapport d’utilisation des appareils Teams](device-usage-report.md) et le [rapport d’utilisation de Teams](teams-usage-report.md). À compter du 1er septembre 2021, ce paramètre est activé par défaut pour tout le monde dans le cadre de notre engagement continu à protéger les informations importantes et à permettre aux entreprises de prendre en charge leurs lois locales sur la protection de la vie privée. 
>
>Ce paramètre s’applique également aux rapports d’utilisation Microsoft 365 dans Centre d'administration Microsoft 365, Microsoft Graph et Power BI.
