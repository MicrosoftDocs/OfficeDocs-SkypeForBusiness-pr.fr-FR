---
title: Synchroniser les données du système d’information sur les élèves (SIE) avec Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Synchronisez les données du système d’information sur les élèves (SIE) avec Education Insights dans Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997733"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Synchroniser les données du système d’information sur les élèves (SIE) avec Education Insights
Plus [Education Insights](class-insights.md) reçoit de données, plus les enseignants peuvent aider leurs élèves, et plus les responsables de l’éducation peuvent aider les enseignants.

Pour fournir des informations au niveau de l’organisation, nous devons utiliser la [Synchronisation des données scolaires (SDS)](/SchoolDataSync) pour nous connecter au système d'informations sur les élèves (SIE). Ainsi, Insights présentera la structure hiérarchique du système d’enseignement correctement mappée. 

L’affichage des informations au niveau de la classe en tant qu’enseignant *ne nécessite pas* cette synchronisation, car nous utilisons la structure et les autorisations de classe de Teams.

## <a name="plan-your-school-data-sync-integration"></a>Planifier l’intégration de votre Synchronisation des données scolaire
Synchronisation des données scolaires Microsoft (également connu sous le nom de SDS) fournit les données du système d'informations sur les élèves (également connu sous le nom de SIS) et sa structure hiérarchique du système d’enseignement et mappe l’utilisateur auquel il est attribué, ainsi que des données supplémentaires sur la hiérarchie des étudiants et de l’organisation.

Insights fonctionne parfaitement avec le [format de fichier SDS V2](/schooldatasync/sds-v2-csv-file-format) et versions ultérieures, mais prend également en charge le [format de fichier SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds) *avec des fonctionnalités limitées*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Différences entre les formats de fichier SDS V1 et V2

Pour tirer le meilleur parti des Insights, il est recommandé d’utiliser le format de fichier v2 ou v2.1 (Bientôt disponible)

| Type de données | V1 | V2 (recommandé) |
|:--- |:--- |:--- |
| **Utilisateurs** | Le format V1 inclut **uniquement les enseignants**. Par conséquent, pour définir des autorisations au niveau de l’organisation pour vos responsables de l’éducation, vous devez définir manuellement les autorisations de chacun d’entre eux. | Le format V2 inclut **tous les rôles**, si bien que vous pouvez attribuer des autorisations basées sur les rôles. |
| **Organisations** | Le format V1 inclut uniquement **les établissements d’enseignement**, si bien qu’un seul niveau d’agrégation apparaît (tous vos établissements d’). Vous pouvez zoomer sur un établissement à l’aide d’une liste plate. Cependant, cette liste peut comporter un grand nombre ou différents types d’établissements d’enseignement difficiles à comparer (par exemple, l’école primaire et l’école secondaire ou les écoles de sciences et les écoles de lettres).<br/><br/> Lorsqu’une hiérarchie est en place, vous pouvez créer des niveaux qui ont du sens, tels qu’un département des sciences ou des lettres.| Le format V2 contient **la hiérarchie complète de votre secteur ou de votre établissement**, notamment les universités, les établissements d’enseignement supérieur, les facultés, les campus, les régions, les programmes, etc.<br/><br/> Les hiérarchies vous permettent d’afficher le regroupement pertinent selon chaque niveau de la hiérarchie, de comparer rapidement les unités d’organisation à chaque niveau, d’attribuer des autorisations à des niveaux spécifiques, de définir des objectifs par niveau d’organisation, etc.|

> [!NOTE]
> Les clients ne pourront pas intégrer le format de fichier v2 à partir du 15 juillet 2021 et devront utiliser le format v2.1 à la place. Toutes les futures mises à niveau et nouvelles fonctionnalités seront effectuées au format v2.1 et seront entièrement à compatibilité descendante avec le format de fichier v1.

## <a name="best-practices"></a>Meilleures pratiques
Le mappage précis de la hiérarchie et de la place de chacun dans cette hiérarchie permet à Insights de fournir des données exactes, ainsi que des informations plus précises et plus adaptées aux différents types de responsables de l’éducation.

