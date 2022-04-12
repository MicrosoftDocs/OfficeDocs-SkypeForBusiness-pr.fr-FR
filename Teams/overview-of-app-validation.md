---
title: Vue d’ensemble des tests et de la validation des applications par Microsoft
ms.reviewer: ''
description: Découvrez les contrôles de qualité et la validation des applications effectués pour les applications Teams.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fa6a03c5408afcd7cce1d3e48b78b3b1ddb3675a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/11/2022
ms.locfileid: "64756990"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Validation effectuée par Microsoft pour l’ensemble des applications Teams

Microsoft exige que toutes les applications passent une validation obligatoire avant d’être répertoriées dans le magasin pour les utilisations finales. Elle s’applique à l’ensemble des applications (à l’exception des applications personnalisées) publiées sur le magasin d’applications Teams. En outre, Microsoft encourage vivement les développeurs d’applications à participer à une certification facultative des applications qui indique les contrôles de conformité, de sécurité et de confidentialité améliorés.

Toutes les applications sont obligatoires pour respecter les stratégies de Certification d’application Microsoft. L’équipe du magasin Teams effectue plus de 400 tests pour vérifier que les applications sont utilisables et respectent les normes élevées de confidentialité et de sécurité.

Pour connaître les instructions de validation détaillées auxquelles les développeurs d’applications adhèrent, consultez les [Instructions de validation pour les développeurs](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). Les conseils sont basés sur les [Stratégies de certification des applications Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> La validation et les vérifications par Microsoft ne sont pas disponibles pour une application personnalisée, car elle est développée au sein de votre organisation et n’est disponible qu’aux membres de votre organisation.

## <a name="app-validation-and-testing"></a>Test et validation des applications

Nous exécutons plus de 400 cas de test pour chaque application avant sa mise à disposition sur le magasin Teams. Les tests garantissent des fonctionnalités, une expérience utilisateur et une sécurité appropriées et s’assurent que toutes les applications sont conformes aux stratégies CMO répertoriées publiquement. Voici quelques-uns des tests effectués par l’équipe de validation des applications Microsoft pour chaque application avant sa publication :

* Vérifiez que les autorisations Graph exigées par l’application sont réellement celles dont la fonctionnalité de l’application a besoin et non pas des autorisations supplémentaires. Les autorisations Graph pour les applications existantes sont régulièrement vérifiées pour vous assurer qu’aucune autorisation supplémentaire n’est exigée par une application.
* Les applications qui nécessitent que les utilisateurs se connectent disposent d’une option de déconnexion.
* Tous les éditeurs d’applications font l’objet d’un processus de vérification détaillé sur l’Espace partenaires Microsoft. La vérification inclut la vérification par e-mail, la vérification métier et bien plus encore. Pour en savoir plus sur la publication d’applications, consultez [Création d’un compte Espace partenaires par les développeurs](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Guide de soumission pour les développeurs](/office/dev/store/add-in-submission-guide) et [Publication d’applications par les développeurs](https://aka.ms/PublishToTeamsStore).
* Seules les applications des éditeurs vérifiés peuvent effectuer une recherche d’autorisations Graph auprès des utilisateurs finaux.
* Aucune application ne peut télécharger un fichier exécutable.
* Les applications sont testées pour ne pas contenir de publicités ou de promotions pour d’autres applications
* Les applications sont testées pour effectuer un travail approprié sans langage offensant, bots de cyberattaque, courriers indésirables ou contenu frauduleux.
* Tous les liens d’une application sont fonctionnels et liés uniquement à l’offre de l’application.
* Nous testons et évaluons régulièrement toutes les applications Teams publiées dans le cadre des contrôles d’intégrité du magasin d’applications.
* La politique de confidentialité et les Conditions d’utilisation qui couvrent les applications Teams sont publiées par l’éditeur de logiciels indépendants
* Les coordonnées de l’éditeur de logiciels indépendants sont disponibles dans la liste des magasins et dans leur [page d’attestation Publisher](/microsoft-365-app-certification/teams/teams-apps) respective.

En outre, Microsoft encourage les développeurs d’applications à participer à son programme de conformité qui est une approche rigoureuse et à deux niveaux pour garantir la qualité, la sécurité et la conformité des applications. Le magasin Teams a des centaines d’applications qui vont au-delà du respect des instructions de validation déjà détaillées et qui se conforment à ces programmes.

## <a name="publisher-verification"></a>Vérification de l’éditeur

Avant qu’un développeur d’application ne puisse soumettre son application à Microsoft, il doit faire l’objet d’une vérification. Un éditeur vérifie son identité à l’aide de son compte Microsoft Partner Network (MPN) et associe ce compte MPN à son inscription à l’application. La vérification Publisher aide les administrateurs et les utilisateurs finaux à comprendre l’authenticité des développeurs d’applications qui s’intègrent à la Plateforme d'identités Microsoft. La vérification Publisher offre les avantages suivants :

* Transparence accrue et réduction des risques pour les clients : cette fonctionnalité permet aux clients de comprendre quelles applications utilisées dans leur organisation sont publiées par les développeurs auxquels ils font confiance.
* Amélioration de la personnalisation : un badge `verified` s’affiche dans l’invite de consentement Azure Active Directory, la page des applications d’entreprise et d’autres interfaces utilisateur utilisées par les utilisateurs finaux et les administrateurs.
* Adoption plus fluide de l’entreprise : les administrateurs peuvent configurer des stratégies de consentement de l’utilisateur, avec l’état de vérification de l’éditeur comme critère de stratégie principal.

## <a name="see-also"></a>Voir aussi

* [Vue d’ensemble pour les administrateurs du Programme de conformité de l’application Microsoft 365](overview-of-app-certification.md)
