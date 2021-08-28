---
title: 'Application Patients pour les administrateurs Teams '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: En savoir plus sur application Patients pour les administrateurs Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 61b363af8d77c907ee2166fd0ee29da2d8119fde
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595068"
---
# <a name="patients-app-overview"></a>Présentation de l’application Patients

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui soutien l’équipe. Toutes les données associées à l’application Patients sont conservées dans ce groupe mais ne sont plus accessibles via l’interface utilisateur. Les utilisateurs peuvent re-créer leurs listes à l’aide de l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Les listes permet aux équipes de soins de votre organisation de santé de créer des listes de patients pour différents scénarios (arrondis, réunions d’équipe de formation, surveillance générale des patients, etc.). Pour commencer, consultez le modèle Patients dans listes. Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, consultez [Gérer l’application Listes](../../manage-lists-app.md).

L’application Patients est une application du Store Microsoft Teams disponible pour tous les utilisateurs de Teams. L’application permet aux équipes de santé des patients composées de travailleurs cliniques (par exemple, les membres du personnel médical, les travailleurs sociaux) d’organiser et de passer en revue des listes de patients pour différents scénarios (rondes, réunions d’équipe de recherche, surveillance générale des patients, etc.).

L’application a deux modes :

- Mode connecté EMR qui se connecte aux EMR via FHIR (Fast Healthcare Interoperability Resources). L’application mode connecté EMR reste en mode privé (préversion) et les clients ou administrateurs intéressé peuvent demander l’accès à l’application en déposant un message électronique sur [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) avec des informations sur leur organisation Microsoft 365.
- Le mode manuel qui permet aux équipes de santé d'ajouter/introduire manuellement des informations sur les patients. L’application est disponible dans le magasin d’applications Teams, que les utilisateurs finaux peuvent télécharger en préversion privée. L’application peut être limitée à certaines sections d’utilisateurs à l’aide des [stratégies de configuration des applications](../../teams-app-setup-policies.md) dans Teams. Pour accéder à l’application, votre client doit participer au Programme d’adoption des technologies (TAP). Envoyez-nous un e-mail à [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) pour démarrer le processus de demande d’accès.

## <a name="usage-example"></a>Exemple d’utilisation

Au cours des séances de ronde de chaque équipe dans les services médicaux, les cliniciens se réunissent au poste de soins infirmiers pour discuter des dernières mises à jour sur l'évolution des patients dans le service.  Ils mettent en évidence les mesures critiques clés (pas nécessairement médical ou explicites sur les dossiers médicaux des patients) et garantissent que le patient est sur la bonne voie vers la sortie en fonction de son diagnostic. Pour faire le tour de ces patients, l'infirmière responsable configure l'application patient dans une équipe où tous les cliniciens sont présents et ajoute les patients à une liste de patients. Pendant les rondes, les infirmières et les autres soignants du patient accèdent à Microsoft Teams et à l'application Patients sur leurs appareils mobiles et mettent à jour les informations pertinentes sur le patient sur leur appareil, puis tous les autres membres de l'équipe de santé peuvent voir ces mises à jour et ces notes et rester synchronisés. Deux fois par jour, au début et à la fin d'une garde, ils organisent également des réunions d'équipe multidisciplinaires pour passer en revue la liste des patients et utiliser l'application Patients pour s'exprimer et partager des informations sur chaque patient à l'aide de l'application Patients sur un grand écran. Parfois, certains cliniciens peuvent également se participer à distance à ces réunions Teams et participer à la discussion.

## <a name="configure-patients-app"></a>Configurer l’application Patients

Voir [Gérer les stratégies de configuration d’Microsoft Teams](../../teams-app-setup-policies.md) pour activer l’application Patients pour votre organisation.

Pour plus d'informations sur la manière dont vos utilisateurs finaux peuvent accéder à l'application Patients et l'installer sur une équipe dont ils sont propriétaires ou qu'ils gèrent, cliquez ici, voir [Prise en main de Patients de Microsoft Teams](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Forum aux questions (FAQ)

**Où sont stockées les données de l’application Patients ?**

Toutes les données entrées par les utilisateurs finaux dans l’application Patients, y compris le schéma des colonnes/champs, les données réelles entrées dans la liste et les éléments de liste (c’est-à-dire les patients), sont stockées dans l’infrastructure Exchange Online sécurisée et compatible. Toutes les données sont stockées dans la boîte aux lettres de groupe associée à l’équipe. Cette architecture permet à l'application Patients de satisfaire facilement aux exigences en matière de résidence des données, de prise en charge du cloud pour le secteur public (à venir) et d'autres fonctions de conformité et de protection de l'information, comme la prise en charge de la découverte électronique. L’application Patients fonctionne dans une étendue d’équipe. Vous devrez installer une instance de l’application par équipe.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**Où puis-je me procurer l'application Patients ?**

Si l’application Patients est activée pour son organisation par son administrateur, tout utilisateur final peut se rendre dans le magasin d’applications Teams et ajouter l’application Patients à une équipe dont il est membre. Pour plus d’informations, consultez [Gérer les stratégies de configuration d’application dans Microsoft Teams](../../teams-app-setup-policies.md).

**Puis-je avoir plusieurs instances de l’application Patients dans une équipe, car c’est le fonctionnement de ma cellule/unité ?**

Pour l’instant, vous ne pouvez installer qu’une seule instance de l’application Patients pour une équipe donnée, et uniquement dans le canal général. Toutefois, au sein de l’application, plusieurs listes peuvent être créées pour traiter les scénarios multi-canal ou d’origine/séparation. Par défaut, tous les membres de l’équipe ont accès à l’onglet Patients dans le canal général. 

**Puis-je exporter toutes les données à partir de l’application Patients ?**
Pas pour l’instant, mais cette fonctionnalité sera bientôt disponible. 

**Étant donné que cette application est hébergée sur PHI, y a-t-il un audit pour empêcher tout accès non autorisé ou la conformité non autorisée aux réglementations ?**

Oui. Chaque action d’interface utilisateur effectuée par un utilisateur de Microsoft Teams dans l’application Patients est auditée et disponible dans le Centre de sécurité et conformité. Les détails sont expliqués dans [Journaux d'audit pour l'application Patients](patients-audit.md).

