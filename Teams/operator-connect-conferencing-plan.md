---
title: Planifier Conférence en connexion à l'opérateur
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur les Conférence en connexion à l'opérateur, telles que les exigences et la planification du déploiement.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e1c363c66028a9e8611fa38179585e1e073c54b
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68583976"
---
# <a name="plan-for-operator-connect-conferencing"></a>Planifier Conférence en connexion à l'opérateur

L’audioconférence Microsoft offre la possibilité de composer une conférence et d’effectuer un appel sortant à partir d’une conférence à l’aide de numéros de téléphone rtc (RTC).  Les participants participent à des réunions Microsoft Teams à l’aide d’un pont de conférence audio uniquement.

Avec Conférence en connexion à l'opérateur fonctionnalités, les organisations peuvent utiliser des numéros de téléphone d’un opérateur tiers pour participer à des réunions Microsoft Teams. Si votre opérateur actuel fait partie du programme Microsoft Operator Connect, vous pouvez ajouter des numéros de téléphone de votre opérateur à votre pont d’audioconférence et les utiliser pour participer à des réunions.

Sans Conférence en connexion à l'opérateur fonctionnalités, les organisations peuvent uniquement utiliser les numéros de téléphone fournis par Microsoft pour leur pont d’audioconférence.

>[!NOTE]
>Un fournisseur de numéros de téléphone qui fait partie du programme Microsoft Operator Connect est référencé dans cet article comme un « opérateur ».
>
>Pour voir si votre opérateur participe au programme Microsoft Operator Connect, consultez le [répertoire Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Cet article décrit Conférence en connexion à l'opérateur :

- [Avantages](#benefits)
- [Exigences en matière de licences et facturation](#licensing-requirements-and-billing)
- [Informations supplémentaires sur l’audioconférence Microsoft](#additional-information-on-microsoft-audio-conferencing)

Pour plus d’informations sur la configuration de Conférence en connexion à l'opérateur, consultez [Configurer Conférence en connexion à l'opérateur](operator-connect-conferencing-configure.md).

Si certains utilisateurs de votre organisation doivent passer des appels externes à des numéros de téléphone RTC, vous avez toujours besoin d’un forfait d’appels. Pour en savoir plus sur l’utilisation d’un opérateur tiers pour la connectivité RTC externe, consultez [Plan for Operator Connect](operator-connect-plan.md).

## <a name="benefits"></a>Avantages

Conférence en connexion à l'opérateur offre les avantages suivants :

- **Allocation flexible des numéros de téléphone entre votre opérateur et Microsoft.** Utilisez les numéros de téléphone de Microsoft et de votre opérateur (avec un abonnement Microsoft AudioConférence Standard uniquement) ou utilisez uniquement les numéros de téléphone de votre opérateur (avec une licence Conférence en connexion à l'opérateur uniquement).

- **Infrastructure gérée par l’opérateur.** Votre opérateur gère les contrôleurs de frontière de session (SBC) et l’interconnexion avec Microsoft, ce qui vous permet de bénéficier d’achats et de gestion supplémentaires de matériel.

- **Déploiement plus rapide et plus facile.** Connectez-vous rapidement à votre opérateur et attribuez des numéros de téléphone à votre pont d’audioconférence à partir du Centre d’administration Teams.

- **Prise en charge et fiabilité améliorées.** Les opérateurs fournissent un support technique et des contrats de niveau de service partagé pour améliorer la prise en charge des services, et le peering direct optimisé par Azure crée une connexion réseau un-à-un pour une fiabilité accrue.

Conférence en connexion à l'opérateur peut être la solution appropriée pour votre organisation si :

- Vous souhaitez **conserver vos contrats** avec votre fournisseur de numéros de téléphone existant

- Vous souhaitez **étendre la couverture mondiale** de votre pont d’audioconférence Microsoft existant

- Vous souhaitez **obtenir des numéros de téléphone pour l’audioconférence à** partir d’un nouveau fournisseur de numéros de téléphone

- **L’audioconférence Microsoft n’est pas disponible dans votre emplacement géographique**

- Vous souhaitez **tirer parti d’un opérateur pour les services d’audioconférence avec un modèle de paiement à la minute**, par exemple utiliser des numéros gratuits et effectuer des appels sortants de réunions Teams vers des numéros de téléphone dans les pays non inclus dans votre abonnement

## <a name="licensing-requirements-and-billing"></a>Exigences en matière de licences et facturation

Les utilisateurs qui ont besoin de Conférence en connexion à l'opérateur numéros pour participer aux réunions qu’ils organisent doivent disposer d’un abonnement Microsoft AudioConférence Standard ou d’une licence Microsoft Conférence en connexion à l'opérateur qui leur est attribuée.

### <a name="audio-conferencing-standard-subscription"></a>Abonnement Standard à l’audioconférence

Un abonnement Microsoft AudioConférence Standard peut être acheté en tant que module complémentaire à une licence Microsoft Teams et est également inclus dans les abonnements Microsoft 365 E5 et Office 365 E5.

L’abonnement Standard d’audioconférence permet aux abonnés d’utiliser des numéros de téléphone de Microsoft et d’étendre leurs ponts d’audioconférence avec des numéros d’un opérateur. Les abonnés peuvent également choisir les appels sortants des réunions Teams à acheminer via Microsoft et les appels à acheminer via un opérateur.

Pour plus d’informations, consultez [**Configurer Conférence en connexion à l'opérateur**](operator-connect-conferencing-configure.md).

### <a name="operator-connect-conferencing-license"></a>licence Conférence en connexion à l'opérateur

Une licence Microsoft Conférence en connexion à l'opérateur peut être acquise en tant que module complémentaire à une licence Microsoft Teams.

La licence Conférence en connexion à l'opérateur permet aux abonnés d’utiliser les numéros de téléphone d’un opérateur, mais elle n’inclut pas les numéros de téléphone de Microsoft. Tous les appels sortants à partir de réunions Teams doivent être routées via un opérateur.

Pour plus d’informations, consultez [**Configurer Conférence en connexion à l'opérateur**](operator-connect-conferencing-configure.md).

>[!Note]
>Les participants à la réunion n’ont pas besoin d’une licence d’abonnement Standard d’audioconférence ou d’une licence Conférence en connexion à l'opérateur pour participer à une réunion organisée par un utilisateur disposant de fonctionnalités Conférence en connexion à l'opérateur.

Avec Conférence en connexion à l'opérateur, Microsoft facture votre organisation en fonction du type de licence d’audioconférence utilisée par votre organisation, de l’audioconférence Microsoft ou Conférence en connexion à l'opérateur, ainsi que de l’utilisation de tous les numéros de téléphone fournis par Microsoft.

Votre opérateur facture à votre organisation l’utilisation de Conférence en connexion à l'opérateur numéros qu’il fournit.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Informations supplémentaires sur l’audioconférence Microsoft

L’audioconférence Microsoft permet aux participants de participer à des réunions Microsoft Teams en entrant avec un numéro de téléphone RTC ou en composant un numéro de téléphone RTC. Pour plus d’informations sur les fonctionnalités d’audioconférence Microsoft disponibles pour votre organisation, consultez [audioconférence dans Microsoft 365](audio-conferencing-in-office-365.md).
