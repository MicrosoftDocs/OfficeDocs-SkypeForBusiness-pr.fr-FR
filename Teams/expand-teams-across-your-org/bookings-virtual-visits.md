---
title: Visites virtuelles avec Microsoft Teams et l’Bookings virtuel
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
description: Découvrez comment planifier, gérer et effectuer des visites virtuelles à l’aide de l’Bookings dans Teams.
ms.openlocfilehash: 0db414765a649192d96122ac69764fa279a8dac5
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556535"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visites virtuelles avec Microsoft Teams et l’application Bookings

## <a name="overview"></a>Vue d’ensemble

L [Bookings appappe dans](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) Microsoft Teams permet aux organisations de planifier et de gérer des rendez-vous virtuels pour le personnel et les participants. Elle permet de planifier des rendez-vous tels que des visites médicales, des consultations financières, des entretiens, du support client, des ajustements et des consultations virtuels, des horaires d’ouverture du bureau, etc.

L Bookings facilite la gestion des demandes de planification complexes de toute organisation. Les planificateurs peuvent gérer plusieurs calendriers des services et du personnel, ainsi que les communications avec les participants internes et externes à partir d’une même expérience.

Les rendez-vous virtuels sont Microsoft Teams réunions, qui offrent des fonctionnalités de visioconférence robustes. Par exemple, un médecin peut partager son écran et examiner les résultats des tests avec un patient. Un conseiller bancaire peut également demander des signatures électroniques sur des documents, ce qui leur permet de fermer des transactions à distance.

Chaque rendez-vous virtuel comprend un lien de réunion Teams envoyé aux participants par courrier électronique, qu’ils peuvent facilement rejoindre à partir d’un navigateur web ou à partir d’Teams sur n’importe quel appareil. Les rappels automatiques par courrier électronique permettent de réduire les absences de montre et d’améliorer l’implication des clients et des clients.

Avec Bookings, vous obtenez une expérience adaptée à votre secteur d’activité. Voici quelques exemples de la manière dont vous pouvez l’utiliser dans votre organisation :

|Secteur d’activité | Exemples |
|---------|---------|
|Services financiers    |  Visites virtuelles pour la vente à distance et le service<br/>Planifier et gérer les rendez-vous des gestionnaires de relations bancaires, des conseillers financiers et des expert en réclamations, entre autres, pour aider vos clients à améliorer leur efficacité et leur commodité.  |
|Vente au détail   | Ajustements et consultations virtuels <br/>Planifier et gérer des rendez-vous pour vos associés des ventes, experts en produit et consultants en conception pour effectuer des ajustements virtuels et des consultations avec les clients.   |
|Soins de santé   |  Visites virtuelles pour les soins des patients <br/>Planifier et gérer des rendez-vous pour que les membres de votre équipe de soins rencontrent des patients ou d’autres fournisseurs de soins pour discuter des soins médicaux.   |

Cet article vous donne une vue d’ensemble de la planification, de la gestion et de la conduite de visites virtuelles à l’aide de l’Bookings dans Teams.

## <a name="before-you-get-started"></a>Avant de commencer

Si vous êtes administrateur, consultez Gérer l’application [Bookings dans Teams](../bookings-app-admin.md) pour en savoir plus sur les conditions préalables à l’utilisation de l’application Bookings dans Teams, comment contrôler l’accès à Bookings dans votre organisation, et les paramètres recommandés de stratégie et d’administration.

N’oubliez pas que seuls les scheduleurs de votre organisation doivent installer l’application Bookings dans Teams. Les membres du personnel qui effectuent des rendez-vous virtuels ou y participent n’ont pas besoin de l’application. Ils rejoignent des rendez-vous à partir Teams ou Outlook calendrier, ou en utilisant le lien de la réunion dans leur e-mail de confirmation de réservation.

## <a name="set-up-a-new-booking-calendar"></a>Configurer un nouveau calendrier de réservation

### <a name="create-the-booking-calendar"></a>Créer le calendrier de réservation

Dans Teams, sélectionnez **Bookings** >  **Démarrage**, puis **Nouveau calendrier de réservation**. Complétez le formulaire et assurez-vous de choisir le type d’entreprise approprié pour votre organisation.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Capture d’écran du nouvel écran de réservation de calendrier montrant les types de clients":::

