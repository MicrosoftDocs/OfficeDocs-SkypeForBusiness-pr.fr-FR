---
title: Acheter, configurer et activer Career Coach pour les Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment acheter, configurer et activer Career Coach pour Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ec7ef2f09728abdb2db8acc3be948a50faaf304
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684571"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>Acheter, configurer et activer Career Coach pour les Microsoft Teams

Career Coach est une application Microsoft Teams Éducation optimisée par LinkedIn qui fournit des conseils personnalisés aux étudiants des niveaux supérieurs pour qu’ils naviguent dans leur carrière. Career Coach offre aux établissements d’enseignement une solution de carrière unifiée qui permet aux étudiants de découvrir leur carrière, de développer des compétences réelles et de développer leur réseau au même endroit.

En savoir plus sur [Career Coach.](https://aka.ms/career-coach)

> [!NOTE]
> Utilisez les meilleures pratiques et les conseils utiles de ce guide pour activer les fonctionnalités de Career Coach pour les étudiants, les enseignants et le personnel. Consultez [l’article du guide de planification](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) rapide.

## <a name="review-the-requirements"></a>Examiner les conditions requises

Pour activer Career Coach pour votre établissement d’enseignement, examinez ce dont vous avez besoin pour rendre l’application opérationnel.

**Configuration technique requise**

  - Office 365 client avec Azure Active Directory

  - Microsoft Teams

  - Connexions de compte LinkedIn dans Azure Active Directory

**Licences**

  - Enseignants 

  - Étudiants

> [!NOTE]
> Une licence pour l’enseignant de Career Coach doit être attribuée à l’administrateur informatique qui complète la configuration.

**Données et fichiers de votre établissement d’enseignement**

  - Données du catalogue de cours

  - Champs d’étude proposés

  - Page LinkedIn de l’établissement d’enseignement

  - Abonnement LinkedIn Learning campus (préféré)

## <a name="purchase-the-career-coach-licenses"></a>Acheter les licences Career Coach

Career Coach est disponible dans le monde entier (sauf en Chine et en Russie) pour les établissements d’enseignement supérieur qualifiés via enrollment for Education Solutions (EES), les fournisseurs de services cloud et le centre d’administration Microsoft 365 (direct web). En tant Microsoft Teams, les clients doivent avoir une Microsoft 365 A3/A5 ou Office 365 A1/A3/A5.

### <a name="assign-app-licenses-to-users"></a>Attribuer des licences d’application aux utilisateurs

Pour obtenir des instructions détaillées, voir [Attribuer des licences aux utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="turn-on-linkedin-account-connections"></a>Activer les connexions de compte LinkedIn

Career Coach **nécessite** que les utilisateurs de votre établissement d’enseignement ont la possibilité de connecter leur compte Microsoft 365 à leur compte LinkedIn, qui est facilité au sein de Career Coach

1. Connectez-vous [au Centre d’administration Azure AD](https://aad.portal.azure.com/) avec un compte administrateur global pour l’organisation Azure AD.

2. Sélectionnez **Utilisateurs.**

3. Dans la page **Utilisateurs,** sélectionnez **Paramètres utilisateur.**

4. Sous **connexions de compte LinkedIn,** autorisez les utilisateurs à connecter leurs comptes pour accéder à leurs connexions LinkedIn au sein de certaines applications Microsoft. Aucune donnée n’est partagée tant que les utilisateurs n’ont pas accepté de connecter leur compte.

   - Sélectionnez **Oui** pour activer le service pour tous les utilisateurs de votre établissement d’enseignement

   - Groupe **sélectionné pour** activer le service uniquement pour un groupe d’utilisateurs sélectionnés dans votre établissement d’enseignement

   - Sélectionnez **Non pour** retirer le consentement de tous les utilisateurs de votre établissement d’enseignement

Découvrez comment intégrer [des connexions de compte LinkedIn dans Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="configure-career-coach-in-the-teams-admin-center"></a>Configurer Career Coach dans le centre d’administration Teams’équipe

En utilisant les paramètres d’administration du Microsoft Teams d’administration, vous pouvez configurer Career Coach pour votre établissement d’enseignement et l’activer pour les utilisateurs.

## <a name="access-the-career-coach-app-settings"></a>Accéder aux paramètres de l’application Career Coach

Utilisez la [page Gérer les applications](/microsoftteams/manage-apps) pour afficher les Teams dans le catalogue d’applications de votre établissement d’enseignement.

1. Connectez-vous au **Teams d’administration.**

2. Dans la barre de navigation gauche, **sélectionnez Teams**  >  **applications Gérer les applications.**  

    > [!NOTE]
    > Vous devez être un administrateur global ou un Teams de service pour accéder à la page.

3. Recherchez Career Coach ou **recherchez-le.**  

4. Sélectionnez **Career Coach,** puis **sélectionnez Paramètres.**  

    ![affiche l’application Career Coach sélectionnée avec l’option de Paramètres l’affichage](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a>Configurer les paramètres de l’application Career Coach

Career Coach se classe dans cinq catégories de configuration :

- [Marque et préférences](#brand-and-preferences)

- [Configuration de LinkedIn](#linkedin-configuration)

- [Catalogue de cours](#course-catalog)

- [Champs d’étude](#fields-of-study)

- [Personnalisation](#customization)

> [!NOTE]
> La marque et les préférences, la configuration de  LinkedIn, le catalogue de cours et les champs d’étude sont requis pour activer efficacement l’application pour les étudiants, les enseignants et le personnel.

#### <a name="brand-and-preferences"></a>Marque et préférences

Définissez le nom, le logo et la langue par défaut de votre établissement d’enseignement sur la page des paramètres de marque et de préférences.

![Section Image de marque Career Coach du Centre d’administration](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a>Icône établissement d’enseignement

L’icône d’un établissement d’enseignement est utilisée dans Career Coach pour identifier le contenu propre à votre établissement d’enseignement, les ressources du catalogue de cours dans l’application et la section des expériences réelles du tableau de bord. Pour ce faire, il est préférable d’avoir la mise en forme la plus à jour :

 - A transparent PNG
 - Proportions de 1:1
 - Taille maximale de 64 px x 64 px.

##### <a name="educational-institution-thumbnail"></a>Miniature établissement d’enseignement

L’icône d’un établissement d’enseignement sera utilisée pour les ressources du catalogue de cours dans l’application lorsqu’une image spécifique n’est pas disponible pour un cours. Pour ce faire, il est préférable d’avoir la mise en forme la plus à jour :

- A PNG
- Proportions de 16:9
- Taille maximale de 360 px x 200 px.

#### <a name="linkedin-configuration"></a>Configuration de LinkedIn

La configuration de LinkedIn connecte Career Coach aux données des anciens élèves de LinkedIn.

> [!NOTE]
> Career Coach ne peut pas être activé sans la connexion à la page LinkedIn vérifiée.

##### <a name="add-and-confirm-the-linkedin-page"></a>Ajouter et confirmer la page LinkedIn

Déterminez la page LinkedIn de l’établissement d’enseignement. Recherchez la page LinkedIn en recherchant sur LinkedIn ou en vous connectant avec un membre du personnel des services de carrière afin de déterminer la page à utiliser.  
  
1. Connectez-vous au **Teams d’administration.**

1. Sélectionnez **Teams applications**  >  **Gérer les applications** Connexion  >    >  **LinkedIn de Career** Coach.

2. Entrez l’URL de la page LinkedIn de votre établissement d’enseignement.  

3. Sélectionnez **Appliquer.**

4. Copiez l’URL de vérification et partagez-la avec la documentation de l’administrateur de la page LinkedIn de votre établissement d’enseignement [LinkedIn.](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en) Le lien de vérification expire après 30 jours.  

   ![Paramètres Linkedin pour l’entraîneur professionnel](media/linkedin.png)  

#### <a name="course-catalog"></a>Catalogue de cours

Le catalogue de cours représente les cours et les cours proposés aux étudiants par votre établissement d’enseignement. Ces cours sont utilisés au sein de l’application dans deux zones :

- Les cours sont renvoyés dans le cadre des ressources d’apprentissage.  

- Les données méta des cours et des cours, telles que les descriptions, permettent aux étudiants d’identifier leurs compétences lorsqu’ils téléchargent une transcription.  

Pour créer le catalogue de cours, créez une liste de tous les cours qui ont été appris dans votre établissement d’enseignement et téléchargez-le dans un fichier CSV. L’application dessine à partir du catalogue de cours pour identifier les compétences d’un étudiant à partir de sa transcription et pour suggérer des cours à prendre. 

> [!NOTE]
> Pour [plus d’informations sur](location-of-data-in-teams.md) [](security-compliance-overview.md) la protection des informations sur les étudiants, voir Emplacement des données Teams sécurité et conformité. 

##### <a name="course-catalog-documents-formatting-and-schema"></a>Mise en forme et schéma des documents du catalogue de cours

Le document doit être au format CSV avec une taille maximale de 18 Mo. Le document doit contenir le titre du **cours,** **l’ID** du cours et **l’URL du cours requis.** L’inclure dans les champs recommandés améliore l’expérience pour les étudiants en renvoyant de meilleurs résultats de recherche et une identification de compétence.

> [!NOTE]
> Commencez avec l’exemple de document [du catalogue de]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) cours pour commencer.

Le tableau suivant répertorie les éléments à inclure dans le catalogue des cours :


| Nom             | Statut      | Type   | Description                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | Obligatoire    | chaîne | Généralement, l’ID du cours (indique généralement ce qui est généré dans la transcription). |
| titre            | Obligatoire    | chaîne | Généralement le titre du cours.                                                      |
| sourceLink       | Obligatoire    | URL    | Lien vers la page du cours.                                               |
| description      | Recommandation | chaîne | Texte d’introduction au cours.                                              |
| langue         | Recommandation | chaîne | Langue du cours. Utilisez des codes de langue standard.                           |
| format           | Recommandation | chaîne | Mode d’enseignement (par exemple, en ligne, vidéo, en personne).                              |
| thumbnailLink    | Recommandation | URL    | Lien miniature vers l’image du cours.                                            |
| thumbnailAltText | Recommandation | chaîne | Texte de alt sur l’accessibilité de l’image                                           |
| educationLevel   | Recommandation | chaîne | Niveau d’étude, par exemple. Cycle/diplômé.                                       |
| rubriques           | Recommandation | chaîne | Rubriques ou balises associées aux compétences apprises dans les cours.          |

##### <a name="add-the-course-catalog"></a>Ajouter le catalogue de cours

1. Connectez-vous au **Teams d’administration.**

1. Sélectionnez **Teams applications Gérer** les &gt; **applications** Career &gt; **Coach** &gt; **Paramètres** catalogue &gt; **de cours.**  

2. Télécharger cours au format CSV.

4. Sélectionnez **Appliquer.**

   ![Section Catalogue de cours de l’application Carrières](media/course-catalog.png)

#### <a name="fields-of-study"></a>Champs d’étude

Les champs d’étude sont synonymes de domaines d’intérêt majeurs, de réussites universitaires et de degrés. Ces titres sont référencés par les étudiants lorsqu’ils commencent à utiliser l’application et commencent à définir leur profil personnalisé.

Ajoutez tous les champs d’étude disponibles aux étudiants tels que Ingénierie, Anglais, Entreprise, etc. La liste de champs permet aux étudiants de découvrir des champs d’étude qui peuvent les intéresser et d’ajouter leur zone de focus à leur profil.

> [!NOTE]
> Commencez par le [champ d’exemple du](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) document d’étude.
##### <a name="add-the-fields-of-study"></a>Ajouter les champs de l’étude

1. Connectez-vous au **Teams d’administration.**
1. Sélectionnez **Teams applications** &gt; **Gérer les applications** Career &gt; **Coach** &gt; **Paramètres** &gt; **des champs d’étude.**  

2. Télécharger d’étude au format CSV.

3. Sélectionnez **Appliquer.**

#### <a name="customization"></a>Personnalisation

Career Coach peut être personnalisé pour être unique dans votre établissement d’enseignement. La personnalisation prend en charge l’ajout d’expériences au tableau de bord. Il est recommandé d’ajouter des liens vers des offres d’emploi, des événements, des services de carrière, des événements professionnels, des clubs d’étudiants et toute autre ressource qui aident les étudiants à acquérir une expérience réelle.

##### <a name="add-customized-experiences"></a>Ajouter des expériences personnalisées

1. Connectez-vous au **Teams d’administration.**

1. Sélectionnez **Teams applications Gérer** les &gt; **applications** Career &gt; **Coach**  >  **Paramètres** &gt; **personnalisation.**

2. Ajoutez chaque URL, un titre et une courte description.  
  
3. Sélectionnez **Appliquer.**

## <a name="making-career-coach-available-to-your-organization"></a>Rendre Career Coach disponible pour votre organisation

Maintenant que Career Coach est configuré pour votre organisation. Suivez ces étapes pour vous assurer que Career Coach soit disponible pour l’organisation dans Microsoft Teams.

### <a name="enable-the-app"></a>Activer l’application

Une fois la configuration terminée, activez l’application pour les étudiants et les utilisateurs titulaires d’une licence afin qu’ils ont accès à Career Coach.  
  
> [!NOTE]
> Vous devez avoir des autorisations de rôle d Teams global ou d’administrateur.

1. Connectez-vous au **Teams d’administration.**

1. Sélectionnez **Teams applications** &gt; **Gérer les applications** Career &gt; **Coach.**

2. Déplacez le basculement Statut sur **Autorisé.**  

  > [!NOTE]
  > Autorisé signifie que l’application est disponible pour les utilisateurs de votre établissement d’enseignement. Bloqué signifie que l’application n’est pas disponible pour les étudiants.

### <a name="add-career-coach-as-an-installed-app"></a>Ajouter Career Coach en tant qu’application installée

> [!NOTE]
> Cette étape garantit que 1) Career Coach est correctement configuré pour votre organisation 2) que les étudiants trouvent Career Coach.

1. Connectez-vous au **Teams d’administration.**

2. Sélectionnez **Teams** &gt; **stratégies de configuration des applications** Votre &gt; *stratégie.* 

3. Sous Applications installées, sélectionnez Ajouter des applications.

4. Dans le volet Ajouter des applications installées, recherchez les applications que vous voulez installer automatiquement pour les utilisateurs lorsqu’ils démarrent une Teams. Vous pouvez également filtrer les applications par stratégie d’autorisation d’application. Lorsque vous avez choisi votre liste d’applications, sélectionnez Ajouter.

### <a name="pin-the-app"></a>Épingler l’application

L’épinglage de Career Coach rend l’application plus accessible et visible pour les étudiants.

1. Connectez-vous au **Teams d’administration.**

2. Sélectionnez **Teams** &gt; **stratégies de configuration des applications** Votre &gt; *stratégie.* 

3. Sous **Applications épinglées,** **sélectionnez Ajouter des applications.**

4. Recherchez **Career Coach,** puis sélectionnez **Ajouter.**

5. Choisissez l’ordre d’apparition de l’application, puis sélectionnez **Enregistrer.**

> [!NOTE]
> Les étudiants seront avertis dans un Microsoft Teams que Career Coach a été épinglé.

Pour plus [d’informations,](/microsoftteams/teams-app-setup-policies) référez-vous à Gérer les stratégies de configuration d’application dans Microsoft.

## <a name="resources"></a>Ressources

Les ressources suivantes vous aideront à planifier votre application Career Coach.

- [Bienvenue dans Microsoft Teams](Teams-overview.md)

- [Comment déployer Teams](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Présentation des équipes et des canaux dans Microsoft Teams](teams-channels-overview.md)

- [Gestion des applications dans Microsoft Teams Centre d’administration](manage-apps.md)

- [Sécurité, confidentialité et conformité dans Microsoft Teams](security-compliance-overview.md)

- [Kit d’orientation virtuelle en ligne](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [Limites et spécification des canaux Teams clients](limits-specifications-teams.md)

- [Emplacement des données dans Microsoft Teams](location-of-data-in-teams.md)

- [Formation pour les administrateurs sur Microsoft Teams](ITAdmin-readiness.md)

- [Résolution des problèmes de Teams](/microsoftteams/troubleshoot/teams-welcome)

- [Gérer les stratégies d’autorisation d’application dans Microsoft Teams](teams-app-permission-policies.md)
