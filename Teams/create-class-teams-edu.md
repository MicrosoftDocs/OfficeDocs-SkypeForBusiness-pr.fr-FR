---
title: Méthodes recommandées et meilleures pratiques pour la création d’équipes de cours
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: Découvrez les méthodes recommandées et les pratiques recommandées pour créer des équipes de cours pour votre établissement scolaire.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e85ef79247bdf35c3c116504af23728a0d268ca5
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429326"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>Méthodes recommandées et meilleures pratiques pour la création d’équipes de cours

Microsoft Teams pour l’éducation offre des   [types d’équipe spécifiques](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)   pour l’utilisation scolaire. Le [type d’équipe de la classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) est conçue pour l’utilisation de la classe et inclut des fonctionnalités spécifiques qui prennent en charge les besoins de classe, notamment :  

- Affectations
- Notes
- Bloc-notes OneNote pour la classe  
- [Dossier matériaux de la classe](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  pour la sécurisation du contenu en lecture seule pour les étudiants
- [Accès initial aux enseignants](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) pour configurer la classe avant que les étudiants soient ajoutés 
- Possibilité de désactiver le son des étudiants et d’autres autorisations spéciales  

Plusieurs méthodes s’offrent à vous pour créer des équipes de classe, et les équipes pour l’éducation disposent d’un jeu unique d’outils de déploiement qui leur permet de rendre le plus simple possible. Plusieurs options s’offrent à vous pour vous aider à choisir le chemin de déploiement approprié qui correspond le mieux à vos besoins.  

## <a name="automatic-team-creation-using-sds"></a>Création automatique d’équipe à l’aide de SDS

**Cette fonctionnalité sera prochainement disponible, à la fin du 2020 juillet.**

L’automatisation de la création d’équipe permet aux administrateurs informatiques et aux enseignants de gagner du temps. Elle permet aux enseignants de créer des équipes de cours et de les configurer lors de la connexion. [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) est un outil de formation Office 365 gratuit qui lit les données du système d’enregistrement d’un établissement d’enseignement, par exemple, un système d’information sur les étudiants (SIS) ou un système de gestion des formations (LMS). SDS utilise les données pour enrichir la configuration d’Office 365 de nombreuses façons, notamment la création en bloc de équipes de cours et la synchronisation avec votre système d’information afin de maintenir la mise à jour de votre instructeur et de vos membres d’étudiant au fur et à mesure de la modification de l’inscription. SDS peut importer des données à partir de n’importe quel système d’enregistrement et intègre des connecteurs à la plupart des fournisseurs [SIS existants de](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support). Nous vous recommandons vivement d’utiliser SDS, car il présente les avantages suivants.  

### <a name="benefits"></a>Avantages

- Création et maintenance automatiques des équipes de cours : les enseignants pourront se connecter aux équipes et commencer immédiatement l’apprentissage.
- La synchronisation des membres avec SIS/LMS permet de gérer les modifications d’adhésion des étudiants.
- L’équipe de réussite des clients de l’UDE est disponible pour une assistance gratuite au déploiement.
- [Accès initial aux enseignants](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): les enseignants ont le temps de préparer leur équipe avant d’admettre les étudiants.  
- Vous pouvez également créer des utilisateurs et appliquer des licences Office 365.
- Crée des groupes de sécurité à utiliser dans Office 365, y compris la stratégie des équipes.
- Crée des unités d’administration pour la délégation d’administration étendue et [de réinitialisation du mot de passe d’enseignant](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset). 
- Erreurs intégrées et gestion des tentatives, limitation de limitation et stabilité de la session pour un traitement à grande échelle afin de réduire le travail des administrateurs.  
- Fonctionnalités de nettoyage intégrées renommez et archivez les groupes et les équipes une fois qu’ils sont obsolètes.
- [Synchronisation de qualité](https://docs.microsoft.com/schooldatasync/grade-sync): les enseignants peuvent faire leur classement dans les équipes et faire en sorte qu’elles réécrivent automatiquement les notes des équipes dans le SIS. 
- [Protection des données d’étudiant](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data) : empêcher les étudiants d’utiliser des applications non-Microsoft et suivre et gérer l’autorisation parentale. 
- Les données importées sont utilisées pour enrichir les informations de formation avec les rôles d’utilisateur, les organisations (établissements scolaires) et d’autres données importantes.  

### <a name="considerations"></a>Considérations

SDS crée des équipes en deux étapes. La première étape consiste à créer un groupe Microsoft 365 dans Azure Active Directory (Azure AD). la deuxième étape transforme automatiquement ce groupe en équipe. La deuxième étape de la création d’équipes est facultative dans SDS. Un administrateur peut ne pas vouloir créer automatiquement des équipes en fonction du temps de déploiement et du nombre d’équipes inutilisées pouvant en résulter. Nous recommandons aux établissements disposant de 500 000 équipes de désactiver le bouton de création automatique d’équipe dans SDS et d’utiliser la [méthode de création d’équipe disposant d’enseignant](#educator-led-team-creation-from-office-365-class-groups).  

### <a name="get-started"></a>Prise en main

Pour commencer, accédez à [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) et contactez [https://aka.ms/sdssupport](https://aka.ms/sdssupport) support de déploiement.  

## <a name="educator-led-team-creation-from-office-365-class-groups"></a>Création d’équipes dispensés d’enseignants à partir d’Office 365 groupes de classe

**Cette fonctionnalité sera prochainement disponible dans le centre d' 2020 août.**

La création d’une équipe dirigée par l’enseignant est une option de déploiement idéale si vous voulez permettre aux enseignants de créer facilement les cours dont ils ont besoin. Nous recommandons également que les établissements comptant plus de 500 000 équipes utilisent cette méthode pour réduire au minimum le nombre d’équipes créées à l’extérieur.  

Cette approche hybride vous permet d’utiliser SDS pour créer des groupes pour chaque classe (recommandé) ou d’utiliser [API Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes) pour les créer vous-même. Une fois les groupes de classes préparés, les enseignants peuvent convertir leurs groupes en équipes à l’aide de l’icône **Classes suggérées**.

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="Capture d’écran montrant l’icône de cours suggérés":::

### <a name="benefits"></a>Avantages

- [Accès initial aux enseignants](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): les enseignants ont le temps de préparer leur équipe avant d’admettre les étudiants.  
- Réduit le nombre d’équipes inutilisées et superflues. Les classes sont préparées et suggérées, mais pas créées, sauf si l’enseignant envisage de les utiliser. Nous vous recommandons d’utiliser cette option pour les grandes entreprises qui ont plus de 500 000 équipes afin de réduire l’encombrement.
- SDS
    - La synchronisation des membres avec SIS/LMS permet de gérer les modifications d’adhésion des étudiants.
    - L’équipe de réussite des clients de l’UDE est disponible pour une assistance gratuite au déploiement.
    - Vous pouvez également créer des utilisateurs et appliquer des licences Office 365.
    - Crée des groupes de sécurité à utiliser dans Office 365, y compris la stratégie des équipes.
    - Crée des unités d’administration pour la délégation d’administration étendue et [de réinitialisation du mot de passe d’enseignant](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset).
    - Erreurs intégrées et gestion des tentatives, limitation de limitation et stabilité de la session pour un traitement à grande échelle afin de réduire le travail des administrateurs. 
    - Fonctionnalités de nettoyage intégrées renommez et archivez les groupes et les équipes une fois qu’ils sont obsolètes. 
    - [Synchronisation de qualité](https://docs.microsoft.com/schooldatasync/grade-sync): les enseignants peuvent faire leur classement dans les équipes et faire en sorte qu’elles réécrivent automatiquement les notes des équipes dans le SIS. 
    - [Protection des données d’étudiant](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data) : empêcher les étudiants d’utiliser des applications non-Microsoft et suivre et gérer l’autorisation parentale. 
    - Les données importées sont utilisées pour enrichir les informations de formation avec les rôles d’utilisateur, les organisations (établissements scolaires) et d’autres données importantes.
- API Graph
    - Davantage de flexibilité et de contrôle.
    - Ne nécessite aucune intégration avec SDS.

### <a name="considerations"></a>Considérations

- Pas complètement automatisé et nécessite une action de l’enseignant.
- Les enseignants qui n’ont pas l’autorisation de créer des équipes peuvent continuer à créer des équipes à partir de groupes existants, comme illustré [ici](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- L’API Graph nécessite un haut niveau de compétences techniques et un temps de création et d’exécution du script et de résoudre les problèmes liés à la création de groupes de classes.

### <a name="get-started"></a>Prise en main

Pour commencer à utiliser la méthode SDS, accédez à [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) et contactez [https://aka.ms/sdssupport](https://aka.ms/sdssupport) support de déploiement. 

Pour utiliser la méthode de l’API Graph, voir [API Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) et [Créer une équipe de classe](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http).  

> [!NOTE]
> Pour utiliser cette méthode avec SDS, vous devez activer le bouton de création automatique de l’équipe dans votre profil SDS. Vous pouvez également utiliser une combinaison de création d’équipes disposées automatiquement et professeur pour les équipes de classe requises et facultatives à l’aide de deux profils SDS.

## <a name="powershell-script-using-graph-apis"></a>Script PowerShell à l’aide des API Graph

PowerShell vous permet de créer un script pour créer des équipes, des canaux et configurer les paramètres automatiquement. L’administrateur doit tout d’abord créer le groupe, ajouter des enseignants et des étudiants, puis créer l’équipe comme décrit [ici](https://docs.microsoft.com/graph/teams-create-group-and-team). Vous pouvez également utiliser l’API Microsoft Graph pour créer, configurer, cloner et archiver des équipes. Pour plus d’informations, voir [utiliser l’API Microsoft Graph pour utiliser Microsoft teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview), [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams) et [Créer une équipe de classe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type). L’utilisation des API Graph constitue un excellent moyen de disposer d’un contrôle et d’une flexibilité accrus, mais nécessite un haut niveau de compétences techniques et prend plus de temps pour la configuration initiale.  

### <a name="benefits"></a>Avantages

- Davantage de flexibilité et de contrôle.
- Option permettant de créer des équipes d’accès rapide aux enseignants ou un accès immédiat des étudiants aux équipes.  
- Si vous [Créer des équipes à partir de groupes](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group), les enseignants peuvent accéder en avant-première aux modifications apportées à l’appartenance au groupe Azure AD.

### <a name="considerations"></a>Considérations

- Nécessite un haut niveau de compétences techniques et le temps nécessaire pour créer et exécuter le script et résoudre les problèmes liés à la création de groupes de classes.
- Pas de gestion des erreurs intégrée ni de logique de nouvelle tentative.
- Les modifications d’appartenance ne sont pas synchronisées avec SIS. 

> [!NOTE]
> Les équipes de classe nécessitent une appartenance aux groupes masqués de sorte que seuls les enseignants et les étudiants au sein de la classe puissent voir les membres de cette classe. Pour créer un groupe de classes Office 365, voir [Créer une équipe de classe](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http) afin de respecter les mêmes exigences de confidentialité.

## <a name="manual-team-creation"></a>Création manuelle d’équipe

Les étudiants et les enseignants tirent le meilleur parti de Teams lorsqu’ils peuvent l'utiliser avec le minimum d'obstacles et avoir la souplesse nécessaire pour l'adapter à leurs besoins. L’une des façons dont les utilisateurs peuvent personnaliser leur expérience Teams est d'avoir la possibilité de créer des équipes. Les enseignants configurent leur propre équipe de type classe et invitent les étudiants comme illustré [ici](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch). Les enseignants peuvent inviter des étudiants en [ajoutant des étudiants à l’équipe](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), [partageant un code de jointure](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)ou [partageant un lien vers l’équipe](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Dans la mesure du possible, il est préférable que les enseignants ajoutent les étudiants à l’équipe pour leur en garantir l'accès et être sûr qu’ils soient informés de leur ajout dans une équipe.

### <a name="benefits"></a>Avantages

- Flexibilité supplémentaire pour les enseignants.
- Création et accès immédiat de l’équipe.  

### <a name="considerations"></a>Considérations

- Nécessite l’intervention et le temps de l’enseignant.
- Les membres de l’étudiant ne sont pas synchronisés avec SIS et nécessitent une gestion manuelle.
- N’offre pas aux enseignants un accès en avant-première à leur équipe. Les étudiants pourront y accéder immédiatement.

## <a name="recommended-best-practices"></a>Recommandations recommandées

- Déploiement précoce ! Déployez dès maintenant pour vous assurer que tout fonctionne correctement et prêt pour le premier jour de l’école. Si vous utilisez SDS, vous n’avez pas besoin de l’intégralité de l’appartenance aux étudiants pour démarrer le déploiement de SDS. Les étudiants sont synchronisés lorsque ces informations sont disponibles dans votre SIS.
- Si vous avez plus de 500 000 équipes, nous vous recommandons d’utiliser la méthode de création d’équipe disposant de [enseignant,](#educator-led-team-creation-from-office-365-class-groups). Il réduit les équipes inutilisées et le courrier pêle-mêle en créant uniquement des équipes de cours pertinentes et utiles.  
- S’il existe des problèmes (par exemple, des classes manquantes) avec la création automatique d’une équipe SDS et si les enseignants en ont besoin immédiatement, ils peuvent utiliser la [méthode de création d’équipe disposant de enseignant](#educator-led-team-creation-from-office-365-class-groups) pour réessayer. [La création manuelle d’une équipe](#manual-team-creation) est une autre solution, mais elle ne maintient pas la mise à jour de votre abonnement d’équipe.  
- La limite de l’équipe des clients est de 500 000 équipes. Par conséquent, les administrateurs doivent essayer de réduire le nombre d’équipes inutilisées de manière proactive afin d’éviter d’atteindre ces limites et de prolonger leur temps de configuration. Pour plus d’informations sur les limites, voir [Limites et spécifications pour Microsoft teams](limits-specifications-teams.md).  
