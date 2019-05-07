---
title: Prise en main de Teams pour les organismes de santé
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Prise en main de Teams pour les organismes de santé
ms.openlocfilehash: 7f68a21e835edb3b5ebcd8ff794f4fd3d0716bee
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632289"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Prise en main de Teams pour les organismes de santé

Teams Microsoft offre un certain nombre de fonctionnalités utiles pour les hôpitaux et d’autres organisations de santé. Fonctionnalités d’équipes sont en cours de développement à l’aide des hôpitaux avec :

- Coordination de soins
- Messagerie sécurisée
- Intégration de santé Record (EHR) électronique
- Intégration de travail Firstline

## <a name="care-coordination---microsoft-teams-patients-app"></a>Application de Patients des équipes de Coordination de soins - Microsoft

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams a maintenant une solution de coordination de soins spécifique aux organisations de santé pour les aider à répondre à leur but ultime de fournir la meilleure patients. L’essentiel de la solution de coordination de soins, l’application Microsoft équipes Patients, est une premier onglet application tiers qui s’intègre avec les systèmes (EHR) enregistrements électronique d’intégrité à l’aide d’une interface Fast les prestataires de ressources d’interopérabilité ([FHIR](https://www.hl7.org/fhir/)) afin de précieuses informations médicales dans Microsoft Teams.  

La solution de coordination de soins peut communiquer avec les meilleurs éditeurs de logiciels indépendants (ISV) qui peuvent se connecter l’application de Patients à vos systèmes DMI à l’aide des normes de données d’intégrité existantes, telles que HL7v2 et FHIR. Partenaires de Microsoft avec les leaders suivantes pour établir une relation d’intégrité électronique enregistrement intégration des équipes :

- Datica (par le biais de son offre [CMI](https://datica.com/compliant-managed-integration/) )
- Informations Cloverleaf (à l’aide du [Pont FHIR d’informations](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- REDOX (par le biais de la [R ^ server FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (via [Corolar sur FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

Une intégration DMI et l’interopérabilité partenaire tente d’implémenter Microsoft Teams pour une organisation de fournisseur de soins doit fournir à l’application de Patients une connexion sécurisée et authentifiée avec des systèmes EHR de l’organisation fournisseur de soins. Cela permet le flux (lecture seule) unidirectionnel des enregistrements pertinents patients dans l’application de Patients. L’application de Patients comprend le format FHIR, afin que le partenaire est également responsable pour transformer les données agrégées à partir de différents formats tels que HL7v2, etc. en FHIR DSTU2 ou STU3.

<br>

![Intégration DMI](../../media/ehr-1.png)

<br>

L’application de Patients s’intègre avec les systèmes d’enregistrements (EHR) médical et permet en charge des fournisseurs pour communiquer sur les patients dans en temps réel au sein de la plateforme sécurisée des équipes. L’application de Patients est la première investissement dans la zone de coordination de soins qui vise à relever les défis suivants :

- Peu efficaces livraisons et communication critique par le biais de l’expérience de patients
- Informations en silo qui crée charges administratives
- Grands mécontentements entre les médecins avec les outils de collaboration fragmenté et complexes
- Coordination des soins en personne inefficace que vous pouvez graver temps cliniques trop coûteux

Microsoft Teams permet les médecins, médecins, personnel et autres membres du personnel collaborer efficacement en :

- Faisant partie d’une seule équipe virtualisée qui fonctionne et collabore sur des documents Office
- Des conversations persistantes sur différents patients nécessitant une attention
- L’utilisation des canaux avec onglets comme moyen de structure de leur travail, avec une aide supplémentaire à partir des onglets à laquelle ils peuvent épingler sources d’information
- À l’aide de réunions de canal avec la puissance d’équipes audio, vidéo, partage d’écran, d’enregistrement et les fonctionnalités de transcription pour gérer les réunions quotidiennes
- Utilisation de l’application de Patients à curate une liste de patients à haut risque qui doit être surveillé et extrait les détails le plus récent à partir du système DMI. L’application de Patients elle-même ajoute les fonctionnalités suivantes à Teams Microsoft :

    - Possibilité de créer plusieurs patient répertorie dans une seule chaîne.
    - Possibilité d’afficher et de classer les informations affichées sur des colonnes peuvent être configurés par le biais des patients.
    - Possibilité de provisionnement automatique l’application via un modèle d’équipe.
    - Disponible sur l’application des équipes pour iOS et Android pour travailleurs mobiles de santé premier ainsi que les clients web et du bureau Microsoft Teams.
    - Prise en charge pour les versions de FHIR DSTU2 et STU3 par le biais de l’analyse d’une déclaration de conformité.
    - Journaux d’audit de toutes les actions de recherche et d’affichage sur son interface utilisateur pour remédier PHI par directives HIPAA.

L’application de Patients repose sur la plateforme d’extensibilité équipes et tire parti de l’infrastructure d’onglets pour afficher le contenu riche patient dans un canal. Pour en savoir plus sur les autres applications équipes et la plateforme elle-même, consultez les [applications pour les équipes Microsoft](/microsoftteams/platform/concepts/apps/apps-overview).  

> [!NOTE]
> L’application de Patients est en mode Aperçu privé et l’interface FHIR est dans la version bêta. Versions publiées ne devraient pas être compatibles.

![Capture d’écran de patients application](../../media/ehr-2.png)

Pour plus d’informations de mise en œuvre, voir [Intégration d’enregistrements de santé électroniques dans les équipes Microsoft](patients-app.md) .

## <a name="templates"></a>Modèles

Nouveaux modèles pour la création d’équipes ont été développés pour appliquer à un paramètre hôpital, et plus devraient bientôt. Il est ainsi plus facile de créer des équipes qui utilisent des professionnels de la santé pour coordonner des soins de patients dans différents départements ou longtemps. Voir [les modèles d’équipe pour les organisations de santé en main](healthcare-templates.md). Les équipes peuvent être démarrés pour les services internes tels que cardiologie, ou longtemps de soins, et des modèles plus dans le développement.

## <a name="secure-messaging"></a>Messagerie sécurisée

Sécuriser la messagerie prend en charge la collaboration au sein des équipes de soins, y compris plusieurs nouvelles fonctionnalités :

- Un expéditeur du message peut définir une priorité spéciale pour leur message, afin que le destinataire est informé à plusieurs reprises jusqu'à ce qu’ils lire le message.
- Un expéditeur du message peut demander une confirmation de lecture, afin qu’ils sont avertis lorsqu’un messages a été lu par le destinataire du message.

Ensemble, ces fonctionnalités permettent attention plus rapide aux messages urgents et que le message a été reçu et lecture de confiance. Nouvelle soignant à l’aide de ces fonctionnalités peut être créées sur une base par patient. Ces fonctionnalités sont basés sur la stratégie et peuvent être affectées aux utilisateurs individuels ou des équipes entières.

Pour plus d’informations, voir [stratégies de messagerie sécurisée pour les organisations de santé en main](messaging-policies-hc.md) .

## <a name="firstline-worker-integration"></a>Intégration de travail Firstline

Microsoft Teams s’intègre à Firstline travailleur, qui peut être utilisé pour coordonner les fonctionnalités de dotation en personnel MAJ et bien plus encore.

 Voir les articles suivants :

- [Atteindre vos équipes Microsoft StaffHub équipes dans Microsoft Teams](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [Gérer l’application Shifts pour votre organisation dans Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
