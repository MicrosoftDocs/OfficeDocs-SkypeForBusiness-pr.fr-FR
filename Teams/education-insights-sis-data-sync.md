---
title: Synchroniser les données du système d’information sur les élèves (SIE) avec Education Insights
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Synchronisez les données du système d’information sur les élèves (SIE) avec Education Insights dans Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b22b66800e71f1cea90c31b7091eb98a99466e9f
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363020"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Synchroniser les données du système d’information sur les élèves (SIE) avec Education Insights
Plus [Education Insights](class-insights.md) reçoit de données, plus les enseignants peuvent aider leurs élèves, et plus les responsables de l’éducation peuvent aider les enseignants.

Pour fournir des informations au niveau de l’organisation, nous devons utiliser la [Synchronisation des données scolaires (SDS)](/SchoolDataSync) pour nous connecter au système d'informations sur les élèves (SIE). Ainsi, Insights présentera la structure hiérarchique du système d’enseignement correctement mappée. 

L’affichage des informations au niveau de la classe en tant qu’enseignant *ne nécessite pas* cette synchronisation, car nous utilisons la structure et les autorisations de classe de Teams.

## <a name="plan-your-school-data-sync-integration"></a>Planifier l’intégration de votre Synchronisation des données scolaire
Synchronisation des données scolaires Microsoft (également connu sous le nom de SDS) fournit les données du système d'informations sur les élèves (également connu sous le nom de SIS) et sa structure hiérarchique du système d’enseignement et mappe l’utilisateur auquel il est attribué, ainsi que des données supplémentaires sur la hiérarchie des étudiants et de l’organisation.

Insights fonctionne parfaitement avec le [format de fichier SDS V2.1](/schooldatasync/sds-v2.1-csv-file-format), mais prend également en charge le [format de fichier SDS V2](/schooldatasync/sds-v2-csv-file-format) et [format de fichier SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds)*avec des fonctionnalités limitées*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Différences entre les formats de fichier SDS V1 et V2

| Type de données | V1 | V2 et V2.1 |
|:--- |:--- |:--- |
| **Utilisateurs** |Prend en charge uniquement le rôle « enseignant », par conséquent, les autorisations au niveau de l’organisation pour vos responsables de l’éducation doivent être définies manuellement|Prend en charge plusieurs rôles afin que les autorisations basées sur les rôles puissent être définies|
| **Organisations** | Prend en charge uniquement les « écoles », niveau d’agrégation.<br><br>Par conséquent, ne fournit pas plusieurs niveaux d’agrégation et offre une capacité limitée à comparer différents types d’établissements d’enseignement (par exemple, école primaire et secondaire, école de sciences et école d’art)|Prend en charge la hiérarchie multicouche, y compris les districts/institutions, les universités, les collèges, les facultés, les campus, les régions, les programmes, etc.<br><br>Permet plusieurs niveaux d'agrégation et de comparer facilement les unités organisationnelles à chaque niveau, d'attribuer des autorisations à des niveaux spécifiques, de définir des objectifs par niveau d'organisation, etc.|
| **Informations facultatives supplémentaires** |Aucun|**Format de fichier V2.1 uniquement**<br><br>*Sessions universitaires* : périodes de sessions (semestres, années scolaires, etc.)<br><br>Données démographiques et indicateurs d’étudiants* : données telles que la race, l’appartenance à l’origine et le sexe, ainsi que des programmes spéciaux (IEP, 504)|

> [!NOTE]
> Les clients ne pourront pas intégrer le format de fichier v2 à partir du 15 juillet 2021 et devront utiliser le format v2.1 à la place. Toutes les futures mises à niveau et nouvelles fonctionnalités seront effectuées au format v2.1 et seront entièrement à compatibilité descendante avec le format de fichier v1.

### <a name="best-practices"></a>Meilleures pratiques

Le mappage précis de la hiérarchie et de la place de chacun dans cette hiérarchie permet à Insights de fournir des données exactes, ainsi que des informations plus précises et plus adaptées aux différents types de responsables de l’éducation.

Plus vous fournirez de détails, plus les rapports et les actualités seront adapté et pertinents.

