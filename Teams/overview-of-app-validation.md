---
title: Vue d’ensemble de la validation des applications et des tests d’application par Microsoft
ms.reviewer: ''
description: Comprendre les contrôles de qualité, la validation des applications et les programmes de certification pour Teams applications.
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
ms.openlocfilehash: 9accce27ded20f8ce78d4d5b80f6aff474213675
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64649017"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Vérifications et validation effectuées par Microsoft sur Teams applications

Microsoft exige que toutes les applications passent une validation obligatoire avant d’être répertoriées dans le Store pour les utilisations définitives. Il s’applique à toutes les applications (à l’exception des applications personnalisées) publiées sur le Teams App Store. En outre, Microsoft encourage vivement les développeurs d’applications à participer à une certification facultative des applications qui indique des contrôles de conformité, de sécurité et de confidentialité améliorés.

Toutes les applications sont obligatoires pour respecter les stratégies de certification des applications Microsoft. L’équipe du magasin Teams effectue plus de 400 tests pour s’assurer que les applications sont utilisables et respectent des normes élevées de confidentialité et de sécurité.

Pour connaître les instructions de validation détaillées auxquelles les développeurs d’applications adhèrent, consultez [les instructions de validation pour les développeurs](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

> [!NOTE]
> La validation et les vérifications par Microsoft ne sont pas disponibles pour une application personnalisée, car elle est développée au sein de votre organisation et n’est disponible que pour les membres de votre organisation.

<!--- TBD: Add the link later. 
To review the certification policies of any app, see [App certification policies]().
Is the link /microsoft-365-app-certification/teams/teams-apps
--->

## <a name="app-validation-and-testing"></a>Validation et test d’application

Nous exécutons plus de 400 cas de test pour chaque application avant sa mise à disposition sur le Teams Store. Les tests garantissent les fonctionnalités, l’expérience utilisateur et la sécurité appropriées, et garantissent que toutes les applications sont conformes aux stratégies CMO répertoriées publiquement. Voici quelques-uns des tests effectués par l’équipe de validation d’application Microsoft pour chaque application avant sa publication :

* Assurez-vous que Graph autorisations demandées par l’application sont réellement celles dont la fonctionnalité de l’application a besoin et non pas d’autorisations supplémentaires. Graph autorisations pour les applications existantes sont régulièrement vérifiées pour vous assurer qu’aucune autorisation supplémentaire n’est requise par une application.
* Les applications qui nécessitent que les utilisateurs se connectent ou se connectent doivent avoir une option de journalisation/déconnexion.
* Tous les éditeurs d’applications font l’objet d’un processus de vérification détaillé sur l’Espace partenaires Microsoft. La vérification inclut la vérification par e-mail, la vérification métier et bien plus encore. Pour en savoir plus sur la publication d’applications, consultez [comment les développeurs créent un compte Espace partenaires](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [guide de soumission pour les développeurs](/office/dev/store/add-in-submission-guide) et [comment les développeurs publient des applications](https://aka.ms/PublishToTeamsStore).
* Seules les applications des éditeurs vérifiés peuvent rechercher Graph autorisations auprès des utilisateurs finaux.
* Aucune application ne peut télécharger un fichier exécutable.
* Les applications sont testées pour ne pas contenir de publicités, promotion pour d’autres applications
* Les applications sont testées pour être adaptées sans langage offensant, bots de cyberattaque, courrier indésirable ou contenu frauduleux.
* Tous les liens d’une application sont fonctionnels et liés uniquement à l’offre d’application.
* Nous testons et évaluons régulièrement toutes les applications Teams publiées dans le cadre des contrôles d’intégrité de l’App Store.
* La politique de confidentialité et les conditions d’utilisation qui couvrent Teams applications sont publiées par l’éditeur de logiciels indépendants
* Les coordonnées de l’éditeur de logiciels indépendants sont disponibles dans la liste des magasins et dans leurs [pages d’attestation Publisher respectives](/microsoft-365-app-certification/teams/teams-apps).

## <a name="publisher-verification"></a>vérification Publisher

Publisher vérification aide les administrateurs et les utilisateurs finaux à comprendre l’authenticité des développeurs d’applications qui s’intègrent au Plateforme d'identités Microsoft. Le fait d’avoir un éditeur vérifié signifie que l’éditeur a vérifié son identité à l’aide de son compte MPN (Microsoft Partner Network) et a associé ce compte MPN à son inscription d’application.

Publisher vérification offre les avantages suivants :

* Transparence accrue et réduction des risques pour les clients : cette fonctionnalité permet aux clients de comprendre quelles applications utilisées dans leur organisation sont publiées par les développeurs auxquels ils font confiance.
* Amélioration de la personnalisation : un `verified` badge s’affiche dans l’invite de consentement Azure Active Directory, la page applications Enterprise et d’autres interfaces utilisateur utilisées par les utilisateurs finaux et les administrateurs.
* Adoption plus fluide de l’entreprise : les administrateurs peuvent configurer des stratégies de consentement de l’utilisateur, avec l’état de vérification de l’éditeur comme critère de stratégie principal.

En outre, Microsoft encourage les développeurs d’applications à participer à son programme de conformité qui est une approche rigoureuse à deux niveaux pour garantir la qualité, la sécurité et la conformité des applications. Teams store a des centaines d’applications qui vont au-delà du respect des instructions de validation déjà détaillées et se conforment à ces programmes.

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365 programme de conformité des applications

Le programme de conformité Microsoft montre qu’une application est contrôlée par rapport aux contrôles dérivés de frameworks standard de pointe du secteur et que des pratiques de sécurité et de conformité solides sont en place pour protéger les données client. Le programme comporte deux phases :

* Publisher attestation.
* certification Microsoft 365.

### <a name="publisher-attestation"></a>attestation Publisher

Le développeur d’applications doit effectuer une auto-évaluation qui inclut des questions fréquemment posées par les clients ou les administrateurs informatiques lorsqu’ils évaluent la sécurité et la conformité d’une application. Microsoft publie ensuite ces informations pour une évaluation plus facile et plus rapide. Ces informations incluent des détails sur la gestion des données, la sécurité, la conformité et la confidentialité lorsqu’une application est activée dans une organisation.

Pour plus d’informations, consultez le [guide d’attestation de publication](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

### <a name="microsoft-365-certification"></a>certification Microsoft 365

La certification des applications est obtenue par le biais de l’examen et de l’approbation d’un analyste qualifié d’une évaluation complète centrée sur les infrastructures, processus et procédures de sécurité et de conformité d’une application. L’application est contrôlée par rapport à une série de contrôles de sécurité dérivés de frameworks standard de premier plan du secteur. Le certificat montre que des pratiques de sécurité et de conformité solides sont en place pour protéger les données client lorsque l’application est activée dans une organisation.

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
