---
title: Prise en main de Teams pour les organismes de santé
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
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: En savoir plus sur les fonctionnalités de soins à la santé incluant la coordination des soins, la messagerie sécurisée, la visite virtuelle, l’intégration DMI et l’intégration du système de travail terrain.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 07f5e87a454091319775bf5e1124e2c4651ea736
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469550"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Prise en main de Teams pour les organismes de santé

Microsoft teams propose de nombreuses fonctions utiles pour les hôpitaux et les autres services de la santé. Les fonctionnalités d’équipes sont en cours de développement, ce qui permet aux hôpitaux de :

- Coordination et collaboration au service
- Messagerie sécurisée
- Visite virtuelle
- Intégration du DMI (Electronic Medical Recording)
- Intégration du système de travail terrain

Le contenu de cette section repose sur les fonctionnalités de base de teams, telles que les réunions, les appels et la messagerie, et suppose que vous avez déjà déployé des équipes au sein de votre organisation. Si vous n’avez pas encore déployé Teams, commencez par lire [la rubrique Comment déployer Microsoft teams](../../How-to-roll-out-teams.md).

## <a name="care-coordination---microsoft-teams-patients-app"></a>Coordination de la santé-application patients de Microsoft teams

> [!IMPORTANT]
> **À compter du 30 octobre 2020, l’application patients sera déconseillée et les utilisateurs ne pourront plus l’installer à partir de l’App Store d’Teams. Nous vous encourageons à commencer à utiliser l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans teams dès aujourd’hui.**
>
>Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe. Lorsque l’application patients est supprimée, toutes les données qui lui sont associées seront conservées dans ce groupe, mais ne seront plus accessibles par le biais de l’interface utilisateur. Les utilisateurs actuels peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>L' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) est préinstallée pour tous les utilisateurs d’teams et est disponible sous la forme d’une tabulation dans chaque équipe ou canal. Les listes permettent aux équipes de soins de créer des listes de patients à l’aide du modèle de patients intégré, de zéro à partir de zéro ou d’importer des données dans Excel. Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).

