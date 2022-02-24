---
title: Visites virtuelles avec Microsoft Teams et l’application Bookings
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Découvrez comment planifier, gérer et effectuer des visites virtuelles à l’aide de l’application Bookings dans Teams.
ms.openlocfilehash: 6241c377cc5daa0986081fbfa30eca5fa7146efc
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929269"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visites virtuelles avec Microsoft Teams et l’application Bookings

## <a name="overview"></a>Vue d’ensemble

[L’application Bookings dans](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) Microsoft Teams permet aux organisations de planifier et de gérer des rendez-vous virtuels pour le personnel et les participants. Elle permet de planifier des rendez-vous tels que des visites médicales, des consultations financières, des entretiens, du support client, des ajustements et des consultations virtuels, des horaires d’ouverture du bureau, etc.

L’application Bookings facilite la gestion des demandes de planification complexes de toute organisation. Les planificateurs peuvent gérer plusieurs calendriers des services et du personnel, ainsi que les communications avec les participants internes et externes à partir d’une même expérience.

Les rendez-vous virtuels sont tenus Microsoft Teams réunions, qui offrent des fonctionnalités de visioconférence robustes. Par exemple, un médecin peut partager son écran et examiner les résultats des tests avec un patient. Un conseiller bancaire peut également demander des signatures électroniques sur des documents, ce qui leur permet de fermer des transactions à distance.

Chaque rendez-vous virtuel comprend un lien de réunion Teams envoyé aux participants par courrier électronique, qu’ils peuvent facilement rejoindre à partir d’un navigateur web ou à partir d’Teams sur n’importe quel appareil. Les rappels automatiques par courrier électronique permettent de réduire les absences de montre et d’améliorer l’implication des clients et des clients.

Bookings vous permet d’obtenir une expérience adaptée à votre secteur d’activité. Voici quelques exemples de la manière dont vous pouvez l’utiliser dans votre organisation :

|Secteur d’activité | Exemples |
|---------|---------|
|Services financiers    |  Visites virtuelles pour la vente à distance et le service<br/>Planifier et gérer les rendez-vous des gestionnaires de relations bancaires, des conseillers financiers et des expert en réclamations, entre autres, pour aider vos clients à améliorer leur efficacité et leur commodité.  |
|Vente au détail   | Ajustements et consultations virtuels <br/>Planifier et gérer des rendez-vous pour vos associés des ventes, experts en produit et consultants en conception pour effectuer des ajustements virtuels et des consultations avec les clients.   |
|Soins de santé   |  Visites virtuelles pour les soins des patients <br/>Planifier et gérer des rendez-vous pour que les membres de votre équipe de soins rencontrent des patients ou d’autres fournisseurs de soins pour discuter des soins médicaux.   |

Cet article vous donne une vue d’ensemble de la planification, de la gestion et de la conduite de visites virtuelles à l’aide de l’application Bookings dans Teams.

## <a name="before-you-get-started"></a>Avant de commencer

Si vous êtes administrateur, voir Gérer l’application [Bookings dans Teams](../bookings-app-admin.md) pour en savoir plus sur les conditions préalables à l’utilisation de l’application Bookings dans Teams, comment contrôler l’accès à Bookings dans votre organisation, et les paramètres de stratégie et d’administration recommandés.

N’oubliez pas que seuls les planningurs de votre organisation doivent installer l’application Bookings dans Teams. Les membres du personnel qui effectuent des rendez-vous virtuels ou y participent n’ont pas besoin de l’application. Ils rejoignent des rendez-vous à partir Teams ou Outlook calendrier, ou en utilisant le lien de la réunion dans leur e-mail de confirmation de réservation.

## <a name="set-up-a-new-booking-calendar"></a>Configurer un nouveau calendrier de réservation

### <a name="create-the-booking-calendar"></a>Créer le calendrier de réservation

Dans Teams, sélectionnez **BookingsGet** >  **démarré**, puis **Nouveau calendrier de réservation**. Complétez le formulaire et assurez-vous de choisir le type d’entreprise approprié pour votre organisation.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Capture d’écran du nouvel écran de réservation de calendrier montrant les types de clients":::

