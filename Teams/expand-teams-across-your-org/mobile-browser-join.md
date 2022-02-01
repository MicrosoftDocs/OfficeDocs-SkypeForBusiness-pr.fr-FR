---
title: Gérer l’expérience de jointisation pour Teams visites virtuelles sur les navigateurs mobiles
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
description: Découvrez l’expérience de jointisation pour les Teams virtuelles sur les navigateurs mobiles.
ms.openlocfilehash: 5c4b0f7ac9011d12d12e3076f900880292e72eb1
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288562"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Gérer l’expérience de jointisation pour Teams visites virtuelles sur les navigateurs mobiles

Microsoft Teams permet aux personnes de facilement prendre des rendez-vous sur leurs appareils mobiles sans avoir à les Teams. Pour une expérience plus transparente, les participants peuvent rejoindre des rendez-vous tels que des visites médicales, des consultations financières, des enseignants, etc., à partir d’un navigateur mobile. Les participants n’ont pas besoin d’installer Teams’application mobile sur leurs appareils mobiles Android ou iOS.

Lorsqu’un participant rejoint un navigateur mobile, lorsqu’un participant rejoint un rendez-vous à partir d’un appareil mobile, il n’est pas invité à télécharger Teams. Au lieu de Teams, la fenêtre s’ouvre dans un navigateur mobile, où le participant peut sélectionner **Rejoindre maintenant** pour rejoindre la réunion. Cette fonctionnalité vous permet de garder à l’esprit que si Teams est déjà installé sur l’appareil mobile d’un participant, Teams s’ouvre dans un navigateur mobile et non dans l’application.

Pour l’instant, la jointë de navigateur mobile est disponible pour les rendez-vous programmés via les services suivants :

- [Application Bookings](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams de dossiers médicaux électroniques (EHR)

  - Intégration avec [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Intégration à [Ehr DesHéz](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Configurer une jointe de navigateur mobile

### <a name="appointments-scheduled-through-the-bookings-app"></a>Rendez-vous programmés via l’application Bookings

Les responsables de la planification de votre organisation peuvent activer cette fonctionnalité pour des types de rendez-vous spécifiques et pour des rendez-vous individuels dans l’application Bookings.

Une fois cette fonctionnalité désactivée, l’e-mail de confirmation ou le SMS envoyé aux participants contiendra un lien de participation à la réunion qui ouvre Teams dans un navigateur mobile. Sur les appareils mobiles Android, Teams s’ouvre dans Chrome. Sur les appareils mobiles iOS, Teams s’ouvre dans Safari.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Activer la participation à un navigateur mobile pour un type de rendez-vous

Dans Bookings, sélectionnez **Paramètres** >  **Types** de rendez-vous, sélectionnez un [type](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) de rendez-vous, puis sélectionnez Autoriser les participants à rejoindre la réunion à partir **d’un navigateur mobile**. Ceci permet de rejoindre un navigateur mobile pour tous les rendez-vous de ce type.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Capture d’écran du paramètre Autoriser les participants à rejoindre la réunion à partir d’un navigateur mobile pour les types de rendez-vous dans l’application Bookings":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Activer la jointité d’un navigateur mobile pour un rendez-vous individuel

Dans Bookings, **sélectionnez Nouvelle réservation**, puis sélectionnez Autoriser les participants à rejoindre la réunion à partir **d’un navigateur mobile**.

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Capture d’écran du paramètre Autoriser les participants à rejoindre la réunion à partir d’un navigateur mobile dans le nouveau formulaire de réservation de l’application Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Rendez-vous programmés via le Teams EHR

Aucune mise en service n’est requise pour vous ou votre personnel.

**Intégration à Cerner EHR** : le connecteur Teams EHR prend en charge les patients rejoignant des visites virtuelles via un mobile. Au moment du rendez-vous, les patients peuvent rejoindre une visite virtuelle en appuyant sur le lien dans le SMS. Le patient choisit le navigateur de son choix, puis Teams s’ouvre dans ce navigateur.

**Intégration à EhrIenne :** le connecteur Teams EHR prend en charge les patients rejoignant des visites virtuelles via MyChart web et mobile. Au moment du rendez-vous, les patients peuvent commencer une visite virtuelle à partir de MyChart à l’aide du **bouton Commencer la visite** virtuelle. Le patient choisit le navigateur de son choix, puis Teams s’ouvre dans ce navigateur.

## <a name="supported-mobile-browsers"></a>Navigateurs mobiles pris en charge

Voici les navigateurs mobiles actuellement pris en charge. Sauf indication contraire, la dernière version et deux versions précédentes sont prise en charge.

|Plateforme  |Chrome |Safari |Edge (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1; Les applications iOS sur Safari ne peuvent pas sélectionner de micros et de haut-parleurs. Par exemple, Bluetooth appareils mobiles. Il s’agit d’une limitation du système d’exploitation, qui contrôle la sélection de l’appareil par défaut.

&sup2; Safari 14+ et macOS 11+ sont requis pour la prise en charge vidéo sortante.

## <a name="things-to-consider"></a>Éléments à prendre en compte

Le membre du personnel qui dirige la visite virtuelle peut partager son écran à partir de son client Teams de bureau, mobile ou Web avec un participant qui rejoint la réunion à partir d’un navigateur mobile. Toutefois, les participants ne peuvent pas partager leur écran à partir d’un navigateur mobile.

> [!NOTE]
> Nous ajoutons d’autres fonctionnalités à l’expérience de réunion dans les prochaines version de Teams. Revenir pour obtenir les informations les plus à jour. Pour rester au fait des fonctionnalités de Teams à venir, consultez la [feuille de route Microsoft 365 de l’équipe](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>Articles connexes

- [Visites virtuelles avec Teams et l’application Bookings](bookings-virtual-visits.md)
- [Créer un type de rendez-vous Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Rejoindre un rendez-vous Bookings en tant que participant](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Visites virtuelles avec des Teams - Intégration dans l’intégration à l’environnement de gestion des biens et des données](healthcare/ehr-admin-cerner.md)
- [Visites virtuelles avec Teams - Intégration à EhRExique](healthcare/ehr-admin.md)
