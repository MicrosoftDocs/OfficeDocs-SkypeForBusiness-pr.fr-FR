---
title: 'Application patients pour les administrateurs teams '
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
description: En savoir plus sur l’application patients pour les administrateurs teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b86c180bc809fa10b261738ae5b324737006f541
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772185"
---
# <a name="patients-app-overview"></a>Présentation de l’application Patients

> [!NOTE]
> À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale. Consultez le modèle patients dans les listes pour commencer. Pour en savoir plus sur la gestion de l’application listes dans votre organisation, voir [gérer l’application listes](../../manage-lists-app.md) .

L’application patients est une application Microsoft teams Store disponible pour tous les utilisateurs d’Teams. L’application permet aux équipes médicales du patient composées de travailleurs cliniques (par exemple, infirmières, médecins, travailleurs sociaux) de se réunir et de réviser des listes de patients dans le cas de scénarios allant de segments et de réunions d’équipe interdisciplinaires à la surveillance générale du patient.

L’application possède deux modes :

- Le mode connecté EMR qui se connecte à EMRs via FHIR. L’application en mode connecté EMR reste en version privée prédéfinie, et les administrateurs ou les clients concernés peuvent demander l’accès à l’application en déposant des messages Microsoft sur [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) avec des informations sur son organisation Microsoft 365.
- Le mode manuel qui permet aux équipes d’hygiène d’ajouter/de mettre en place des informations relatives aux patients manuellement. L’application est disponible dans le magasin d’applications teams pour que les utilisateurs finaux puissent télécharger la version privée préversion. L’application peut être limitée à certaines sections d’utilisateurs à l’aide de [stratégies de configuration d’application](../../teams-app-setup-policies.md) dans Teams. Pour pouvoir accéder à l’application, votre client doit faire partie du programme d’adoption de technologie (TAP). Envoyez-nous un e-mail à [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) pour démarrer le processus de demande d’accès.

## <a name="usage-example"></a>Exemple d’utilisation

Au cours d’un arrondi dans le cadre d’une période de travail dans les soins médicaux, les médecins regroupent dans la station albattable des nouvelles mises à jour de l’évolution des patients.  Ils ont mis en surbrillance les mesures critiques critiques (qui ne sont pas nécessairement médicales ou qui s’affichent sur les dossiers médicaux des patients) et permettent de s’assurer que le patient se trouve sur le chemin coulissant approprié pour se décharger en fonction du diagnostic. Pour arrondir ce qui est le cas, les soins d’une équipe fixent l’application du patient au sein d’une équipe où tous les médecins sont ajoutés et ajoutent des patients à une liste de patients. Pendant les arrondis, les infirmières et le Givers d’autres soins pour le patient accèdent à l’application Microsoft teams et au patients sur leurs appareils mobiles et mettent à jour les informations pertinentes relatives aux patients sur son appareil, et tous les autres utilisateurs de l’équipe d’État peuvent voir ces mises à jour et notes et rester synchronisées. Deux fois par jour, au début et à la fin d’une équipe, ils ont également des réunions d’équipe multidisciplinaires pour parcourir la liste des patients et utiliser l’application patients pour vous mettre en ligne et partager des informations sur chaque patient à l’aide de l’application patients sur un grand écran d’affichage. Dans la plupart des cas, certains cliniciens pourront également se connecter à distance à ces équipes et continuer à participer à la discussion.

## <a name="configure-patients-app"></a>Configurer l’application patients

Pour plus d’informations sur la façon de préparer votre environnement pour l’utilisation de l’application patients en mode EMR, voir intégration des enregistrements de la [santé électronique dans Microsoft teams](patients-app.md). Vous devrez également consulter la rubrique [gérer les stratégies de configuration des applications dans Microsoft teams](../../teams-app-setup-policies.md) pour activer l’application patients pour votre organisation.

Pour plus d’informations sur la façon dont vos utilisateurs finaux peuvent accéder à l’application patients et l’installer dans une équipe qu’elles possèdent ou gérer, voir [prendre en main Microsoft teams patients](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Forum aux questions (FAQ)

**Emplacement de stockage des données de l’application patients**

Toutes les données entrées par les utilisateurs finaux dans l’application patients, y compris le schéma de colonne/champ, les données réelles entrées dans la liste et les éléments de liste (par exemple, patients), sont stockées dans l’infrastructure Exchange Online sécurisée et conforme. Toutes les données sont stockées dans la boîte aux lettres de groupe associée à l’équipe. Cette architecture permet à l’application patients de répondre facilement aux informations de résidence, au support technique du cloud public (bientôt disponible) et aux autres fonctionnalités de conformité et de protection des informations telles que la prise en charge de eDiscovery. L’application patients fonctionne dans le cadre d’une équipe. Vous devrez installer une instance de l’application par équipe.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Où puis-je obtenir l’application patients ?**

Si l’application patients est activée pour son organisation par son administrateur, tout utilisateur final peut accéder à l’App Store et ajouter l’application patients à une équipe dont il est membre. Pour plus d’informations, consultez [gérer les stratégies de configuration des applications dans Microsoft teams](../../teams-app-setup-policies.md).

**Est-ce que je peux avoir plusieurs instances de l’application patients dans une équipe, car c’est la façon dont ma sortie fonctionne ?**

Pour l’instant, vous ne pouvez installer qu’une seule instance de l’application patients pour une équipe donnée, et uniquement dans le canal général. Néanmoins, au sein de l’application, plusieurs listes peuvent être créées pour gérer des scénarios de canaux multiples ou d’isolation/séparation. Par défaut, tous les membres de l’équipe ont accès à l’onglet patients dans le canal général. 

**Puis-je exporter toutes les données de l’application patients ?**
Pas pour l’instant, mais cette fonctionnalité sera bientôt disponible. 

**Dans la mesure où cette application prend en charge l’utilisation de PHI, est-ce que le contrôle empêche tout accès non autorisé ou conformité aux réglementations ?**

Oui, c’est. Chaque action de l’interface utilisateur exécutée par un utilisateur de Microsoft teams sur l’application patients est auditée et disponible dans le centre de sécurité et conformité. Les détails sont décrits dans les [journaux d’audit de l’application patients](patients-audit.md).

## <a name="related-topics"></a>Sujets associés

[Intégration des dossiers médicaux électroniques dans Microsoft Teams](patients-app.md)
