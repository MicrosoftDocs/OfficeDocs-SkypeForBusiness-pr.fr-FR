---
title: Gérer l’expérience de jointure pour Teams rendez-vous virtuels sur les navigateurs
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
ms.reviewer: hafarmer
description: Découvrez l’expérience de jointure pour Teams rendez-vous virtuels sur les navigateurs.
ms.openlocfilehash: 418186734befa66f145ca56f883605715d83aa30
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853305"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>Gérer l’expérience de jointure pour Teams rendez-vous virtuels sur les navigateurs

Microsoft Teams permet aux utilisateurs de rejoindre facilement des rendez-vous virtuels sans avoir à télécharger Teams. Pour une expérience plus transparente, les participants peuvent participer à des rendez-vous tels que des visites médicales et des consultations financières à partir d’un bureau ou d’un navigateur mobile. Les participants n’ont pas besoin d’installer l’application Teams sur leur appareil.

Avec la jointure du navigateur, lorsqu’un participant rejoint un rendez-vous, il n’est pas invité à télécharger Teams. Au lieu de cela, Teams s’ouvre dans un navigateur, où le participant peut sélectionner **Rejoindre maintenant** pour participer. Avec cette fonctionnalité, gardez à l’esprit que si Teams est déjà installé sur l’appareil, Teams s’ouvre dans un navigateur et non dans l’application.

Actuellement, la jointure du navigateur est disponible pour les rendez-vous planifiés par le biais des éléments suivants :

- [Application Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- connecteur Microsoft Teams Electronic Health Record (EHR)

  - Intégration à [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Intégration à [Epic EHR](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>Configurer la jointure du navigateur

### <a name="appointments-scheduled-through-the-bookings-app"></a>Rendez-vous planifiés via l’application Bookings

Les planificateurs de votre organisation peuvent activer cette fonctionnalité pour des types de rendez-vous spécifiques et pour des rendez-vous individuels dans l’application Bookings.

Une fois cette fonctionnalité activée, l’e-mail de confirmation ou le sms envoyé aux participants contient un lien de participation à une réunion qui s’ouvre Teams dans un navigateur de bureau ou mobile. Pour obtenir la liste des navigateurs pris en charge, consultez [Navigateurs pris en charge](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Activer la jointure du navigateur pour un type de rendez-vous

Dans Bookings, accédez à **Paramètres** >  **TypesAppointment**, sélectionnez un [type de rendez-vous](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887), puis **activez Autoriser les participants à rejoindre à partir d’un navigateur**. Cela permet la jointure du navigateur pour tous les rendez-vous de ce type.

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Capture d’écran de l’option Autoriser les participants à participer à partir d’un paramètre de navigateur pour les types de rendez-vous dans l’application Bookings":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Activer la jointure du navigateur pour un rendez-vous individuel

Dans Bookings, sélectionnez **Nouvelle réservation**, puis **activez Autoriser les participants à rejoindre à partir d’un navigateur**.

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Capture d’écran de l’option Autoriser les participants à rejoindre à partir d’un paramètre de navigateur sur le nouveau formulaire de réservation dans l’application Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Rendez-vous planifiés via le connecteur Teams DSE

Aucune configuration n’est nécessaire pour vous ou votre personnel !

**Intégration à Cerner EHR** : le connecteur Teams EHR prend en charge les patients qui rejoignent des rendez-vous virtuels via un lien dans le SMS. Au moment du rendez-vous, les patients peuvent participer en appuyant sur le lien dans le SMS et Teams s’ouvre dans un navigateur.

**Intégration à Epic EHR** : le connecteur Teams EHR prend en charge les patients qui rejoignent des rendez-vous virtuels via MyChart web et mobile. Au moment du rendez-vous, les patients peuvent démarrer le rendez-vous à partir de MyChart à l’aide du bouton **Commencer la visite virtuelle**, et Teams s’ouvre dans un navigateur.

## <a name="supported-browsers"></a>Navigateurs pris en charge

Voici les navigateurs actuellement pris en charge. Nous prenons en charge la dernière version plus deux versions précédentes, sauf indication contraire.

|Plateforme  |Chrome |Safari |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; Le partage d’écran sortant n’est pas pris en charge sur iOS ou Android.

&sup2; Les applications iOS sur Safari ne peuvent pas sélectionner les périphériques de microphone et de haut-parleur. Par exemple, Bluetooth appareils. Il s’agit d’une limitation du système d’exploitation, qui contrôle la sélection de l’appareil par défaut.

## <a name="things-to-consider"></a>Éléments à prendre en compte

Le membre du personnel qui effectue le rendez-vous peut partager son écran à partir de son Teams client de bureau, mobile ou web avec un participant qui se joint à partir d’un bureau ou d’un navigateur mobile. Toutefois, les participants ne peuvent pas partager leur écran à partir d’un navigateur de bureau ou mobile.

## <a name="related-articles"></a>Articles connexes

- [Rendez-vous virtuels avec Teams et l’application Bookings](bookings-virtual-visits.md)
- [Créer un type de rendez-vous Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Participer à un rendez-vous Bookings en tant que participant](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Rendez-vous virtuels avec Teams - Intégration à Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Rendez-vous virtuels avec Teams - Intégration à Epic EHR](healthcare/ehr-admin.md)