Plus vous fournirez de détails, plus les rapports et les actualités seront adapté et pertinents.

Voici quelques pratiques recommandées visant à garantir le déploiement fluide de SDS pour permettre à vos utilisateurs d’utiliser au mieux Insights.

### <a name="file-format-version-to-ue"></a>Version du format de fichier vers UE
*   Utiliser le format de fichier V2.1 (bientôt disponible) et synchroniser les données facultatives utilisées par Education Insights

### <a name="users-and-roles"></a>Utilisateurs et rôles
*   Vérifiez que **tous les utilisateurs** apparaissent dans les fichiers que vous fournissez et que vous avez synchronisés. Cela inclut tous les élèves et membres du personnel qui ont besoin de consulter les données relatives aux unités d’organisation concernées.
    Si votre SIE n’inclut que des enseignants actuellement, ajoutez manuellement les autres utilisateurs avant de charger les fichiers dans le SDS, puis de synchroniser les données.
    Les statistiques collectées par Insights proviennent uniquement des étudiants inscrits, si certains étudiants sont manquants, ce qui rend les données et les conclusions erronées.
    
*   Veillez à **fournir le prénom et le nom de famille de chaque utilisateur**. Dans le cas contraire, les utilisateurs seront référencés par leur adresse e-mail, ce qui offre une expérience non optimale dans les rapports et les mises à la une (cartes avec Insights sur l’activité ou les performances des étudiants).

*   Le niveau de note/année doit être basé sur cette [liste de mappages ](#supported-grade-level-values). 

*   Il est important d'**ajouter l'année/le niveau scolaire à tous les étudiants** afin que les données d'activité puissent être agrégées et filtrées en fonction de celui-ci.    

*   Veillez à affecter **chaque utilisateur à l’unité d’organisation correspondante**. De cette façon, Education Insights n’affichera pas de données erronées dans les feux de l’attention de Education Insights.

    *   Vous pouvez associer un étudiant à plusieurs unités d’organisation, par exemple, les étudiants inscrits dans un programme spécial ou dans deux facultés. Si l’étudiant a plusieurs unités d’organisation, fournissez une ligne pour chacun d’eux dans le fichier utilisateur de cet étudiant.
    
    *   L’administrateur informatique peut accorder des autorisations en fonction de l’unité d’organisation pour le personnel. **Assurez-vous que les membres du personnel sont associés au niveau d’unité approprié**, afin qu’ils reçoivent les autorisations dont ils ont besoin. Par exemple, un conseillé affecté à quatre établissements doit avoir accès à toutes les notes de ces établissements d’enseignement ; un chef d’établissement doit avoir accès à toutes les classes de son établissement. 
    
*   **Le rôle est essentiel**. Bien que cette liste soit fermée, essayez de faire correspondre le rôle de [la liste](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) au rôle réel de chaque utilisateur que vous chargez. Cela vous permet d’attribuer des autorisations basées sur les rôles en conséquence. Par exemple, accordez des autorisations pour que tous les chefs d’établissement voient les classes de leur établissement ou à tous les professeurs pour qu’ils voient leurs enseignants. 

### <a name="organizations"></a>Organisations

* Veillez à **refléter la hiérarchie réelle et complète de votre organisation**. Pour ce faire, vous pouvez ajouter le fichier manuellement. Dans certains cas, cette hiérarchie n’apparaît pas dans le SIE. Toutefois, il peut être nécessaire, de consulter l’agrégation correspondante par chaque niveau de la hiérarchie, d’attribuer des autorisations à des niveaux spécifiques, de définir des objectifs par niveau d’organisation, etc. 

* Vérifiez que **toutes les unités d’organisation de l’arborescence des organisations incluent les élèves ou les classes** pour agréger les données des élèves à leur place. Nous vous recommandons de placer les élèves sur la branche la plus basse de l’arborescence.

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

