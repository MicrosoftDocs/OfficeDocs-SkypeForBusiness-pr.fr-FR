---
title: Visites virtuelles dans Microsoft Teams et l’application Bookings
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Découvrez comment utiliser l’application Bookings dans Teams pour planifier, gérer et effectuer des visites virtuelles.
ms.openlocfilehash: 9c925e07bebe20e1f103a4f3acf3dc60f8409bcf
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973280"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visites virtuelles dans Microsoft Teams et l’application Bookings

## <a name="overview"></a>Présentation

[L’application Bookings dans](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) Microsoft Teams permet aux organisations de planifier et de gérer des rendez-vous virtuels pour le personnel et les participants. Il vous permet de planifier des rendez-vous virtuels tels que des visites médicales, des consultations financières, des entretiens, un support client, des expériences d’achat virtuel, des heures d’ouverture du bureau, etc.

L’application Bookings facilite la gestion des demandes de planification complexes de toute organisation. Les planificateurs peuvent gérer plusieurs calendriers des services et du personnel, ainsi que les communications avec les participants internes et externes à partir d’une même expérience.

Les visites virtuelles ont lieu au cours Microsoft Teams réunions, qui offrent de solides fonctionnalités de visioconférence. Par exemple, un médecin peut partager son écran et examiner les résultats des tests avec un patient. Un conseiller bancaire peut également demander des signatures électroniques sur des documents, ce qui leur permet de fermer des transactions à distance.

Chaque rendez-vous virtuel inclut un lien de réunion Teams envoyé aux participants par courrier électronique, qu’ils peuvent facilement rejoindre à partir d’un navigateur web ou à partir d’Teams sur n’importe quel appareil. Les rappels automatiques par courrier électronique permettent de réduire les absences de montre et d’améliorer l’implication des clients et des clients.

Bookings vous permet d’obtenir une expérience adaptée à votre secteur d’activité. Voici quelques exemples de la manière dont vous pouvez l’utiliser dans votre organisation :

|Secteur d’activité | Exemples |
|---------|---------|
|Services financiers    |  Visites virtuelles pour la vente à distance et le service<br/>Planifier et gérer des rendez-vous virtuels pour les gestionnaires de relations bancaires, les conseillers financiers et les expert en réclamations, entre autres, pour aider vos clients à accroître leur efficacité et leur commodité.  |
|Soins de santé   |  Visites virtuelles pour les soins des patients <br/>Planifier et gérer les visites virtuelles pour que les membres de votre équipe de soins rencontrent des patients ou d’autres fournisseurs de soins pour discuter des soins médicaux.   |         |
|Vente au détail   | Expériences d’achat virtuel <br/>Planifier et gérer des rendez-vous pour vos associés des ventes, experts en produits et consultants en conception pour mener des expériences d’achat virtuel avec les clients.   |         |

Cet article vous donne une vue d’ensemble de l’utilisation de l’application Bookings dans Teams pour planifier, gérer et effectuer des visites virtuelles.

## <a name="before-you-get-started"></a>Avant de commencer

Si vous êtes administrateur, voir Gérer l’application [Bookings](../bookings-app-admin.md) dans Teams pour en savoir plus sur les conditions préalables à l’utilisation de l’application Bookings dans Teams, comment contrôler l’accès à Bookings dans votre organisation, et les paramètres de stratégie et d’administration recommandés.

N’oubliez pas que seuls les planningurs de votre organisation doivent installer l’application Bookings dans Teams. Les membres du personnel qui effectuent des rendez-vous virtuels ou y participent n’ont pas besoin de l’application. Ils rejoignent des rendez-vous à partir Teams ou Outlook calendrier, ou en utilisant le lien de la réunion dans leur e-mail de confirmation de réservation.

## <a name="set-up-a-new-booking-calendar"></a>Configurer un nouveau calendrier de réservation

### <a name="create-the-booking-calendar"></a>Créer le calendrier de réservation

Dans Teams, allez **à Bookings**  >  **Get started,** puis **sélectionnez Nouveau calendrier de réservation.** Complétez le formulaire et assurez-vous de choisir le type d’entreprise approprié pour votre organisation.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Capture d’écran du nouvel écran de réservation de calendrier montrant les types de clients":::

