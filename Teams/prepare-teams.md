---
title: "Améliorer votre environnement Skype Entreprise actuel pour Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Conseils pour commencer votre transition de Skype Entreprise vers Microsoft Teams"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb34e60e913926db1ddd6d71ea8a7d1c0d070cd2
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
<a name="optimize-your-current-skype-for-business-environment-for-microsoft-teams"></a>Améliorer votre environnement Skype Entreprise actuel pour Microsoft Teams
==============================================================

Tout changement nécessite du temps. Votre organisation doit prendre en compte des cycles de déploiement, une planification des ressources, une préparation technique et une gestion des changements. Nous nous efforçons d'assurer que Microsoft Teams réponde à vos besoins pour garantir le bon fonctionnement à long terme. En attendant, voici quelques conseils sur les préparations que vous pouvez appliquer dès aujourd'hui. En appliquant ces recommandations, vous pouvez assurer une implémentation de Teams réussie dans votre organisation.

## <a name="environmental-readiness"></a>Préparation de l'environnement


Les recommandations ci-après doivent être utilisées pour assurer le bon déroulement et l'intégrité de l'implémentation de Teams. Cela permettra de confirmer que votre environnement Skype Entreprise actuel est prêt pour le déploiement de Teams.   


### <a name="network-readiness-assessment"></a>Évaluation de la préparation réseau


Vous devez effectuer une *évaluation de la préparation du réseau* avant d'implémenter un produit de communications en temps réel tel que Teams. Une *évaluation de la préparation du réseau* est axée sur les performances réseau, la planification réseau, ainsi que sur d'autres aspects généraux de la mise en réseau, tels que les ports et les protocoles qui doivent être ouverts. Même si vous utilisez déjà un produit de communications en temps réel, tel que Skype Entreprise, l'*évaluation de la préparation du réseau* permettra de valider la préparation réseau.

Téléchargez le guide sur l'[évaluation de la préparation du réseau](https://go.microsoft.com/fwlink/?linkid=859069).

### <a name="my-advisor"></a>Mon conseiller


Tout au long de votre transition, nous vous recommandons d'utiliser le guide pratique que vous trouverez sur la page [Mon conseiller](http://aka.ms/myadvisor). Mon conseiller consiste en un guide complet en libre service et d'un ensemble d'outils pour la planification et la gestion de Teams et de Skype Entreprise Online pour la réussite de vos opérations.


### <a name="quality-assessment"></a>Évaluation de la qualité


Avant de commencer à intégrer vos utilisateurs à Teams, assurez-vous que le déploiement actuel de Skype Entreprise satisfait le niveau de qualité quant au multimédia en temps réel. Utilisez le tableau de bord de qualité des appels pour contrôler l'utilisation et identifier les tendances de qualité et l'analyse des appels pour résoudre les problèmes ou examiner les indicateurs de qualité pour des appels spécifiques.

Visionnez les [vidéos relatives au tableau de bord de qualité des appels](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos) pour obtenir des conseils sur l'utilisation du tableau de bord de qualité des appels dans le cadre de la vérification de la qualité des médias.

Pour en savoir plus sur l'analyse des appels, accédez à la page [Analyse des appels Skype Entreprise](https://support.office.com/article/Set-up-Skype-for-Business-Call-Analytics-fbf7247a-84ae-46cc-9204-2c45b1c734cd).

### <a name="quality-champion-role"></a>Rôle de Champion Qualité


Les organisations doivent identifier une personne ou un groupe de personnes pour attribuer le rôle de Champion Qualité. Le Champion Qualité examine les mesures de qualité par rapport à l'utilisation, et identifie les tendances et domaines à améliorer.

Le Champion Qualité est la personne à consulter concernant les difficultés liées à la qualité des appels et agit en tant qu'expert technique pour identifier les problèmes de qualité en examinant les tendances actuelles d'utilisation et de la qualité et en identifiant les mesures à prendre. Le champion qualité doit collaborer avec les équipes appropriées pour mettre en place des mesures correctrices, fournir des rapports à un comité directeur sur la progression et les problèmes ouverts. En général, le meilleur candidat au rôle de Champion Qualité est le responsable du service clientèle. En fonction de la taille et de la complexité de votre organisation, toute personne vivement intéressée par l'expérience utilisateur et qui dispose des compétences pour identifier les tendances peut agir en tant que champion qualité, avec le soutien adéquat pour collaborer avec d'autres équipes en vue de prendre des mesures.

Des informations sur le concept de champion qualité et les outils et techniques d'examen de la qualité sont disponibles sur la page [Manage a quality and reliable service delivery workshop (Gérer atelier de travail sur la livraison de services fiables et de qualité)](https://go.microsoft.com/fwlink/?linkid=859071).

## <a name="environmental-dependencies"></a>Dépendances de l'environnement


Teams combine plusieurs services Office 365 et dépend par conséquent de leur implémentation et opération correctes. Ces services incluent entre autres SharePoint Online, Exchange Online, et OneDrive Entreprise.

Bien que tous ne sont pas requis, il est vivement recommandé de les implémenter. Si vous décidez de ne pas implémenter certains services, cela affectera les fonctionnalités que Teams peut offrir à votre organisation. Par exemple, même si vous n'avez pas besoin d'implémenter SharePoint Online, certaines fonctionnalités de Teams reposent sur ce produit, telles que le partage de fichiers dans les groupes. L'absence de SharePoint Online affectera les fonctionnalités fournies par le client.

Consultez les articles suivants pour en savoir plus sur les conditions requises :
- [Groupes Office 365 et Microsoft Teams](Office-365-groups.md)
- [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md) 
- [Interaction entre Exchange et Teams](Exchange-Teams-interact.md)



