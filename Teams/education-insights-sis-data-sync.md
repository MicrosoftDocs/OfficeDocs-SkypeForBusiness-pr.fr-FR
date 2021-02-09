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
ms.openlocfilehash: 70cef1893b0260e690f5470bff0111dda5e7e7fe
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145821"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Synchroniser les données du système d’information sur les élèves (SIE) avec Education Insights
Plus [Education Insights](class-insights.md) reçoit de données, plus les enseignants peuvent aider leurs élèves, et plus les responsables de l’éducation peuvent aider les enseignants.

Pour fournir des informations au niveau de l’organisation, nous devons utiliser la [Synchronisation des données scolaires (SDS)](https://docs.microsoft.com/SchoolDataSync) pour nous connecter au système d'informations sur les élèves (SIE). Ainsi, Insights présentera la structure hiérarchique du système d’enseignement correctement mappée. 

L’affichage des informations au niveau de la classe en tant qu’enseignant *ne nécessite pas* cela, car nous utilisons la structure et les autorisations de classe de Teams.

## <a name="plan-your-sis-integration"></a>Planifier l’intégration de votre SIE
Les données du SIE fournissent la structure hiérarchique du système d’enseignement et établissent une correspondance entre chaque utilisateur et son lieu d’affectation.

Insights fonctionne parfaitement avec le [format de fichier SDS V2](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format), mais prend également en charge le [format de fichier SDS V1](https://docs.microsoft.com/schooldatasync/school-data-sync-format-csv-files-for-sds) avec des fonctionnalités *limitées*.

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Différences entre les formats de fichier SDS V1 et V2

| Type de données |   V1 | V2 (recommandé pour les nouveaux clients) |
|:--- |:--- |:--- |
| **Utilisateurs** | Le format V1 inclut **uniquement les enseignants**. Par conséquent, pour définir des autorisations au niveau de l’organisation pour vos responsables de l’éducation, vous devez les rechercher, puis définir manuellement les autorisations de chacun d’entre eux. | Le format V2 inclut **tous les rôles**, si bien que vous pouvez attribuer des autorisations basées sur les rôles. |
| **Organisations** | Le format V1 inclut uniquement **les établissements d’enseignement**, si bien qu’un seul niveau d’agrégation apparaît (tous vos établissements d’). Vous pouvez zoomer sur un établissement à l’aide d’une liste plate. Cependant, cette liste peut comporter un grand nombre ou différents types d’établissements d’enseignement difficiles à comparer (par exemple, l’école primaire et l’école secondaire ou les écoles de sciences et les écoles de lettres).<br/><br/> Lorsqu’une hiérarchie est en place, vous pouvez créer des niveaux qui ont du sens, tels qu’un département des sciences ou des lettres.| Le format V2 contient **la hiérarchie complète de votre secteur ou de votre établissement**, notamment les universités, les établissements d’enseignement supérieur, les facultés, les campus, les régions, les programmes, etc.<br/><br/> Les hiérarchies vous permettent d’afficher le regroupement pertinent selon chaque niveau de la hiérarchie, de comparer rapidement les unités d’organisation à chaque niveau, d’attribuer des autorisations à des niveaux spécifiques, de définir des objectifs par niveau d’organisation, etc.|

### <a name="type-of-data-required"></a>Type de données obligatoire
Le tableau suivant indique le type de données obligatoire pour tirer le meilleur parti d’Insights.

| Type de données | Exemples des éléments à fournir|Pourquoi est-ce important ?|
|:--- |:--- |:--- |
| **Utilisateurs** |   Rôle (par exemple, élève)<br/> Classe/année (par exemple, 10)<br/> Organisation (nom) | Lorsque nous affectons correctement à chaque personne son rôle, sa classe/son année et son organisation, nous pouvons vérifier que les résumés et les regroupements sont corrects.|
| **Organisations** | Type d’organisation (par exemple, université) |   La hiérarchie est importante ici. Par exemple, les établissements d’enseignement peuvent appartenir à un secteur, lequel peut appartenir à un État.<br/> Lorsqu’un responsable de l’enseignement d’un secteur géographique est autorisé à consulter les données, cela ne concerne que les établissements d’enseignement de ce secteur.|
| **Classes** | Titre (Informatique 101, par exemple) | Cette information indique en détails les cours dispensés dans l’organisation. Cette situation doit être correctement mappée pour que nous puissions affecter l’élève à la classe appropriée. |
| **Inscription** | Rôle (par exemple, élève) | Cela concerne les élèves et les enseignants, et nous permet de savoir dans quelle classe ils sont inscrits. |

> [!NOTE]
> Pendant le processus de déploiement, vous pouvez décider d’utiliser SDS pour configurer les comptes des utilisateurs et des classes dans Teams ou pour fournir des données à Insights uniquement.

## <a name="best-practices"></a>Meilleures pratiques
Le mappage précis de la hiérarchie et de la place de chacun dans cette hiérarchie permet à Insights de fournir des données exactes, ainsi que des informations plus précises et plus adaptées aux différents types de responsables de l’éducation.

Plus vous fournirez de détails ici, plus les rapports et les actualités seront adapté et pertinents.
Voici quelques pratiques recommandées visant à garantir le déploiement fluide de SDS pour permettre à vos utilisateurs d’utiliser au mieux Insights.

### <a name="users"></a>Utilisateurs
*   Vérifiez que *tous les utilisateurs* apparaissent dans les fichiers que vous fournissez et que vous avez synchronisés. Cela inclut tous les élèves et membres du personnel qui ont besoin de consulter les données relatives aux unités d’organisation concernées.

    Si votre SIE n’inclut que des enseignants actuellement, ajoutez manuellement les autres utilisateurs avant de charger les fichiers dans le SIE, puis de synchroniser les données.

    Si certains élèves sont absents, les statistiques recueillies par Insights ne proviennent que des étudiants inscrits, ce qui rend les données et les conclusions trompeuses.
    
*   Veillez à *fournir le prénom et le nom de famille de chaque utilisateur*. Si ces données sont manquantes, les utilisateurs seront référencés par leur adresse e-mail. Cela donne une expérience négative dans les rapports et les actualités (cartes avec des informations sur l’activité ou les performances des élèves).

*   Vous devez indique la *classe/l’année en 2 chiffres* (par exemple, 07 pour l’année 7). Consultez la [liste de mappage](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported). 

*   Il est important *d'ajouter l’année/la classe à tous les élèves* pour filtrer les données.    

*   Veillez à affecter *chaque utilisateur à l’unité d’organisation correspondante*. De cette façon, nous n’afficherons pas de données trompeuses dans nos actualités sur la base des données agrégées de chaque unité.

    *   Vous pouvez associer un élève à plusieurs unités d’organisation, par exemple, les élèves inscrits dans un programme spécial ou dans deux facultés. Dans ce cas, mettez deux lignes à disposition dans le fichier Utilisateurs de cet élève : une pour chaque organisation.
    
    *   En fonction de l’unité d’organisation du personnel, vous pourrez définir les autorisations pertinentes. Veillez à les associer au niveau d’unité approprié pour que les membres du personnel obtiennent les autorisations dont ils ont besoin. Par exemple, un conseillé affecté à quatre établissements doit avoir accès à toutes les classes de ces établissements d’enseignement ; un chef d’établissement doit avoir accès à toutes les classes de son établissement. 
    
*   Le rôle est essentiel. Bien qu’il s’agisse d’une liste fermée, essayez de faire correspondre le rôle de [la liste](https://docs.microsoft.com/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) au rôle réel de chaque utilisateur que vous chargez. Vous pouvez ainsi attribuer des autorisations basées sur les rôles. Par exemple, accordez des autorisations pour que tous les chefs d’établissement voient les classes de leur établissement ou à tous les professeurs pour qu’ils voient leurs enseignants. 

### <a name="organizations"></a>Organisations

* Veillez à *refléter la hiérarchie réelle de votre organisation*. Pour ce faire, vous pouvez ajouter le fichier manuellement. Dans certains cas, cette hiérarchie n’apparaît pas dans le SIE. Toutefois, il peut être nécessaire, ici, de consulter l’agrégation correspondante par chaque niveau de la hiérarchie, d’attribuer des autorisations à des niveaux spécifiques, de définir des objectifs par niveau d’organisation, etc. 

* Vérifiez que *toutes les unités d’organisation de l’arborescence des organisations incluent les élèves ou les classes* pour agréger les données des élèves à leur place. Nous vous recommandons de placer les élèves sur la branche la plus basse de l’arborescence.

> [!NOTE]
> Si vous souhaitez en savoir plus sur le déploiement de la SDS, veuillez consulter la rubrique [Planification de SDS](https://docs.microsoft.com/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-using-sds"></a>Intégrer un SIE à l’aide de SDS

Nous fournissons la Synchronisation des données scolaires (SDS) avec Office 365 pour l’éducation. La SDS lit les données du système d’information sur les élèves (SIE) d’un établissement d’enseignement, puis les intègre à Teams pour permettre la création automatique de salles de classe et d’utilisateurs en ligne.

Elle synchronise également les données du SIE avec Insights.

### <a name="sync-with-insights"></a>Synchronisation avec Insights

Vous devez d’abord activer le bouton à bascule Insights pour démarrer le processus de synchronisation.

* Sur le [**portail SDS**](https://sds.microsoft.com), accédez à **Paramètres**, faites défiler l’écran vers le bas jusqu’à **Collect data for Insights (Collecter des données pour Insights)**, puis vérifiez que vous avez activé cette fonction (elle est *activée* par défaut).

* Faites défiler l’écran vers le bas jusqu’au commutateur suivant, **Synchroniser les données organisationnelles à partir de SDS (préversion)**, puis activez-le.

Si l’option *Synchroniser les données organisationnelles à partir de SDS (préversion)* n’apparaît pas dans la page Paramètres, accédez à la [page d’inscription](https://aka.ms/insights/join) pour fournir vos informations. Un membre d’équipe vous contactera.

:::image type="content" source="media/insights-sds-settings.png" alt-text="Synchronisation avec Insights (boutons à bascule)":::

### <a name="deploy-sds"></a>Déployer la SDS
**Si vous utilisez déjà la SDS**, nous vous recommandons de suivre nos [meilleures pratiques](#best-practices). 

Pour synchroniser vos profils actuels avec Insights, allez dans vos **Profil de synchronisation**, cliquez sur **Modifier**, puis sélectionnez **Synchroniser aux Insights**. Pour la synchronisation initiale, nous vous recommandons d’attendre pendant 24 heures la mise à disposition des rapports soient disponibles une fois les données actualisées depuis votre SIE.  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="Profil de synchronisation avec Insights (boutons à bascule)":::

**Si vous n’utilisez pas encore la SDS**, vous devez à présent [la déployer](https://docs.microsoft.com/schooldatasync/deploying-school-data-sync).

Pendant le processus de déploiement, vous pouvez décider d’utiliser SDS pour configurer les comptes des utilisateurs et des classes dans Teams ou pour fournir des données à Insights uniquement.

> [!NOTE]
> Si nous sommes au milieu de l’année et si vous avez déjà créé des équipes manuellement, utilisez la SDS uniquement pour fournir les données à Insights. L’année suivante, nous vous recommandons d’utiliser SDS également pour la configuration des comptes des utilisateurs et des classes dans Teams.

### <a name="verify-the-sync-process"></a>Vérifier le processus de synchronisation
Une nouvelle zone d’état s’affiche en côté des données de l’organisation de synchronisation à partir de SDS (préversion) sur la page Paramètres.
 
*   Si l’état est **En cours**, patientez jusqu’à 24 heures après le déploiement du profil SDS.

*   Si l’état est **Terminé**, félicitations. Vous pouvez afficher Insights au niveau de l’organisation, puis passer à l’étape suivante.

*   Si l’état est **Terminé avec les erreurs**, **Terminé avec les avertissements** ou **Abandonné**, téléchargez le fichier journal contenant les erreurs et avertissements de la dernière synchronisation, puis vérifiez si vous pouvez les corriger. 

> [!IMPORTANT]
> Si vous rencontrez des problèmes, [le support](https://aka.ms/edusupport) est là pour vous aider.
