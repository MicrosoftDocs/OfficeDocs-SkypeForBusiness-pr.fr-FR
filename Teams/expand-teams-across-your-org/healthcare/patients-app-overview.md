---
title: 'Application patients pour les administrateurs teams '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Application patients pour les administrateurs teams
ms.openlocfilehash: 85f0d382de11b9259c6839aa8d0e556ad2512f5a
ms.sourcegitcommit: 2064c94eae82a5453674d38f0b28dcd6dc5c370e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "37885498"
---
# <a name="patients-app-overview"></a>Présentation de l’application Patients

L’application patients est une application Microsoft teams Store disponible pour tous les utilisateurs d’Teams. L’application permet aux équipes de soins du patient constituée de personnes cliniques (par exemple, infirmières, médecins, travailleurs sociaux) d’organiser et de réviser des listes de patients dans le cas de scénarios allant de segments et de réunions d’équipes interdisciplinaires à la surveillance générale du patient.   

L’application possède deux modes : 

- Le mode connecté EMR qui se connecte à EMRs via FHIR. L’application en mode connecté EMR reste en version privée prédéfinie, et les utilisateurs intéressés ou les administrateurs peuvent demander l’accès à l’application en déplaçant le message électronique de Microsoft sur teamsforhealthcare@service.microsoft.com contenant des informations sur leur client Office 365. 
- Le mode manuel qui permet aux équipes de soins d’ajouter/de mettre en place des informations relatives aux patients manuellement. L’application est disponible dans le magasin d’applications teams pour permettre aux utilisateurs finaux de télécharger par défaut une version d’évaluation publique. L’application peut être limitée à certaines sections d’utilisateurs à l’aide [de stratégies de configuration d’applications dans Microsoft teams](../../teams-app-setup-policies.md)



## <a name="usage-example"></a>Exemple d’utilisation

Au cours d’un arrondi dans le cadre d’une période de travail dans les soins médicaux, les médecins regroupent dans la station albattable des nouvelles mises à jour de l’évolution des patients.  Ils ont mis en surbrillance les métriques critiques principales (qui ne sont pas nécessairement médicales ou dont la mention est explicite sur les dossiers médicaux des patients) et permettent de s’assurer que le patient se trouve sur le chemin coulissant approprié pour se décharger en fonction du diagnostic. Pour arrondir ce qui est le cas, les soins d’une équipe fixent l’application du patient au sein d’une équipe où tous les médecins sont ajoutés et ajoutent des patients à une liste de patients. Pendant les arrondis, les infirmières et le Givers d’autres soins pour le patient accèdent à l’application Microsoft teams et au patients sur leurs appareils mobiles et mettent à jour les informations pertinentes du patient sur son appareil, puis tout autre membre de l’équipe de soins peut voir ces mises à jour et notes et Restez synchronisé. Deux fois par jour, au début et à la fin d’une équipe, il a également des réunions d’équipe displicinary pour passer à la liste des patients et utiliser l’application patients pour vous mettre en ligne et partager les informations relatives à chaque patient à l’aide de l’application patients sur un grand écran d’affichage. Dans la plupart des cas, certains cliniciens pourront également se connecter à distance à ces équipes et continuer à participer à la discussion. 

## <a name="configure-patients-app"></a>Configurer l’application patients

Pour plus d’informations sur la façon de préparer votre environnement pour l’utilisation de l’application patients en mode EMR, voir intégration des enregistrements de la [santé électronique dans Microsoft teams](patients-app.md). Vous devrez également consulter la rubrique [gérer les stratégies de configuration des applications dans Microsoft teams](../../teams-app-setup-policies.md) pour activer l’application patients pour votre organisation.

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

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

Oui, c’est. Chaque action de l’interface utilisateur exécutée par un utilisateur de Microsoft teams sur l’application patients est auditée et disponible dans le centre de sécurité et conformité. Les détails sont décrits dans [cet article.](patients-audit.md)


## <a name="related-topics"></a>Voir aussi

[Intégration des dossiers médicaux électroniques dans Microsoft Teams](patients-app.md)
