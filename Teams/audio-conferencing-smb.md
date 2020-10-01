---
title: Configurer l’audioconférence pour les petites et moyennes entreprises
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Découvrez comment définir une audioconférence pour les petites et moyennes entreprises pour les personnes qui ont besoin d’utiliser un téléphone pour appeler une réunion. '
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328434"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurer l’audioconférence pour les petites et moyennes entreprises

Grâce à l’audioconférence, les personnes peuvent appeler des réunions teams à l’aide d’un téléphone au lieu d’utiliser l’application teams sur leur appareil mobile ou sur leur ordinateur.  

S’il s’agit d’une petite entreprise ou d’une petite taille avec des utilisateurs de 300 et que vous n’avez pas de licence de conférence audio, vous pouvez bénéficier d’une audioconférence pour un an. Cette offre gratuite est disponible à partir du 1er octobre 2020.

La licence du complément audioconférence peut être appliquée aux utilisateurs disposant de licences Microsoft 365 entreprise basique, Business standard, Business Premium, Enterprise E1 ou entreprise E3. Pour en savoir plus, voir [licences de complément teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Si vous avez entreprise E5 ou Microsoft 365 entreprise voix, vous ne serez pas en mesure d’utiliser la fonctionnalité de conférence rendez-vous gratuite, car ces licences incluent déjà une audioconférence.

Dans cet article, nous allons vous montrer comment configurer l’audioconférence. Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions. Les participants à une réunion qui rejoignent des réunions ne nécessitent pas de licences ou d’autres paramètres. Pour en savoir plus, voir [audioconférence](audio-conferencing-in-office-365.md).

## <a name="step-1-get-audio-conferencing-licenses"></a>Étape 1 : obtenir des licences de conférence audio

Procurez-vous une licence d’audioconférence pour chaque personne qui animera des réunions. Pour cela, utilisez le centre d’administration 365 Microsoft.

1. Dans le centre d’administration Microsoft 365, accédez **Billing**à  >  **services d’achat**de facturation, puis au bas de la page, sélectionnez **composants**additionnels. 
2. Sélectionnez Détails de la **promotion Microsoft 365 audio Conferencing**  >  **Details**.
3. Entrez le nombre de licences dont vous avez besoin pour les organisateurs de la réunion, puis terminez votre commande.

> [!NOTE]
> Activez ou désactivez l’option **affecter automatiquement à tous les utilisateurs**sans licence, selon que vous voulez affecter automatiquement une licence d’audioconférence à tous les utilisateurs ne disposant pas de cette licence.

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Étape 2 : affecter une licence d’audioconférence aux utilisateurs qui animent des réunions

Attribuez une licence à chaque personne qui animera des réunions. Pour cela, utilisez le centre d’administration 365 Microsoft.

### <a name="assign-a-license-to-one-user"></a>Attribuer une licence à un utilisateur

1. Dans le centre d’administration 365 Microsoft, accédez **à utilisateurs**  >  **actifs**.  
2. Sélectionnez la ligne de l’utilisateur auquel vous voulez attribuer une licence, puis dans le volet, sélectionnez **licences et applications**.
3. Activez la case à cocher **audioconférence Microsoft 365** , puis cliquez sur **enregistrer les modifications**. 

### <a name="assign-a-license-to-multiple-users"></a>Attribution d’une licence à plusieurs utilisateurs

1. Dans le centre d’administration 365 Microsoft, accédez **à utilisateurs**  >  **actifs**.  
2. Sélectionnez les cercles situés en regard des utilisateurs auxquels vous voulez attribuer une licence, puis sélectionnez **gérer les licences de produits**.
3. Dans le volet **gérer les licences de produits** , sélectionnez **affecter plus**.
4. Activez la case à cocher **audioconférence Microsoft 365** , puis cliquez sur **enregistrer les modifications**.  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a>Étape 3 : Rechercher ou obtenir un numéro de téléphone pour votre pont de conférence

Vous avez besoin d’un numéro de téléphone (également appelé numéro de service) de votre pont de conférence pour pouvoir l’utiliser dans les invitations aux réunions. Vous pouvez choisir d’utiliser un **numéro partagé** ou un **numéro dédié**. Les deux types de numéros peuvent être utilisés par n’importe quel appelant pour rejoindre une réunion.

### <a name="use-a-shared-number"></a>Utiliser un numéro partagé

Un numéro partagé est un numéro partagé par toutes les organisations. Les numéros partagés sont automatiquement attribués lorsque vous configurez audioconférence. Ces numéros partagés sont des numéros payants, auxquels des frais longue distance peuvent s’appliquer.

Pour trouver le numéro par défaut affecté à votre pont de conférence, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à**  >  la zone**ponts de conférence**, puis recherchez le numéro de l’emplacement le plus proche de vous.

### <a name="get-a-dedicated-number"></a>Obtenez un numéro dédié

Un numéro dédié est un numéro qui est disponible uniquement à vos utilisateurs. Un numéro dédié peut être un numéro payant ou un numéro sans frais. Pour utiliser un numéro dédié, vous devez d’abord obtenir le numéro, puis l’affecter à votre pont de conférence.  

Il existe plusieurs façons d’obtenir un numéro dédié. Vous pouvez obtenir un numéro de Microsoft ou transférer (porter) un numéro existant de votre fournisseur de services actuel vers Microsoft. Pour en savoir plus sur la façon de procéder, consultez la rubrique [obtention de numéros de service](getting-service-phone-numbers.md).

> [!NOTE]
> Si vous utilisez un numéro gratuit, vous devez d’abord affecter une licence de crédits de communication à chaque personne qui animera des réunions. Pour en savoir plus, reportez-vous à [la rubrique Configuration de crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md).

Une fois que vous disposez de votre numéro, attribuez-le à votre pont de conférence. Pour cela, utilisez le centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **meetings**  >  **Conference ponts**.
2. Cliquez sur **Ajouter**, puis sélectionnez **numéro payant** ou **numéro gratuit**.
3. Dans le volet **Ajouter un numéro de téléphone** , sélectionnez le numéro, puis sélectionnez **appliquer**.

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a>Étape 4 : affecter un numéro de connexion aux utilisateurs qui animent des réunions

Attribuez un numéro de connexion à chaque personne qui animera des réunions. Pour cela, utilisez le centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, sélectionnez **utilisateurs**, cliquez sur le nom d’affichage de l’utilisateur, puis sélectionnez **modifier**.
2. Sélectionnez **modifier**   en regard de **audioconférence**, puis dans le volet **audioconférence**   , sélectionnez un numéro dans les listes **numéro payant**   ou numéro **gratuit**   , puis sélectionnez **appliquer**.

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a>Étape 5 : planifier une réunion teams dans Outlook

Pour planifier une réunion, dans Outlook, accédez au **calendrier**, puis sélectionnez le bouton **nouvelle réunion teams** . Les numéros d’accès définis pour l’utilisateur et l’ID de conférence sont automatiquement ajoutés à l’invitation à la réunion qui est envoyée aux participants à la réunion.

Pour en savoir plus, voir [planifier une réunion teams dans Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Si vous le souhaitez, vous pouvez personnaliser les invitations aux réunions pour ajouter le logo de votre société, des liens vers le site Web de l’assistance et l’exclusion de responsabilité, et un pied de page uniquement. Voir [Personnaliser les invitations aux réunions](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="related-topics"></a>Sujets associés

- [Audioconférence](audio-conferencing-in-office-365.md)
- [Configurer l’audioconférence pour les équipes](set-up-audio-conferencing-in-teams.md)
- [Questions fréquentes à propos de l’audioconférence](audio-conferencing-common-questions.md)
- [Affichage des numéros de service](getting-service-phone-numbers.md)
- [Licences de compléments teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Attribution de licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