Si vous êtes une grande organisation, créez plusieurs calendriers de réservation si vous souhaitez que les participants reçoivent un courrier de réservation d’un service spécifique plutôt que de votre organisation globale.
Pour en savoir plus, [voir Créer un calendrier Bookings](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Si ce n’est pas la première fois que vous travaillez dans l’application Bookings ou si vous souhaitez travailler dans un calendrier de réservation existant, dans Bookings, sélectionnez la flèche de la flèche vers le bas en côté du nom de votre organisation, puis choisissez Calendrier de réservation **existant.** À partir de là, vous pouvez rechercher celui que vous souhaitez.

### <a name="add-staff"></a>Ajouter des enseignants

Dans le calendrier de réservation, sélectionnez Autres **options** (...) > **Paramètres**, puis sélectionnez **Personnel**. Ajoutez des membres du personnel et attribuez un rôle à chaque personne que vous ajoutez. Vous pouvez ajouter jusqu’à 100 membres du personnel à un calendrier de réservation.

L’application Bookings est intégrée à Outlook. Une fois que vous avez ajouté des membres du personnel, vous pouvez consulter la disponibilité du calendrier de cette personne et planifier des réservations pour elle. Pour en savoir plus, voir [Ajouter du personnel et afficher un calendrier Bookings](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Créer des types de rendez-vous

Créez des types de rendez-vous spécifiques pour représenter les services proposés par votre organisation et personnaliser l’expérience de réservation.

Dans le calendrier de réservation, sélectionnez Autres **options** (...) > **types** de rendez-vous, puis **sélectionnez Nouveau type de rendez-vous**. Entrez un nom (&mdash;par exemple, Ouverture de compte, Renouvellement d’emprunt, Consultation d’emprunt,&mdash; Préparation de la taxe, etc.).

Les informations et liens que vous ajoutez sont inclus dans la confirmation par courrier électronique qui est envoyée aux participants chaque fois que ce type de rendez-vous est réservé. Vous pouvez même définir des rappels par courrier électronique et d’autres options, telles que la possibilité pour les participants de rejoindre la réunion à partir d’un navigateur [mobile](mobile-browser-join.md) sans avoir à Teams. Pour en savoir plus, voir [Créer un type de rendez-vous](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-a-visit"></a>Planifier une visite

Dans le calendrier de réservation, **sélectionnez Nouvelle réservation**. Sélectionnez un type de rendez-vous, puis remplissez les informations pertinentes.

Cela inclut les informations de contact des participants, le membre du personnel qui fournit le service, les notes internes que seul le personnel peut voir, les rappels par courrier électronique et si le participant peut rejoindre la réunion à partir d’un navigateur mobile. Pour en savoir plus, [consultez Planifier une réservation dans l’Teams Bookings](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

La confirmation par courrier électronique envoyée au participant inclut le lien de la réunion et une pièce jointe afin qu’il puisse ajouter le rendez-vous virtuel à son calendrier. Le personnel reçoit également un e-mail de confirmation et d’invitation à une réunion.

## <a name="conduct-a-visit"></a>Effectuer une visite

Dans votre Teams calendrier Outlook, sélectionnez la réservation, puis sélectionnez Rejoindre ou Teams lien de la réunion. Vérifiez vos paramètres audio et vidéo, puis sélectionnez **Rejoindre maintenant**. Pour plus d’informations, [voir Conduire un rendez-vous Bookings](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-visits-and-get-real-time-status-updates"></a>Surveiller les visites et obtenir des mises à jour de l’état en temps réel

[L’affichage de la](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) file d’attente dans Bookings fournit à votre personnel un tableau de bord qui permet de surveiller tous les rendez-vous virtuels de la journée, avec les mises à jour en temps réel. Pour voir la file d’attente, sous **l’onglet File d’attente** dans Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Capture d’écran de l’affichage de la file d’attente dans l’application Bookings Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

Dans la file d’attente, les scheduleurs peuvent ajouter une nouvelle réservation, afficher les détails pertinents du rendez-vous et consulter les statuts des rendez-vous tout au long de la journée. Lorsqu’un patient rejoint la salle d’attente, son statut change, et le temps d’attente est affiché et suivi. L’affichage est actualisé automatiquement avec des mises à jour en couleur afin que les modifications soient facilement identifiées.

Le personnel enseignant peut même rejoindre et gérer les rendez-vous directement à partir de la file d’attente.

> [!NOTE]
> Actuellement, l’application Bookings prend en charge l’ajout d’un jusqu’à 100 membres du personnel par calendrier de réservation. Si vous avez utilisé Graph API pour configurer et ajouter du personnel à un calendrier de réservation, cette limite peut ne pas être appliquée. Dans ce scénario, l’onglet **File** d’attente ne pourra pas restituer le contenu des calendriers qui comptent plus de 100 membres du personnel. Pour une expérience optimale, nous vous recommandons d’ajouter au moins 100 membres du personnel à un calendrier de réservation. Nous travaillons à la résolution de cette limitation dans les prochaines version.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Fonctionnalités supplémentaires avec l’application web Bookings

L’application web Bookings vous offre des fonctionnalités supplémentaires. Par exemple, vous pouvez publier une page de réservation en ligne libre-service dans laquelle les personnes peuvent planifier des rendez-vous avec les membres de votre personnel. Pour accéder à l’application web Bookings, accédez à Autres **options** (...) **>'ouvrir l’application web Bookings**.

Pour en savoir plus, [consultez Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="related-articles"></a>Articles connexes

- [Gérer l’expérience de jointisation pour les Teams virtuelles sur les navigateurs mobiles](mobile-browser-join.md)

- [Teams utilisation des visites virtuelles](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Commencer à travailler avec Teams pour les organisations de soins de santé](healthcare/teams-in-hc.md)

- [Application Bookings dans la Teams’aide](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
