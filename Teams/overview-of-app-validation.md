---
title: Vue d’ensemble des tests et de la validation des applications par Microsoft
description: Découvrez les instructions de validation d’application Teams basées sur les stratégies de certification de la Place de marché. Découvrez comment Microsoft garantit que les applications Teams respectent des normes élevées de confidentialité et de sécurité.
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 08/11/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eeb0c49dcf560b858b8723f813cc86b6b51c1daa
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377552"
---
# <a name="testing-and-validation-done-by-microsoft-for-all-teams-apps"></a>Test et validation effectués par Microsoft pour toutes les applications Teams

Microsoft exige que toutes les applications passent une validation obligatoire avant d’être répertoriées dans le magasin pour les utilisations finales. Elle s’applique à l’ensemble des applications (à l’exception des applications personnalisées) publiées sur le magasin d’applications Teams. En outre, Microsoft encourage vivement les développeurs d’applications à participer à une certification facultative des applications qui indique les contrôles de conformité, de sécurité et de confidentialité améliorés.

Toutes les applications sont obligatoires pour respecter les stratégies de Certification d’application Microsoft. L’équipe du magasin Teams effectue plus de 400 tests pour vérifier que les applications sont utilisables et respectent les normes élevées de confidentialité et de sécurité.

Pour connaître les instructions de validation détaillées auxquelles les développeurs d’applications adhèrent, consultez les [Instructions de validation pour les développeurs](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). Les conseils sont basés sur les [Stratégies de certification des applications Teams](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> La validation et les vérifications par Microsoft ne sont pas disponibles pour une application personnalisée, car elle est développée au sein de votre organisation et n’est disponible qu’aux membres de votre organisation.

## <a name="app-validation-and-testing"></a>Test et validation des applications

Nous exécutons plus de 400 cas de test pour chaque application avant sa mise à disposition sur le magasin Teams. Les tests garantissent des fonctionnalités, une expérience utilisateur et une sécurité appropriées et s’assurent que toutes les applications sont conformes aux stratégies CMO répertoriées publiquement. Voici quelques-uns des tests effectués par l’équipe de validation des applications Microsoft pour chaque application avant sa publication :

* Vérifiez que les autorisations Graph exigées par l’application sont réellement celles dont la fonctionnalité de l’application a besoin et non pas des autorisations supplémentaires. Les autorisations Graph pour les applications existantes sont régulièrement vérifiées pour vous assurer qu’aucune autorisation supplémentaire n’est exigée par une application.
* Les applications qui nécessitent que les utilisateurs se connectent disposent d’une option de déconnexion.
* Les développeurs de toutes les applications subissent un processus de vérification détaillé sur l’Espace partenaires Microsoft. La vérification inclut la vérification par e-mail, la vérification métier et bien plus encore. Pour en savoir plus sur la publication d’applications, consultez [Création d’un compte Espace partenaires par les développeurs](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Guide de soumission pour les développeurs](/office/dev/store/add-in-submission-guide) et [Publication d’applications par les développeurs](https://aka.ms/PublishToTeamsStore).
* Seules les applications des développeurs vérifiés peuvent effectuer une recherche d’autorisations Graph auprès des utilisateurs finaux.
* Aucune application ne peut télécharger un fichier exécutable.
* Les applications sont testées pour ne pas contenir de publicités, promotion pour d’autres applications.
* Les applications sont testées pour effectuer un travail approprié sans langage offensant, bots de cyberattaque, courriers indésirables ou contenu frauduleux.
* Tous les liens d’une application sont fonctionnels et liés uniquement à l’offre de l’application.
* Nous testons et évaluons régulièrement toutes les applications Teams publiées dans le cadre des contrôles d’intégrité du magasin d’applications.
* La politique de confidentialité et les conditions d’utilisation qui couvrent les applications Teams sont fournies par le développeur d’applications.
* Les coordonnées du développeur de l’application sont disponibles dans la description du Store et dans leurs [pages d’attestation Publisher](/microsoft-365-app-certification/teams/teams-apps)respectives.

En outre, Microsoft encourage les développeurs d’applications à participer à son programme de conformité qui est une approche rigoureuse et à deux niveaux pour garantir la qualité, la sécurité et la conformité des applications. Le magasin Teams a des centaines d’applications qui vont au-delà du respect des instructions de validation déjà détaillées et qui se conforment à ces programmes.

## <a name="related-article"></a>Article connexe

* [Vue d’ensemble pour les administrateurs du Programme de conformité de l’application Microsoft 365](overview-of-app-certification.md)