Si vous êtes une grande organisation, créez plusieurs calendriers de réservation si vous souhaitez que les participants reçoivent un courrier de réservation d’un service spécifique plutôt que de votre organisation globale.
Pour en savoir plus, [voir Créer un Bookings calendrier](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Si ce n’est pas la première fois que vous travaillez dans l’application Bookings ou si vous souhaitez travailler dans un calendrier de réservation existant, dans Bookings, sélectionnez la flèche de la flèche vers le bas en face du nom de votre organisation, puis choisissez Calendrier de réservation **existant.** À partir de là, vous pouvez rechercher celui que vous souhaitez.

### <a name="add-staff"></a>Ajouter des enseignants

Dans le calendrier de réservation, sélectionnez Autres **options** (...) > **Paramètres**, puis sélectionnez **Personnel**. Ajoutez des membres du personnel et attribuez un rôle à chaque personne que vous ajoutez. Vous pouvez ajouter jusqu’à 100 membres du personnel à un calendrier de réservation.

L Bookings appeil s’intègre avec Outlook. Une fois que vous avez ajouté des membres du personnel, vous pouvez consulter la disponibilité du calendrier de cette personne et planifier des réservations pour elle. Pour en savoir plus, voir [Ajouter du personnel et afficher Bookings calendrier](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Créer des types de rendez-vous

Créez des types de rendez-vous spécifiques pour représenter les services proposés par votre organisation et personnaliser l’expérience de réservation. Les plannings peuvent ensuite utiliser le type de rendez-vous pour planifier une visite.

Dans le calendrier de réservation, sélectionnez Autres **options** (...) > **Paramètres** types de rendez-vous **, puis** **sélectionnez Ajouter un type de rendez-vous**. Entrez un nom (&mdash;par exemple, Ouverture de compte, Renouvellement d’emprunt, Consultation d’emprunt,&mdash; Préparation de la taxe, etc.).

Les informations que vous ajoutez sont incluses dans la confirmation par e-mail envoyée aux participants chaque fois que ce type de rendez-vous est réservé. Vous pouvez définir des rappels par courrier électronique et d’autres options, telles que la possibilité pour les participants de rejoindre la réunion à partir d’un navigateur [mobile](mobile-browser-join.md) sans avoir à Teams.

Si vous êtes un Bookings, vous pouvez lier jusqu’à quatre formulaires que les participants rempliront à chaque fois que ce type de rendez-vous est réservé. Par exemple, vous pouvez exiger que les participants remplissent un formulaire d’inscription avant de rejoindre une visite. Pour lier un formulaire, **sélectionnez Lier un formulaire**. Entrez l’URL du formulaire, puis sélectionnez **Lien**. (Si c’est la première fois que vous liez un formulaire, vous êtes invité à créer un groupe Microsoft 365 pour stocker des formulaires. **Sélectionnez Créer un** groupe pour créer le groupe. Vous ne devez effectuer cette période qu’une seule fois pour le calendrier de réservation.)

Lorsque vous travaillez avec des formulaires, gardez à l’esprit que :

- Pour apporter des modifications à un formulaire déjà lié à un type de rendez-vous, sélectionnez-le dans le type de rendez-vous ou dans le groupe de Microsoft 365 à [https://forms.office.com](https://forms.office.com).
- Le téléchargement de fichiers vers des formulaires contenant une [question de](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) chargement de fichier est pris en charge lorsque tous les participants sont issus de la même organisation.

Lorsqu’un scheduleur utilise le type de rendez-vous pour planifier une visite, il peut choisir d’inclure le formulaire, de le supprimer ou d’ajouter tout autre formulaire lié au type de rendez-vous. Les participants doivent remplir le formulaire avant de rejoindre la visite.

Pour en savoir plus, voir [Créer un type de rendez-vous](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-a-visit"></a>Planifier une visite

Dans le calendrier de réservation, **sélectionnez Nouvelle réservation**. Sélectionnez un type de rendez-vous, puis remplissez les informations pertinentes.

Cela inclut les informations de contact des participants, le membre du personnel qui fournit le service, les notes internes que seul le personnel peut voir, les rappels par courrier électronique et si le participant peut rejoindre la réunion à partir d’un navigateur mobile. Si un formulaire est lié au type de rendez-vous, vous pouvez choisir de l’inclure, de le supprimer ou d’ajouter d’autres formulaires liés.

La confirmation par courrier électronique envoyée au participant inclut le lien de la réunion et une pièce jointe afin qu’il puisse ajouter le rendez-vous virtuel à son calendrier. Le personnel reçoit également un e-mail de confirmation et d’invitation à une réunion. Si un formulaire a été inclus dans le rendez-vous, Bookings et les schedulers peuvent voir si le formulaire a été rempli par le participant avant la visite et consulter la réponse du participant.

Pour en savoir plus, [consultez Planifier une réservation dans l’Teams Bookings’application.](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)

## <a name="conduct-a-visit"></a>Effectuer une visite

Dans votre Teams calendrier Outlook, sélectionnez la réservation, puis sélectionnez Rejoindre ou Teams lien de la  réunion. Vérifiez vos paramètres audio et vidéo, puis sélectionnez **Rejoindre maintenant**. Pour en savoir plus, [voir Diriger un rendez Bookings rendez-vous](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-visits-and-get-real-time-status-updates"></a>Surveiller les visites et obtenir des mises à jour de l’état en temps réel

[L’affichage en](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) file d’attente Bookings fournit à votre personnel un tableau de bord qui permet de surveiller tous les rendez-vous virtuels de la journée, avec les mises à jour en temps réel. Pour voir la file d’attente, sous **l’onglet File d’attente**, Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Capture d’écran de l’affichage de la file d’attente dans l Bookings appil de l’Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

Dans la file d’attente, les scheduleurs peuvent ajouter une nouvelle réservation, afficher les détails pertinents du rendez-vous et consulter les statuts des rendez-vous tout au long de la journée. Lorsqu’un patient rejoint la salle d’attente, son statut change, et le temps d’attente est affiché et suivi. L’affichage est actualisé automatiquement avec des mises à jour en couleur afin que les modifications soient facilement identifiées.

Le personnel enseignant peut même rejoindre et gérer les rendez-vous directement à partir de la file d’attente.

> [!NOTE]
> Pour l’instant, l Bookings appappil de réservation prend en charge l’ajout d’un jusqu’à 100 membres du personnel par calendrier de réservation. Si vous avez utilisé Graph API pour configurer et ajouter du personnel à un calendrier de réservation, cette limite peut ne pas être appliquée. Dans ce scénario, l’onglet **File** d’attente ne pourra pas restituer le contenu des calendriers qui comptent plus de 100 membres du personnel. Pour une expérience optimale, nous vous recommandons d’ajouter au moins 100 membres du personnel à un calendrier de réservation. Nous travaillons à la résolution de cette limitation dans les prochaines version.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Fonctionnalités supplémentaires avec l’Bookings web

L Bookings web vous offre des fonctionnalités supplémentaires. Par exemple, vous pouvez publier une page de réservation en ligne libre-service dans laquelle les personnes peuvent planifier des rendez-vous avec les membres de votre personnel. Pour accéder à Bookings’application web, accédez à Autres **options** (...) **>'ouvrir Bookings’application web**.

Pour en savoir plus, voir [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-visits-usage"></a>Obtenir des informations sur l’utilisation des visites virtuelles

Le [rapport utilisation des visites virtuelles](../teams-analytics-and-reports/virtual-visits-usage-report.md) dans le centre Microsoft Teams d’administration donne aux administrateurs une vue d’ensemble de Teams de l’activité des visites virtuelles dans votre organisation. Le rapport présente des données d’analyse détaillées pour les rendez-vous virtuels, Bookings visites.

Vous pouvez afficher les indicateurs clés tels que le temps d’attente en salle d’attente et la durée de la visite. Utilisez ces informations pour obtenir des informations sur les tendances d’utilisation afin d’optimiser les visites virtuelles afin d’optimiser les résultats d’entreprise.

## <a name="related-articles"></a>Articles connexes

- [Gérer l’expérience de jointisation pour les Teams virtuelles sur les navigateurs mobiles](mobile-browser-join.md)

- [Teams utilisation des visites virtuelles](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Démarrage avec d Teams pour les organisations de soins de santé](healthcare/teams-in-hc.md)

- [Bookings appappe dans la documentation Teams’aide](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