Si vous êtes une grande organisation, créez plusieurs calendriers de réservation si vous souhaitez que les participants reçoivent un courrier de réservation d’un service spécifique plutôt que de votre organisation globale.
Pour en savoir plus, [voir Créer un calendrier Bookings.](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)

> [!NOTE]
> Si ce n’est pas la première fois que vous travaillez dans l’application Bookings ou si vous souhaitez travailler dans un calendrier de réservation existant, dans Bookings, sélectionnez la flèche de la flèche vers le bas en côté du nom de votre organisation, puis choisissez Calendrier de réservation **existant.** À partir de là, vous pouvez rechercher celui que vous souhaitez.

### <a name="add-staff"></a>Ajouter des enseignants

Dans le calendrier de réservation, sélectionnez Autres **options** (...) > **Paramètres,** puis sélectionnez **Personnel.** Ajoutez des membres du personnel et attribuez un rôle à chaque personne que vous ajoutez.

L’application Bookings est intégrée à Outlook. Une fois que vous avez ajouté des membres du personnel, vous pouvez consulter la disponibilité du calendrier de cette personne et planifier des réservations pour elle. Pour en savoir plus, voir [Ajouter du personnel et afficher un calendrier Bookings.](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)  

### <a name="create-appointment-types"></a>Créer des types de rendez-vous

Créez des types de rendez-vous spécifiques pour représenter les services offerts par votre organisation et personnaliser l’expérience de réservation.

Dans le calendrier de réservation, sélectionnez Autres **options** (...) > **types** de rendez-vous, puis **sélectionnez Nouveau type de rendez-vous.** Entrez un nom, par exemple, Ouverture de compte, Renouvellement d’emprunt, Consultation d’emprunt, Préparation de la taxe et toute autre information et &mdash; &mdash; paramètres de votre souhaitez.

Les informations et liens que vous ajoutez sont inclus dans la confirmation par courrier électronique qui est envoyée aux participants chaque fois que ce type de rendez-vous est réservé. Vous pouvez même définir des rappels par courrier électronique et d’autres options, telles que la possibilité pour les participants de rejoindre la réunion à partir d’un navigateur [mobile](mobile-browser-join.md) sans avoir à Teams. Pour en savoir plus, voir [Créer un type de rendez-vous.](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)

## <a name="schedule-a-virtual-visit"></a>Planifier une visite virtuelle

Dans le calendrier de réservation, **sélectionnez Nouvelle réservation.** Sélectionnez un type de rendez-vous, puis remplissez les informations pertinentes.

Cela inclut les informations de contact des participants, le membre du personnel qui fournit le service, les notes internes que seul le personnel peut voir, les rappels par courrier électronique et si le participant peut rejoindre la réunion à partir d’un navigateur mobile. Pour en savoir plus, [consultez Planifier une réservation dans l Teams’application Bookings.](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)

La confirmation par courrier électronique envoyée au participant inclut le lien de la réunion et une pièce jointe pour lui aider à ajouter le rendez-vous virtuel à son calendrier. Le personnel reçoit également un e-mail de confirmation et d’invitation à une réunion.

## <a name="conduct-a-virtual-visit"></a>Effectuer une visite virtuelle

Dans votre Teams calendrier Outlook, sélectionnez la réservation, puis  sélectionnez Rejoindre ou Teams lien de la réunion. Vérifiez vos paramètres audio et vidéo, puis sélectionnez **Rejoindre maintenant.** Pour en savoir plus, [consultez Conduire un rendez-vous Bookings.](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Fonctionnalités supplémentaires avec l’application web Bookings

L’application web Bookings vous offre des fonctionnalités supplémentaires. Par exemple, vous pouvez publier une page de réservation en ligne libre-service dans laquelle les personnes peuvent planifier des rendez-vous avec les membres de votre personnel. Pour accéder à l’application web Bookings, accédez à Autres **options** (...) > **Ouvrir Bookings Web App.**

Pour en savoir plus, [consultez Microsoft Bookings.](/microsoft-365/bookings/bookings-overview)

## <a name="related-articles"></a>Articles connexes

[Gérer l’expérience de jointisation pour Teams visites virtuelles sur les navigateurs mobiles](mobile-browser-join.md)

[Prise en main de Teams pour les organismes de santé](healthcare/teams-in-hc.md)

[Application Bookings dans la Teams’aide](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
