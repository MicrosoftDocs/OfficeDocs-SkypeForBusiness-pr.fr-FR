---
title: Planifier l’Connecter conférence de l’opérateur
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
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur les Connecter conférence téléphonique, telles que la exigences et la planification du déploiement.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257515"
---
# <a name="plan-for-operator-connect-conferencing"></a>Planifier l’Connecter conférence de l’opérateur

L’audioconférence Microsoft offre la possibilité d’appeler une conférence et d’appeler à partir d’une conférence à l’aide de numéros de téléphone de réseau téléphonique commuté (PSTN).  Les participants rejoignent Microsoft Teams réunion à l’aide d’un pont de conférence audio uniquement.

Grâce aux Connecter de conférence, les organisations peuvent utiliser les numéros de téléphone d’un opérateur tiers pour participer Microsoft Teams réunions. Si votre opérateur actuel fait partie du programme Connecter de l’opérateur Microsoft, vous pouvez ajouter des numéros de téléphone de votre opérateur à votre pont d’audioconférence et les utiliser pour participer à des réunions.

Sans opérateur Connecter de conférence, les organisations peuvent uniquement utiliser les numéros de téléphone fournis par Microsoft pour leur pont d’audioconférence.

>[!NOTE]
>Un fournisseur de numéros de téléphone qui fait partie du programme Connecter opérateur Microsoft est référencé dans cet article en tant qu'« opérateur ».
>
>Pour voir si votre opérateur participe au programme de mise Connecter’opérateur Microsoft, consultez l’Microsoft 365 [de l Connecter de recherche.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)

Cet article décrit l’opérateur Connecter conférence :

- [Avantages](#benefits)
- [Conditions de licence et facturation](#licensing-requirements-and-billing)
- [Informations supplémentaires sur l’audioconférence Microsoft](#additional-information-on-microsoft-audio-conferencing)

Pour plus d’informations sur la configuration de l’Connecter conférence, consultez Configurer l’Connecter [conférence.](operator-connect-conferencing-configure.md)

Si certains utilisateurs de votre organisation doivent effectuer des appels externes vers des numéros de téléphone PSTN, vous avez encore besoin d’un plan d’appel. Pour en savoir plus sur l’utilisation d’un opérateur tiers pour la connectivité PSTN externe, voir [Plan d’utilisation des](operator-connect-plan.md)Connecter.

## <a name="benefits"></a>Avantages

L’Connecter conférence offre les avantages suivants :

- **Attribution flexible de numéros de téléphone entre votre opérateur et Microsoft.** Utilisez des numéros de téléphone de Microsoft et de votre opérateur (avec un abonnement Microsoft Audio Conferencing Standard uniquement) ou uniquement des numéros de téléphone de votre opérateur (avec une licence d’opérateur Connecter Conferencing uniquement).

- **Infrastructure gérée par un opérateur.**   Votre opérateur gère les contrôleurs de session en bordure (SBCS) et l’interactivité avec Microsoft, ce qui vous permet d’économiser des composants additionnels et de gérer vos données.

- **Déploiement plus rapide et plus facile.**   Connectez-vous rapidement à votre opérateur et attribuez des numéros de téléphone à votre pont de conférence audio à partir du Teams d’administration.

- **Prise en charge et fiabilité améliorées.**   Les opérateurs fournissent un support technique et des contrats de niveau de service partagés afin d’améliorer la prise en charge du service, et l’peering direct optimisé par Azure crée une connexion réseau un-à-un pour une fiabilité accrue.

L Connecter conférence de conférence peut être la bonne solution pour votre organisation si :

- Vous voulez conserver **vos contrats avec** votre fournisseur de numéros de téléphone existant

- Vous voulez **développer la couverture globale de** votre pont d’audioconférence Microsoft existant

- Vous souhaitez **obtenir des numéros de téléphone pour l’audioconférence** à partir d’un nouveau fournisseur de numéros de téléphone

- **L’audioconférence Microsoft n’est pas disponible dans votre emplacement géographique**

- Vous souhaitez tirer parti d’un opérateur pour les services d’audioconférence avec un modèle de paiement à la **minute,** tel que l’utilisation de numéros gratuits et la appels sortants de réunions Teams vers des numéros de téléphone dans les pays qui ne sont pas inclus dans votre abonnement.

## <a name="licensing-requirements-and-billing"></a>Conditions de licence et facturation

Les utilisateurs qui ont besoin de numéros d’opérateur Connecter Conferencing pour participer aux réunions qu’ils organisent doivent avoir une licence Microsoft Audio Conferencing Standard ou une licence d’opérateur Microsoft Connecter Conferencing qui leur est affectée.

### <a name="audio-conferencing-standard-subscription"></a>Abonnement Audioconférence Standard

Un abonnement Microsoft Audio Conferencing Standard peut être acheté sous la la mesure d’un module logiciel à une licence Microsoft Teams et est également inclus dans les abonnements Microsoft 365 E5 et Office 365 E5 conférence.

L’abonnement Audioconférence Standard permet aux abonnés d’utiliser des numéros de téléphone de Microsoft et de développer leurs ponts d’audioconférence avec les numéros d’un opérateur. Les abonnés peuvent également choisir les appels sortants Teams les réunions à router via Microsoft et les appels à router via un opérateur.

Pour plus d’informations, [**voir Configurer l’Connecter conférence.**](operator-connect-conferencing-configure.md)

### <a name="operator-connect-conferencing-license"></a>Licence Connecter conférence de l’opérateur

Une licence de Connecter conférence de Microsoft peut être acquise en tant qu’module logiciel d’Microsoft Teams licence.

La licence Connecter conférence téléphonique permet aux abonnés d’utiliser les numéros de téléphone d’un opérateur, mais n’inclut pas les numéros de téléphone de Microsoft. Tous les appels sortants Teams vos réunions doivent être acheminés via un opérateur.

Pour plus d’informations, [**voir Configurer l’Connecter conférence.**](operator-connect-conferencing-configure.md)

>[!Note]
>Les participants à la réunion n’ont pas besoin d’une licence d’abonnement Standard d’audioconférence ou d’une licence d’opérateur Connecter Conférence pour participer à une réunion organisée par un utilisateur avec les fonctionnalités d’opérateur Connecter Conferencing.

Avec l’opérateur Connecter Conférence, Microsoft facture votre organisation en fonction du type de licence d’audioconférence utilisé par votre organisation, de l’audioconférence ou de l’opérateur Connecter conférence, et de l’utilisation des numéros de téléphone fournis par Microsoft.

Votre opérateur facture votre organisation pour l’utilisation des numéros d’Connecter conférence fournis par votre opérateur.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Informations supplémentaires sur l’audioconférence Microsoft

L’audioconférence Microsoft permet aux participants de participer à Microsoft Teams réunion en composant un numéro de téléphone PSTN ou en composant un numéro de téléphone PSTN. Pour plus d’informations sur les fonctionnalités de Microsoft Audioconférence disponibles pour votre organisation, consultez la conférence [audio dans Microsoft 365.](audio-conferencing-in-office-365.md)
