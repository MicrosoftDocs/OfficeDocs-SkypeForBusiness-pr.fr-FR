---
title: 'Application Patients pour les administrateurs de Teams '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: En savoir plus sur l’application Patients pour les administrateurs de Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803502"
---
# <a name="patients-app-overview"></a>Présentation de l’application Patients

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’application [Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui constitue le fond de l’équipe. Toutes les données associées à l’application Patients sont conservées dans ce groupe, mais ne peuvent plus être accessibles via l’interface utilisateur. Les utilisateurs peuvent re-créer leurs listes à l’aide de [l’application Listes.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Grâce aux listes, les équipes de soins de votre organisation de soins peuvent créer des listes de patients pour des scénarios allant des arrondis et des réunions d’équipe de recherche à la surveillance générale des patients. Consultez le modèle Patients dans Listes pour commencer. Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, voir [l’application Gérer les listes.](../../manage-lists-app.md)

L’application Patients est une application du Microsoft Teams Store accessible à tous les utilisateurs de Teams. L’application permet aux équipes de santé des patients composées d’agents cliniques (par exemple, infirmières, infirmières, travailleurs sociaux) d’organiser et de passer en revue des listes de patients pour des scénarios allant des arrondis et des réunions d’équipe de recherche à la surveillance générale des patients.

L’application est en deux modes :

- Mode connecté EMR qui se connecte aux emrs via FEMBA. L’application EMR Connected mode reste en mode privé et les clients ou administrateurs intéressés peuvent demander l’accès à l’application en leur demandant un e-mail au [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) avec des informations sur leur organisation Microsoft 365.
- Mode manuel qui permet aux équipes d’état d’ajouter/apporter manuellement des informations sur les patients. L’application est disponible dans le magasin d’applications Teams que les utilisateurs finaux peuvent télécharger en prévisualisation privée. L’application peut être limitée à certaines sections des utilisateurs à l’aide de stratégies [de configuration d’application](../../teams-app-setup-policies.md) dans Teams. Pour accéder à l’application, votre client doit participer au programme d’adoption des technologies (TAP). Envoyez-nous un [e-mail teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) pour démarrer le processus de demande d’accès.

## <a name="usage-example"></a>Exemple d’utilisation

Lors de l’arrondi des sessions à chaque équipe de médecins, les médecins rassemblent à la station de l’urgence pour discuter des dernières mises à jour sur l’avancement des patients du groupe.  Ils mettent en évidence les mesures critiques clés (pas nécessairement médicales ou explicites sur les dossiers médicaux des patients) et s’assurent que le patient se trouve sur le chemin approprié pour être déchargé sur la base de son diagnostic. Pour arrondir autour de ces patients, l’infirmière à la charge définit l’application patient dans une équipe où tous les patients sont ajoutés et ajoute des patients à une liste de patients. Pendant les cycles, les infirmières et les autres personnes qui donnent les soins aux patients accèdent à Microsoft Teams et à l’application Patients sur leurs appareils mobiles, et met à jour les informations pertinentes sur le patient sur leur appareil. Tous les autres membres de l’équipe d’état peuvent consulter ces mises à jour et notes et rester synchronisés. Deux fois par jour, au début et à la fin d’un shift, elle propose également plusieurs réunions d’équipe pour faire le point sur la liste des patients et utiliser l’application Patients pour se baser sur chaque patient et partager des informations sur chaque patient à l’aide de l’application Patients sur un grand écran d’affichage. Il arrive souvent que certains membres participent également à ces réunions Teams à distance et font toujours partie de la discussion.

## <a name="configure-patients-app"></a>Configurer l’application Patients

Pour plus d’informations sur la préparation de votre environnement à l’utilisation de l’application Patients en mode EMR, voir Intégration d’enregistrements médicaux électroniques [dans Microsoft Teams.](patients-app.md) Vous devrez également consulter les stratégies de configuration de l’application [Gérer dans Microsoft Teams](../../teams-app-setup-policies.md) afin d’activer l’application Patients pour votre organisation.

Pour plus d’informations sur la façon dont vos utilisateurs finaux peuvent accéder à l’application Patients et l’installer à une équipe qu’ils possèdent ou gèrent, voir Prendre en charge [Microsoft Teams Patients.](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Forum aux questions (FAQ)

**Où sont stockées les données de l’application Patients ?**

Toutes les données entrées par les utilisateurs finaux dans l’application Patients, y compris le schéma de colonne/champ, les données réelles entrées dans la liste et les éléments de liste (c’est-à-dire les patients), sont stockées dans l’infrastructure Exchange Online sécurisée et conforme. Toutes les données sont stockées dans la boîte aux lettres de groupe associée à l’équipe. Cette architecture permet à l’application Patients de facilement répondre à la résidence de données, au support du cloud public (à venir) et à d’autres fonctionnalités de conformité/protection des informations telles que la prise en charge de la découverte électronique. L’application Patients fonctionne dans une étendue d’équipe. Vous devrez installer une instance de l’application par équipe.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**À partir d’où puis-je acquérir l’application Patients ?**

Si l’application Patients est activée pour leur organisation par leur administrateur, n’importe quel utilisateur final peut se rendre sur l’App Store Teams et ajouter l’application Patients à une équipe dont il est membre. Pour plus d’informations, voir [Gérer les stratégies de configuration d’application dans Microsoft Teams.](../../teams-app-setup-policies.md)

**Puis-je avoir plusieurs instances de l’application Patients dans une équipe, car c’est la manière dont mon unité/unité fonctionne ?**

Pour l’instant, vous ne pouvez installer qu’une seule instance de l’application Patients pour une équipe donnée, et uniquement dans le canal général. Toutefois, dans l’application, plusieurs listes peuvent être créées pour traiter les scénarios de multi-canal ou d’isolation/séparation. Par défaut, tous les membres de l’équipe ont accès à l’onglet Patients dans le canal général. 

**Puis-je exporter toutes les données à partir de l’application Patients ?**
Pas pour le moment, mais cette fonctionnalité sera bientôt disponible. 

**Étant donné que cette application est conforme à PHI, y a-t-il des audits pour empêcher tout accès non autorisé ou conformité avec les réglementations ?**

Oui, c’est vrai. Chaque action de l’interface utilisateur individuelle effectuée par un utilisateur de Microsoft Teams dans l’application Patients est auditée et disponible dans le Centre de sécurité et conformité. Les détails sont expliqués dans les [journaux d’audit pour l’application Patients.](patients-audit.md)

## <a name="related-topics"></a>Sujets associés

[Intégration des dossiers médicaux électroniques dans Microsoft Teams](patients-app.md)