Microsoft teams dispose désormais d’une solution de coordination de soins adaptée aux organisations de santé pour leur permettre d’offrir la meilleure assistance pour le patient. Le Crux de la solution de coordination des soins, l’application Microsoft teams patients, est une application de l’onglet première partie qui s’intègre aux systèmes de dossiers d’intégrité par voie électronique (DMI) à l’aide d’une interface[FHIR](https://www.hl7.org/fhir/)(Fast Healthcare Interoperability Resources) pour permettre une collaboration et une communication cliniques.  

La solution de coordination de soins peut communiquer avec des éditeurs de logiciels indépendants leaders (ISV) qui peuvent connecter l’application patients à vos systèmes DMI en utilisant des normes de données d’état actuelles telles que HL7v2 et FHIR. Les partenaires Microsoft disposant des leaders suivants pour établir une intégration d’une santé électronique aux équipes :

- Datica (par le biais de leur offre [CMI](https://datica.com/compliant-managed-integration/) )
- Infor Cloverleaf (via [infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (par le biais du [serveur R ^ FHIR](https://www.redoxengine.com/fhir/))
- DapaSoft (via [Corolar sur FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Un partenaire d’intégration et d’interopérabilité DMI qui tente de mettre en œuvre Microsoft teams pour une organisation de prestataire de services de santé doit fournir une connexion sécurisée et authentifiée aux systèmes DMI de l’organisation du prestataire de services de santé. Cela permet d’activer le flux unidirectionnel (lecture seule) des dossiers médicaux pertinents dans l’application patients. L’application patients comprend le format FHIR, de sorte que le partenaire se charge également de transformer les données agrégées à partir de différents formats tels que HL7v2, etc., dans FHIR DSTU2 ou STU3.

L’application patients s’intègre aux systèmes de dossiers de santé électronique et permet aux fournisseurs de soins de communiquer sur le soin du patient en temps réel dans la plateforme sécurisée des équipes. L’application patients est le premier investissement important dans la zone de la coordination de soins qui vise à résoudre les problèmes suivants :

- Faible efficacité en matière de remise et de communication critique par le biais de l’interface du patient
- Informations de silo qui génèrent des charges d’administration
- Mécontentement des médecins grâce aux outils de collaboration complexes et fragmentés
- Une coordination de soins inefficace qui peut graver trop de temps cliniques.

Microsoft teams permet aux médecins, médecins, infirmières et aux autres membres du personnel de collaborer efficacement en :

- Faire partie d’une équipe virtualisée unique qui fonctionne et collabore sur des documents Office
- L’utilisation de conversations permanentes sur différents patients nécessite une attention
- Utilisation de canaux avec des onglets pour structurer leur tâche, avec une aide supplémentaire provenant des onglets pour lesquels ils peuvent épingler les sources d’informations
- Utiliser des réunions de canal avec les fonctionnalités audio, vidéo, de partage d’écran, de partage et de transcription de l’équipe pour gérer les réunions quotidiennes
- L’utilisation de l’application patients vous permet d’organiser une liste de patients à haut risque qui doivent être surveillés et d’extraire les informations les plus récentes du système DMI. L’application patients ajoute les fonctionnalités suivantes à Microsoft teams :
  - Possibilité de créer plusieurs listes de patients au sein d’un seul canal.
  - Possibilité d’afficher et de trier les informations affichées aux patients via des colonnes configurables.
  - Possibilité d’approvisionner automatiquement l’application par le biais d’un modèle d’équipe.
  - Disponible dans l’application teams pour iOS et Android pour les mobiles des premiers travailleurs de la santé, ainsi que le client Microsoft teams et le client de bureau.
  - La prise en charge des versions FHIR DSTU2 et STU3 par le biais de l’analyse de la déclaration de conformité.
  - Journaux d’audit pour toutes les actions d’affichage ou de recherche sur son interface

L’application patients repose sur la plateforme d’extensibilité des équipes et tire parti de l’infrastructure des onglets pour afficher le contenu du patient enrichi au sein d’un canal. Pour en savoir plus sur les autres applications teams et sur la plateforme elle-même, voir [applications pour Microsoft teams](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> L’application patients est en version d’évaluation privée et l’interface FHIR est en version bêta. Les versions finales ne sont pas censées être à compatibilité descendante.

![Capture d’écran de l’application patients sur un ordinateur de bureau et un appareil mobile](../../media/ehr-2.png)

Pour plus d’informations sur l’implémentation, voir [intégration d’enregistrements de santé électronique dans Microsoft teams](patients-app.md) .

## <a name="teams-templates"></a>Modèles teams

De nouveaux modèles de création d’équipes ont été développés pour s’appliquer à un environnement d’hôpital et de plus en plus sont prévus. Ainsi, il est plus facile de créer des équipes que les travailleurs de la santé utilisent pour coordonner les soins des patients dans divers services ou vers l’extérieur. Voir [commencer par les modèles d’équipes pour les entreprises de santé](healthcare-templates.md). Les équipes peuvent être démarrées pour les services internes tels que Cardiology ou pour les soins de niveau supérieur, et de plus en plus de modèles en développement.

## <a name="lists-app"></a>Application listes

L’application listes dans teams permet aux équipes de suivre les informations et d’organiser le fonctionnement. L’application est préinstallée pour tous les utilisateurs d’teams et est disponible sous forme d’onglet dans chaque équipe ou canal. Les listes peuvent être créées à partir de zéro, de modèles prédéfinis ou d’importation de données dans Excel.

Les équipes de soins peuvent utiliser le modèle patients pour commencer. Ils peuvent créer des listes pour suivre les besoins et l’état des patients. Les données du patient existantes dans les feuilles de calcul Excel peuvent être intégrées pour créer une liste dans Teams. Ces listes peuvent être utilisées pour des scénarios tels que des arrondis et la surveillance du patient pour coordonner les soins.

Par exemple, une infirmière de frais crée une liste de patients dans une équipe qui inclut tous les membres de l’équipe de soins. Au cours des arrondis, l’équipe de soins accède aux équipes sur leurs appareils mobiles et met à jour les informations relatives aux patients dans la liste, que tous les membres de l’équipe peuvent voir pour rester synchronisés. Dans le cas d’une session d’arrondi dans laquelle l’équipe de soins recueille et évalue les métriques de performances de fonctionnement clés pour s’assurer qu’un patient se trouve sur le chemin coulissant approprié, il peut partager ces informations à l’aide des équipes sur un grand écran d’affichage. Les membres de l’équipe qui ne sont pas sur le site peuvent rejoindre à distance.

Voici un exemple de liste qui a été configurée pour l’arrondi du patient.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Capture d’écran de la liste d’exemples pour arrondi du patient":::

Pour en savoir plus, voir [gérer l’application listes pour votre organisation dans teams](../../manage-lists-app.md).

## <a name="secure-messaging"></a>Messagerie sécurisée

La messagerie sécurisée prend en charge la collaboration dans les équipes de soins, y compris avec plusieurs nouvelles fonctionnalités :

- Un expéditeur de message peut définir une priorité spéciale pour le message, de sorte que le destinataire est prévenu de manière répétée jusqu’à ce qu’il Lise le message.
- Un expéditeur de message peut demander une confirmation de lecture, de sorte qu’il est prévenu de la lecture d’un message envoyé par le destinataire du message.

Ensemble, ces fonctionnalités permettent d’attirer plus rapidement les messages urgents et de veiller à ce que le message ait été reçu et lu. Les nouvelles équipes de soins utilisant ces fonctionnalités peuvent être créées par patient. Ces fonctionnalités sont basées sur des politiques qui peuvent être affectées à des personnes ou à des équipes entières.

Pour plus d’informations, voir [prendre en main des politiques de messagerie sécurisée pour les entreprises de santé](messaging-policies-hc.md) .

En outre, en ce qui concerne la sécurisation de la messagerie, c’est la possibilité d’avoir d’autres clients fédérés par le biais d’organisations de santé, autorisant une communication plus complète entre les clients. (Voir [gérer les accès externes dans Microsoft teams](../../manage-external-access.md)).

## <a name="firstline-worker-integration"></a>Intégration du travailleur terrain

Microsoft teams est intégré au Worker terrain, qui peut être utilisé pour coordonner les fonctions de personnel de décalage, etc. Voir [gérer l’application Shifts pour votre organisation dans Microsoft teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).
