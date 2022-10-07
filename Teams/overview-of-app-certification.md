---
title: Vue d’ensemble de la certification des applications par Microsoft
description: Découvrez le programme de conformité de l’application Microsoft 365 pour la sécurité, la conformité et la confidentialité des applications tierces.
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.date: 09/22/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 992b557e72aaa855008f1bfec8073d800b65badf
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377542"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>Programme de conformité de l’application Microsoft 365 pour la sécurité, la conformité et la confidentialité des applications tierces

Le programme de conformité Microsoft vérifie et audite une application par rapport à des contrôles dérivés des infrastructures de pointe liées aux normes du secteur d’activité. Le programme démontre que de solides pratiques de sécurité et de conformité sont en place pour protéger les données clients. Le programme comprend les phases suivantes :

* [Vérification du serveur de publication](#publisher-verification).
* [Attestation du serveur de publication](#publisher-attestation).
* [Certification Microsoft 365](#microsoft-365-certification).

## <a name="publisher-verification"></a>Vérification de l’éditeur

Avant qu’un développeur d’application ne puisse soumettre son application à Microsoft, il doit faire l’objet d’une vérification. Un développeur vérifie son identité à l’aide de son compte Microsoft Partner Network (MPN) et associe ce compte MPN à son inscription d’application. La vérification de l’éditeur aide les administrateurs et les utilisateurs finaux à comprendre l’authenticité des développeurs d’applications. La vérification Publisher offre les avantages suivants :

* Transparence accrue et réduction des risques pour les clients : cette fonctionnalité permet aux clients de comprendre quelles applications utilisées dans leur organisation sont publiées par les développeurs auxquels ils font confiance.
* Amélioration de la personnalisation : un badge `verified` s’affiche dans l’invite de consentement Azure Active Directory, la page des applications d’entreprise et d’autres interfaces utilisateur utilisées par les utilisateurs finaux et les administrateurs.
* Adoption plus fluide de l’entreprise : les administrateurs peuvent configurer des stratégies de consentement de l’utilisateur, avec l’état de vérification de l’éditeur comme critère de stratégie principal.

## <a name="publisher-attestation"></a>Attestation Publisher

L’attestation Publisher est le niveau suivant dans le programme de conformité des applications. Les applications attestées par l’éditeur assurent une confiance des administrateurs quant aux mesures de sécurité et de conformité d’une application. Cela permet également de réduire le temps d’examen de ces informations pour une application. L’attestation reflète les pratiques de sécurité, de gestion des données et de conformité d’une application par rapport à plus de 80 facteurs de risque identifiés par [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security). Le processus d’attestation de l’éditeur peut commencer avant la fin de la vérification de l’éditeur.

Les développeurs d’applications sont invités à effectuer une auto-évaluation qui inclut des questions fréquemment posées par les clients et les administrateurs informatiques pour évaluer la sécurité et la conformité d’une application. Microsoft publie ensuite ces informations pour une évaluation plus facile et plus rapide. Pour en savoir plus, consultez le [Guide d’attestation](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

Les administrateurs peuvent rapidement rechercher les applications attestées publiées de trois manières différentes.

* Lorsque vous collectez plus d’informations sur une application, consultez les détails d’une application spécifique sur son lien dans [Sécurité et conformité des applications Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps). Vous pouvez également sélectionner le lien `Publisher attestation` dans le [Centre d’administration Teams](https://admin.teams.microsoft.com/).

  :::image type="content" source="media/attested-app-tac3.png" alt-text="Dans le Centre d’administration Teams, sélectionnez le lien d’attestation Publisher pour afficher les détails de l’attestation d’une application.":::

* Dans le Centre d’administration Teams, lorsque vous vérifiez les détails d’une application à partir de la page **[Gérer l’application](https://admin.teams.microsoft.com/policies/manage-apps)**, consultez l’icône attestée de l’éditeur sur la bannière dans la page de détails de l’application.

  :::image type="content" source="media/attested-app-tac1.png" alt-text="Dans le Centre d’administration Microsoft Teams, l’icône attestée par Publisher s’affiche sur toutes les applications attestées.":::

* Dans le Centre d’administration Teams, avant [d’accorder des autorisations à l’application](app-permissions-admin-center.md), une coche bleue devant le nom de l’application indique qu’il s’agit d’une application attestée par un éditeur. Toutes les applications Microsoft 365 passent également par l’attestation d’éditeur. Par conséquent, une coche bleue s’affiche également pour les applications Microsoft 365.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Dans le Centre d’administration Microsoft Teams, dans la boîte de dialogue pour accorder des autorisations, la coche bleue indique qu’il s’agit d’une application attestée par un éditeur.":::

La page des détails de l’attestation pour une application attestée ou certifiée répertorie les détails suivants.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Informations détaillées fournies pour les applications attestées.":::

## <a name="microsoft-365-certification"></a>Certification Microsoft 365

La certification des applications s’effectue via la procédure suivante :

* Révision d’un analyste qualifié.
* Approbation par un analyste qualifié d’une évaluation complète centrée sur les infrastructures, processus et procédures de sécurité et de conformité d’une application.

Nous vérifions l’application par rapport à une série de contrôles de sécurité dérivés d’infrastructures de pointe liées aux normes du secteur d’activité.

Le certificat illustre les pratiques de sécurité et de conformité fortes en place pour protéger les données client lorsque l’application est utilisée dans une organisation. Pour plus d’informations sur la façon dont les administrateurs et les utilisateurs finaux bénéficient de la certification, consultez [Vue d’ensemble du programme de conformité des applications Microsoft 365](/microsoft-365-app-certification/docs/enterprise-app-certification-guide).

Les administrateurs peuvent vérifier rapidement la présence d'applications certifiées Microsoft 365 de la manière suivante.

* Lorsque vous collectez plus d’informations sur une application sur le web, consultez l’icône du bouclier dans [Documentation Microsoft sur l’application](/microsoft-365-app-certification/teams/teams-apps).

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="Consultez les informations sur la certification Microsoft 365 dans l'article d'aide détaillé sur la sécurité et la conformité d'une application":::

* Lors de la vérification d’une application dans le [Centre d’administration Teams](https://admin.teams.microsoft.com/policies/manage-apps), triez la liste des applications à l’aide de la colonne Certification. Affichez l’icône et, éventuellement, sélectionnez le lien pour accéder à la page spécifique à l'application mentionnée ci-dessus.

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Afficher le statut de certification Microsoft 365 d'une application dans le centre d'administration Teams." lightbox="media/m365cert-apps-list2.png":::

* Lorsque vous affichez les détails d’une application, consultez l’icône Microsoft 365 certifiée dans la bannière de l’application.

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Afficher les informations relatives à la certification Microsoft 365 dans la bannière de l'application lors de la gestion d'une application spécifique dans le centre d'administration de Teams.":::

* Dans le Centre d’administration Teams, avant [d’accorder des autorisations à l’application](app-permissions-admin-center.md), une coche bleue devant le nom de l’application indique qu’il s’agit d’une application attestée par un éditeur. Toutes les applications Microsoft 365 passent également par l’attestation d’éditeur. Par conséquent, une coche bleue s’affiche également pour les applications Microsoft 365.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Dans le centre d'administration Teams, dans la boîte de dialogue d'octroi des autorisations, les administrateurs peuvent cocher la case bleue pour s'assurer que l'application est certifiée Microsoft 365":::

## <a name="view-security-compliance-and-privacy-information"></a>Afficher les informations de sécurité, de conformité et de confidentialité

Vous trouverez des informations sur la sécurité, la confidentialité, la conformité et les comportements d’une application attestée ou certifiée dans la [Documentation Microsoft](/microsoft-365-app-certification/teams/teams-apps) et le [Centre d’administration Teams](https://admin.teams.microsoft.com/policies/manage-apps).

### <a name="microsoft-documentation"></a>Documentation Microsoft

Vous trouverez les détails sur la sécurité, la confidentialité, la conformité et bien plus encore pour chaque application répertoriée dans les articles d’aide propres à l’application liés à [Sécurité et de conformité des applications Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Informations détaillées fournies pour les applications qui sont soumises au programme de conformité de Microsoft.":::

### <a name="teams-admin-center"></a>Centre d’administration Microsoft Teams

Lors de l’évaluation d’une application, vous pouvez utiliser des CASB (Cloud Access Security Broker) indépendants, tels que MCAS (Microsoft Cloud App Security), pour trouver des informations sur la sécurité et les comportements d’une application. Le Centre d’administration Teams inclut des informations de sécurité et de conformité provenant de MCAS pour les applications certifiées Microsoft 365. Consultez ces informations dans la page des détails de l’application pour vérifier si l’application répond à vos besoins de sécurité.

> [!NOTE]
> Cette fonctionnalité est disponible pour tous les administrateurs, que votre organisation dispose ou non d’une licence qui prend en charge MCAS.

Pour accéder aux informations MCAS d’une application :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Sélectionnez **Certification** pour trier les applications et envoyer (push) toutes les applications certifiées Microsoft 365 en haut du tableau.

1. Choisissez une application certifiée Microsoft 365.

1. Sélectionnez l’onglet **Sécurité et conformité** .

   :::image type="content" source="media/mcas.png" alt-text="Capture d’écran de l’onglet Sécurité et conformité du Centre d’administration Teams.":::

   Pour obtenir plus d’informations sur les fonctionnalités prises en charge pour l’application, sélectionnez la liste déroulante pour chaque catégorie.

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>Afficher la politique de confidentialité et les conditions d'utilisation d'une application

Dans le Centre d'administration de Teams, chaque page de détail des applications contient un lien vers la déclaration de confidentialité et les conditions d'utilisation de l'application.

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="Depuis le centre d'administration de Teams, les administrateurs peuvent accéder au lien vers la politique de confidentialité et les conditions d'utilisation de chaque application." lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>Articles connexes

* [Afficher les autorisations d’application et accorder le consentement de l’administrateur dans le centre d’administration Microsoft Teams](app-permissions-admin-center.md).