#### <a name="file-format-version-to-use-adn-data-to-sync"></a>Version de format de fichier à utiliser et données à synchroniser
*   Utiliser le format de fichier V2.1 et synchroniser les données facultatives utilisées par Education Insights comme décrit [ici](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv).

#### <a name="users-and-roles"></a>Utilisateurs et rôles
*   Vérifiez que **tous les utilisateurs** apparaissent dans les fichiers que vous fournissez et que vous avez synchronisés. Cela inclut tous les élèves et membres du personnel qui ont besoin de consulter les données relatives aux unités d’organisation concernées.
*   Si votre SIE n’inclut que des enseignants actuellement, ajoutez manuellement tous les autres utilisateurs avant de charger les fichiers dans le SDS, puis de synchroniser les données. Les statistiques collectées par Insights proviennent uniquement des étudiants inscrits, si certains étudiants sont manquants, ce qui rend les données et les conclusions erronées.
    
*   Si vous utilisez également SDS pour l’approvisionnement, veillez à **fournir le prénom et le nom de chaque utilisateur**. Sinon, les étudiants sont référencés par leur adresse e-mail, ce qui entraîne une expérience non optimale.

*   Le niveau de note/année doit être basé sur cette [liste de mappages ](#supported-grade-level-values). 

*   Veillez à **ajouter le niveau grade/année à tous les étudiants** .    

*   Veillez à affecter **chaque utilisateur à l’unité d’organisation correspondante**.

    *   Vous pouvez associer un étudiant à plusieurs unités d’organisation, par exemple, les étudiants inscrits dans un programme spécial ou dans deux facultés. Si l’étudiant a plusieurs unités d’organisation, fournissez une ligne pour chacun d’eux dans le fichier utilisateur de cet étudiant.
    
    *   L’administrateur informatique peut accorder des autorisations en fonction de l’unité d’organisation pour le personnel. **Assurez-vous que les membres du personnel sont associés au niveau d’unité approprié**, afin qu’ils reçoivent les autorisations dont ils ont besoin. Par exemple, un conseillé affecté à quatre établissements doit avoir accès à toutes les notes de ces établissements d’enseignement ; un chef d’établissement doit avoir accès à toutes les classes de son établissement. 
    
*   **Le rôle est essentiel**. Bien que cette liste soit fermée, essayez de faire correspondre le rôle de [la liste](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) au rôle réel de chaque utilisateur que vous chargez. Cela vous permet d’attribuer des autorisations basées sur les rôles en conséquence. Par exemple, accordez des autorisations pour que tous les chefs d’établissement voient les classes de leur établissement ou à tous les professeurs pour qu’ils voient leurs enseignants. 

#### <a name="organizations"></a>Organisations

* Veillez à **refléter la hiérarchie réelle et complète de votre organisation**. Dans certains cas, cette hiérarchie n’est pas reflétée dans le SIE, auquel cas elle doit être ajoutée manuellement au fichier CSV avant la synchronisation.

* Assurez-vous que **toutes les unités d’organisation de l’arborescence des organisations incluent les élèves ou les classes**. Nous vous recommandons de placer les élèves sur la branche la plus basse de l’arborescence.

> [!NOTE]
> Si vous souhaitez en savoir plus sur le déploiement de la SDS, veuillez consulter la rubrique [Planification de SDS](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-data-using-sds"></a>Intégrer des données SIE à l’aide de SDS

Nous fournissons la Synchronisation des données scolaires (SDS) avec Office 365 pour l’éducation. La SDS lit les données du système d’information sur les élèves (SIE) d’un établissement d’enseignement, puis les intègre à des applications Microsoft telles que Teams pour permettre la création automatique de salles de classe et d’utilisateurs en ligne.

Elle synchronise également les données du SIE avec Insights.

En tant qu’administrateur informatique, vous pouvez choisir d’utiliser SDS pour l’approvisionnement uniquement, Insights uniquement ou pour les deux.

Pour synchroniser vos informations SIE avec Educations Insights, suivez les instructions de [Comment déployer SDS pour Insights](/schooldatasync/how-to-deploy-sds-for-insights).

### <a name="deploy-sds"></a>Déployer la SDS
**Si vous utilisez déjà la SDS**, nous vous recommandons de suivre nos [meilleures pratiques](#best-practices). 

**Si vous n’utilisez pas encore la SDS**, vous devez à présent [la déployer](/schooldatasync/deploying-school-data-sync).

Pendant le processus de déploiement, vous pouvez décider si vous souhaitez utiliser SDS pour provisionner des utilisateurs et des classes dans Teams ou pour l’utiliser uniquement pour fournir la hiérarchie utilisateur et organisationnelle à Insights.

> [!NOTE]
> S’il s’agit du milieu de l’année et que vous avez déjà créé des équipes manuellement, utilisez SDS uniquement pour fournir les données de hiérarchie utilisateur et organisationnelle à Insights. L’année prochaine, envisagez d’utiliser SDS pour provisionner également des utilisateurs et des classes pour Teams.

### <a name="verify-the-sync-process"></a>Vérifier le processus de synchronisation
Pour vérifier la progression de l’état de synchronisation, suivez les instructions dans [SDS pour la santé et la surveillance des données Insights](/schooldatasync/sds-for-insights-data-health-and-monitoring).

> [!IMPORTANT]
> Si vous rencontrez des problèmes, [le support](https://aka.ms/edusupport) est là pour vous aider.

## <a name="supported-grade-level-values"></a>Valeurs de niveau scolaire prises en charge

Dans les fichiers SDS, niveau de scolaire/année défini en tant que valeurs sous-titres, ce qui signifie que vous ne pouvez fournir qu’un ensemble sélectionné de valeurs dans le fichier CSV. Toute valeur autre que les valeurs spécifiées entraîne une erreur lors du traitement de la synchronisation.

La section ci-dessous définit les valeurs pris en charge dans le fichier utilisateurs.

### <a name="united-states--worldwide-grade-levels"></a>Niveaux scolaires aux États-Unis/dans le monde
|Valeur dans le fichier (colonne Note) | Étiquette dans Insights|
|:---|:---| 
|IT|Enfant|
|PR|Préscolaire|
|PK|Prématernelle|
|TK|Maternelle transitoire|
|KG|Maternelle|
|01 ou 1|Première année|
|02 ou 2|Ce1|
|03 ou 3|Ce2|
|04 ou 4|Cours moyen|
|05 ou 5|Cours moyen2|
|06 ou 6|Sixième|
|07 ou 7|Cinquième|
|08 ou 8|Quatrième|
|09 ou 9|Troisième|
|10|Seconde|
|11|Première|
|12|Terminal|
|PS|Postsecondaire|
|PS1|Première année d'études postsecondaires|
|PS2|Deuxième cycle de l'enseignement supérieur|
|PS3|Junior postsecondaire|
|PS4|Senior postsecondaire|
|premier cycle universitaire|Premier cycle universitaire|
|diplômé|Diplômé|
|troisième cycle|Troisième cycle (diplômé avec une accentuation sur la recherche)|
|alumni|Alumni|
|adultEducation|Éducation des adultes|
|UG|Non classé|
|Autres|Autres|

### <a name="united-kingdom-year-groups"></a>Groupes annuels du Royaume-Uni
|Valeur dans le fichier (colonne Note) | Étiquette dans Insights|
|:---|:---| 
|IT|Pépinière|
|PR|Préscolaire|
|PK|Crèche|
|01 ou 1|Année 1|
|02 ou 2|Année 2|
|03 ou 3|Année 3|
|04 ou 4|Année 4|
|05 ou 5|Année 5|
|06 ou 6|Année 6|
|07 ou 7|Année 7|
|08 ou 8|Année 8|
|09 ou 9|Année 9|
|10|Année 10|
|11|Année 11|
|12|Année 12|
|13|Année 13|
|PS|Postsecondaire|
|PS1|Première année d'études postsecondaires|
|PS2|Deuxième année d'études postsecondaires|
|PS3|Troisième année d'études postsecondaires|
|PS4|Quatrième année d'études postsecondaires|
|premier cycle universitaire|Premier cycle universitaire|
|diplômé|Diplômé|
|troisième cycle|Troisième cycle (diplômé avec une accentuation sur la recherche)|
|alumni|Alumni|
|adultEducation|Éducation des adultes|
|UG|Non classé|
|Autres|Autres|

