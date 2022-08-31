---
title: Prise en main de Microsoft Teams pour l'apprentissage à distance
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Conseils pour le démarrage de l'apprentissage à distance pour Microsoft Teams pour l’Éducation.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466022"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Prise en main de Microsoft Teams pour l'apprentissage à distance

Cet article décrit les étapes d’administration informatique pour configurer votre établissement d’enseignement pour l’apprentissage à distance à l’aide de Microsoft Teams.

Dans Teams, **les enseignants** peuvent :

- Discutez rapidement avec les étudiants.
- Partagez des fichiers et des sites web.
- Créez des blocs-notes OneNote pour la classe.
  - Organisez des leçons interactives.
  - Fournissez des commentaires efficaces et opportuns.
- Distribuer et classer les devoirs.
- Partager du matériel d’enseignement dans les communautés d’apprentissage professionnel.

**Les administrateurs et le personnel de l’éducation** peuvent :

- Restez à jour sur les événements.
- Collaborez à l’aide de Staff Teams pour des annonces et des conversations thématiques.

# <a name="accounts--licenses"></a>[Comptes & licences](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>Comptes d'utilisateur, licences et sécurité des identités

Teams utilise Microsoft 365 pour authentifier les utilisateurs et fournir des services. Toutes les identités Microsoft 365 doivent être établies pour faciliter la collaboration.

Si les identités d’utilisateur n’existent pas déjà, suivez ce processus pour les établir :

1. [Créez des utilisateurs à l’aide de School Data Sync](/microsoft-365/education/deploy/school-data-sync).
2. [Attribuez des licences aux utilisateurs](teams-edu-licensing.md).
3. [Créez des groupes Microsoft 365](Office-365-groups.md).
4. [Configurez Exchange](Exchange-Teams-interact.md).
5. [Configurez SharePoint et OneDrive](SharePoint-OneDrive-interact.md).
6. [Configurez les utilisateurs qui ont des e-mails Google](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

Microsoft Teams est inclus dans tous les plans Microsoft 365, y compris le plan d’éducation gratuit A1.

Pour obtenir des conseils sur le déploiement de Microsoft 365 et la configuration de Teams, consultez [Créer votre locataire Microsoft 365](/microsoft-365/education/deploy/create-your-office-365-tenant).

# <a name="set-up-teams"></a>[Configurer Teams](#tab/setup)

## <a name="easily-set-up-teams"></a>Configurer facilement Teams

Voici les deux choses que vous devez faire pour être opérationnel avec Teams :

### <a name="1-allow-users-to-create-teams"></a>1. Autoriser les utilisateurs à créer des équipes

**Par défaut, tout le monde peut créer des groupes Microsoft 365 et Teams**, mais cette capacité peut ne pas toujours être appropriée.

Par exemple, certaines écoles peuvent vouloir empêcher les étudiants de créer Teams sans surveillance. La création de groupes et d’équipes Microsoft 365 peut être [limitée à certains groupes de sécurité](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Pour les établissements d’enseignement supérieur, nous vous recommandons d’autoriser tout le monde, y compris les étudiants, à créer des équipes pour les classes, la recherche, les projets de groupe et les groupes d’étude.

Pour une procédure pas à pas sur la création de Teams, consultez [Créer une équipe de classe dans Microsoft Teams](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).

### <a name="2-configure-user-experiences-using-policies"></a>2. Configurer des expériences utilisateur à l’aide de stratégies

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> Découvrez [La sécurité des étudiants dans Teams pour l’apprentissage à distance](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8).
>
> Si vous souhaitez consulter nos recommandations en matière de stratégie EDU, consultez les [stratégies et packages de stratégie Teams pour l’éducation](policy-packages-edu.md).

Les stratégies Teams contrôlent les fonctionnalités disponibles pour des utilisateurs ou des groupes spécifiques. Les stratégies peuvent définir qui doit être autorisé à utiliser la conversation privée, les appels privés, la planification des réunions, les types de contenu qui peuvent être partagés, etc.

**Le personnel de l’enseignement supérieur, les enseignants et les étudiants** peuvent utiliser les stratégies par défaut (globales). Vous pouvez ajuster les stratégies pour ajouter plus de fonctionnalités à Teams, notamment [les fonctionnalités de traduction et la](messaging-policies-in-teams.md#messaging-policy-settings) [transcription automatique des réunions](meetings-policies-recording-and-transcription.md#transcription).

**Les élèves du primaire et du secondaire** peuvent avoir besoin de capacités restreintes. Il est recommandé d’apporter des modifications à la stratégie « Global (par défaut à l’échelle de l’organisation) ».

**Le personnel et les enseignants de l’école primaire et secondaire** doivent se voir attribuer des stratégies qui accordent des fonctionnalités clés, telles que l’autorisation d’une conversation privée et de la planification des réunions. [Assignez ces stratégies en bloc à vos employés et enseignants](batch-group-policy-assignment-edu.md).

> [!IMPORTANT]
> Pour les stratégies de réunion affectées à tous les utilisateurs, nous vous recommandons de définir le paramètre **Admettre automatiquement les personnes** **sur Tout le monde dans votre organisation**. Cela garantit que les utilisateurs non authentifiés doivent être admis à partir de la salle d’attente avant de pouvoir participer aux réunions Teams.
>
> Pour plus d’informations, consultez [Gérer les stratégies de réunion dans Teams](meeting-policies-participants-and-guests.md#automatically-admit-people).

# <a name="class-teams"></a>[Équipes de classe :](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>Créez des équipes de cours pour une utilisation sûre de la classe

Microsoft Teams pour l’éducation offre des [types d’équipe spécifiques](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) pour l’utilisation scolaire. Le [type d’équipe de la classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) est conçue pour l’utilisation de la classe et inclut des fonctionnalités spécifiques qui prennent en charge les besoins de classe, notamment :

- Affectations.
- Notes.
- Bloc-notes OneNote pour salle de classe.
- [Dossier Class Materials](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  pour la sécurisation du contenu en lecture seule pour les étudiants.
- [Informations](./class-insights.md) pour fournir des données en temps réel sur l’engagement, les devoirs et le bien-être de l’étudiant pour chaque classe.
- [Accès précoce aux enseignants](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) pour configurer la classe avant l’ajout des étudiants.
- Possibilité de désactiver le son des étudiants perturbateurs et d’autres autorisations spéciales.

Les équipes de classes peuvent être créées via :

- [School Data Sync (SDS).](#automatic-team-creation-using-sds)
- [Création dirigée par un enseignant à l’aide de groupes de classes Microsoft 365](#educator-led-team-creation-from-microsoft-365-class-groups).
- [Scripts PowerShell à l’aide d’API Graph](#powershell-script-using-graph-apis).
- [Création manuelle d’une équipe](#manual-team-creation).

Plusieurs options s’offrent à vous pour vous aider à choisir le chemin de déploiement approprié qui correspond le mieux à vos besoins.

### <a name="automatic-team-creation-using-sds"></a>Création automatique d’équipe à l’aide de SDS

[School Data Sync (SDS)](/SchoolDataSync) lit les données du système d’enregistrement d’un établissement, comme un système d’information des étudiants (SIS) ou un système de gestion de l’apprentissage (LMS).

SDS peut importer des données à partir de n’importe quel système d’enregistrement et dispose de connecteurs intégrés à de nombreux [fournisseurs SIS](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support).  

#### <a name="benefits-of-sds"></a>Avantages de SDS

- Crée automatiquement des utilisateurs et applique des licences.
- Crée et gère automatiquement des équipes de classes.
- Synchronise avec SIS/LMS pour gérer les modifications d’appartenance des étudiants.
- [Permet aux enseignants de préparer des cours avant d’ajouter des étudiants](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).
- Peut créer automatiquement des groupes de sécurité.
- Crée des unités administratives pour la délégation administrative délimitée.
- [Autorise la réinitialisation du mot de passe de l’enseignant](/schooldatasync/how-to-enable-teacher-password-reset).
- Dispose de fonctionnalités de nettoyage intégrées pour renommer et archiver des groupes et des équipes.
- [Synchronise les notes de Teams à SIS](/schooldatasync/grade-sync).
- [Protège les données personnelles des étudiants](/schooldatasync/protecting-student-personal-data).
- Effectue le suivi et gère le consentement du tuteur.
- Fournit de meilleures données Éducation Insights.

#### <a name="considerations-for-sds"></a>Considérations relatives à SDS

SDS crée des équipes en deux étapes :

1. SDS crée un groupe Microsoft 365 dans Azure Active Directory (Azure AD).
2. SDS transforme automatiquement ce groupe en équipe.

La deuxième étape de la création d’équipes est facultative dans SDS. Un administrateur peut ne pas vouloir créer automatiquement des équipes en fonction du temps de déploiement et du nombre d’équipes inutilisées pouvant en résulter. Au lieu de cela, consultez la [méthode de création d’équipe dirigée par l’enseignant](#educator-led-team-creation-from-microsoft-365-class-groups).  

#### <a name="get-started-with-sds"></a>Bien démarrer avec SDS

Pour commencer, accédez à [School Data Sync (SDS)](/SchoolDataSync) et contactez [https://aka.ms/sdssupport](https://aka.ms/sdssupport) l’assistance gratuite pour le déploiement.  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Création d’une équipe dirigée par un enseignant à partir de groupes de classes Microsoft 365

La création d’une équipe dirigée par un enseignant permet aux enseignants de créer facilement les classes dont ils ont besoin.  

Cette approche vous permet d’utiliser SDS pour créer des groupes pour chaque classe (recommandé) ou d’utiliser [API Graph](/graph/api/educationroot-post-classes) pour les créer vous-même.

Une fois les groupes de classes préparés, les enseignants peuvent convertir leurs groupes en équipes :

1. Sélectionnez l’onglet Teams dans Teams.
2. En haut du client, sélectionnez l’icône **Classes suggérées** .

#### <a name="benefits-of-educator-led-team-creation"></a>Avantages de la création d’équipes dirigées par des enseignants

- Les classes sont préparées et suggérées, mais pas créées, sauf si l’enseignant a l’intention de les utiliser.
- Pour les établissements comptant plus de 500 000 équipes, cette méthode réduit le nombre d’équipes inutiles.
- [Avantages de SDS](#benefits-of-sds).
- API Graph avantages.
  - Permet aux enseignants de contrôler les classes créées.
  - Ne nécessite aucune intégration avec SDS.

#### <a name="considerations-for-educator-led-team-creation"></a>Considérations relatives à la création d’équipe dirigée par un enseignant

- Pas complètement automatisé et nécessite une action de l’étudiant.
- Les enseignants qui n’ont pas l’autorisation de créer des équipes peuvent toujours [créer des équipes à partir de groupes existants](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- API Graph nécessite un haut niveau d’expertise technique, le temps de créer et d’exécuter le script, et le temps de résoudre les problèmes éventuels.

#### <a name="get-started-with-educator-led-team-creation"></a>Prise en main de la création d’équipe dirigée par un enseignant

Pour commencer à utiliser la méthode SDS, accédez à [School Data Sync (SDS)](/SchoolDataSync) et contactez [https://aka.ms/sdssupport](https://aka.ms/sdssupport) l’assistance gratuite pour le déploiement.

- Vous devez désactiver le bouton bascule de création automatique d’équipe dans votre profil SDS.
- Vous pouvez utiliser une combinaison de création d’équipe automatique et dirigée par des enseignants pour les équipes de classe à l’aide de deux profils SDS.

Pour utiliser la méthode de l’API Graph, voir [API Graph](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true) et [Créer une équipe de classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true).  

### <a name="powershell-script-using-graph-apis"></a>Script PowerShell à l’aide des API Graph

Avec PowerShell, vous pouvez écrire un script pour créer des équipes et des canaux, et configurer automatiquement les paramètres.

Cette méthode exige que l’administrateur [crée d’abord le groupe, ajoute des enseignants et des étudiants, puis crée l’équipe](/graph/teams-create-group-and-team).

Vous pouvez également utiliser microsoft [API Graph pour créer, configurer, cloner et archiver des équipes](/graph/api/resources/teams-api-overview).

#### <a name="benefits-of-powershell-scripts"></a>Avantages des scripts PowerShell

- Permet aux administrateurs informatiques de contrôler la création de classes.
- Option permettant de créer des équipes d’accès rapide aux enseignants ou un accès immédiat des étudiants aux équipes.
- [Synchronise les modifications d’appartenance des étudiants au groupe Azure AD](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

#### <a name="considerations-for-powershell-scripts"></a>Considérations relatives aux scripts PowerShell

- Nécessite un haut niveau de compétences techniques et le temps nécessaire pour créer et exécuter le script et résoudre les problèmes liés à la création de groupes de classes.
- Pas de gestion des erreurs intégrée ni de logique de nouvelle tentative.
- Les modifications d’appartenance ne sont pas synchronisées avec SIS.

> [!NOTE]
> Les équipes de classe nécessitent une appartenance aux groupes masqués de sorte que seuls les enseignants et les étudiants au sein de la classe puissent voir les membres de cette classe. Pour créer un groupe de classes Microsoft 365, consultez [Créer une équipe de classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) pour répondre aux exigences de confidentialité.

### <a name="manual-team-creation"></a>Création manuelle d’équipe

Les utilisateurs peuvent adapter leur expérience Teams en ayant la possibilité de créer leurs propres équipes.

Selon les autorisations d’un utilisateur, il peut :

- [Configurez leurs propres équipes et invitez des utilisateurs, y compris des étudiants](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch).
- [Ajoutez manuellement des utilisateurs à l’équipe](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954).
- [Partagez un code de jointure](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).
- [Partagez un lien vers l’équipe](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

Il est préférable que les enseignants ajoutent leurs étudiants à l’équipe pour s’assurer que les étudiants y ont accès et qu’ils soient avertis qu’ils ont été ajoutés.

#### <a name="benefits-of-manual-team-creation"></a>Avantages de la création manuelle d’une équipe

- Donne aux enseignants un contrôle total de la création de classes.
- Les équipes de classes sont créées immédiatement.

#### <a name="considerations-for-manual-team-creation"></a>Considérations relatives à la création manuelle d’une équipe

- Nécessite l’intervention et le temps de l’enseignant.
- L’appartenance des étudiants n’est pas synchronisée avec SIS et nécessite une gestion manuelle.
- Les étudiants bénéficieront d’un accès immédiat aux équipes de classe.

### <a name="recommended-best-practices"></a>Recommandations recommandées

- Déployez dès maintenant pour vous assurer que tout fonctionne correctement et prêt pour le premier jour de l’école.

- Pour les problèmes liés à la création automatique d’équipe SDS, les enseignants peuvent utiliser la [méthode de création d’équipe dirigée par les enseignants](#educator-led-team-creation-from-microsoft-365-class-groups) pour réessayer. [La création manuelle d’une équipe](#manual-team-creation) est une autre solution, mais les classes ne se synchronisent pas avec SIS.

- La limite de l’équipe des clients est de 500 000 équipes. Par conséquent, les administrateurs doivent réduire le nombre d’équipes inutilisées pour éviter d’atteindre ces limites. Pour plus d’informations, consultez [Limites et spécifications pour Microsoft Teams](limits-specifications-teams.md).  

# <a name="educator-early-access"></a>[Accès précoce aux enseignants](#tab/early-access)

## <a name="early-access-to-class-teams"></a>Accès anticipé aux équipes de cours

Early Access Class Teams permet aux enseignants d’accéder à leurs équipes de classe avant que leurs étudiants puissent l’afficher. Les enseignants auront le temps de configurer, d’ajouter des fichiers et de s’organiser avant d’accorder l’accès à leurs étudiants.

Lorsqu’ils sont prêts pour que les étudiants accèdent à l’équipe, ils peuvent [activer leur classe](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78).

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>Comment créer des équipes de classe qui permettent aux enseignants une accès anticipé à la configuration d’une équipe avant d’autoriser les étudiants ?

Les équipes créées à partir de regroupements (via SDS, le format enseignant ou l’API Graph) créent automatiquement des équipes d’accès anticipé en amont par défaut.

Pour créer vos propres équipes d’accès anticipé à l’aide de l’API Graph, vous devez [créer une classe](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) et [créer l’équipe à partir d’un groupe](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true).

### <a name="how-do-i-check-if-a-class-is-activated"></a>Comment vérifier si une classe est activée ?

Dans le [type de ressource d’équipe](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true), affichez la propriété [isMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true) pour voir si une classe est activée.

Utilisez la [l’API obtenir l’équipe](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) pour interroger la propriété ```isMembershipLimitedToOwners``` pour une classe spécifique. Si l’équipe est activée, elle renvoie la valeur faux. Si l’équipe n’a pas été activée, elle retourne la valeur true.

### <a name="how-do-i-activate-a-class-for-an-educator"></a>Comment activer une classe pour un enseignant ?

Utilisez [l’API Mettre à jour l’équipe](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true) et définissez la ```isMembershipLimitedToOwners``` propriété sur false pour activer l’équipe au nom de votre enseignant. Une fois qu’une équipe est activée, elle ne peut pas être inversée.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Créez des équipes pour la communication et la collaboration du personnel

[Les équipes de type personnel](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) sont destinées aux administrateurs de l’éducation et au personnel pour partager des informations et travailler ensemble sur des initiatives à l’échelle de l’institut.

Les administrateurs de l’éducation peuvent ajouter du personnel à l’équipe avec l’Assistant création [d’équipe, en ajoutant des membres après la création de l’équipe](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9), ou en [partageant un code de jointure ou un lien vers l’équipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f).

# <a name="meeting-scenarios"></a>[Scénarios de réunion](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Scénarios de réunions Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Réunions collaboratives pour les classes virtuelles

Les [réunions Microsoft Teams](./tutorial-meetings-in-teams.yml) prennent en charge jusqu’à 250 participants simultanément avec la possibilité d’avoir du son, de la vidéo, un [partage de contenu](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), des tableaux blancs et des notes partagées.

Les réunions peuvent être les suivantes :

- [Planifié dans le client Teams](./tutorial-meetings-in-teams.yml).
- Enregistré et enregistré pour que les participants passent en revue ultérieurement.
- [Transcrit pour trouver facilement du contenu](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308).
- Accessible à l’aide d’un ordinateur portable ou d’un téléphone mobile webcam, microphone et haut-parleur.
- [Optimisé pour des appareils spécifiques](https://products.office.com/microsoft-teams/across-devices/devices).
- Terminé pour tous les participants afin de s’assurer que les étudiants ne sont pas dans une réunion non supervisée.

### <a name="districtuniversity-events-or-updates"></a>Événements ou mises à jour de départements/d'universités

Certaines réunions ont un large public et des besoins de production supplémentaires. Ces réunions ont souvent des présentateurs, des producteurs définis ainsi que des discussions modérées (questions et réponses).

Teams prend en charge ces sessions à l’aide des [événements en direct Microsoft Teams](teams-live-events/what-are-teams-live-events.md).

Les événements en direct peuvent être utilisés pour des scénarios, tels que :

- Mises à jour à l’échelle du district ou de l’université.
- Adresses de leadership.
- Instructions pour les grandes classes ou les groupes d’étudiants.
- S’étendre à votre communauté.

Pour en savoir plus sur la tenue de sessions en direct, consultez :

- [Planifiez et planifiez un événement en direct](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502).
- [Produire un événement en direct](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb).
- [Participez à un événement en direct](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac).
- [Modération d’un Q&A](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

# <a name="resources"></a>[Ressources](#tab/resources)

## <a name="support-resources"></a>Ressources de support

Pour obtenir une vue d’ensemble générique de la transition vers l’apprentissage à distance, [commencez ici](https://www.microsoft.com/education/remote-learning)

Si vous êtes administrateur informatique, enseignant, étudiant ou tuteur, ces ressources peuvent vous aider à utiliser Teams :

- **Administrateurs informatiques**
  - [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).
  - [Téléchargez et distribuez des clients Teams](get-clients.md).
  - [Résolution des problèmes teams](/MicrosoftTeams/troubleshoot/teams).
  - [Teams pour l’infrastructure de bureau virtualisée](./teams-for-vdi.md).
  - [Surveillez et gérez la qualité des appels](monitor-call-quality-qos.md).
  - [Vérifiez l’intégrité du service pour Teams](service-health.md).
  - [Optimisez le trafic Microsoft 365 pour le personnel distant](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571).
  - [Contacts de support pour Teams](/microsoft-365/admin/contact-support-for-business-products).
  - [Teams pour l'éducation webinaires](https://aka.ms/TeamsEDUWebinars).

- **Enseignants**
  - [Centre d’aide pour les enseignants](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).
  - [Aide sur l’apprentissage à distance](https://aka.ms/RemoteLearningHelp).
  - [Téléchargez Teams](get-clients.md).
  - [Teams pour l'éducation webinaires](https://aka.ms/TeamsEDUWebinars).
  - [Cours en ligne pour les enseignants utilisant Teams](https://education.microsoft.com/course/9c9f5c11/overview).
  - [Cours en ligne pour concevoir des environnements d’apprentissage collaboratif avec Teams](https://education.microsoft.com/course/b1e15cfc/overview).
  - [Déposez un ticket de support](https://www.microsoft.com/microsoft-teams/download-app).

- **Étudiants**
  - [Centre d’aide pour les étudiants](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694).
  - [Aide sur l’apprentissage à distance](https://aka.ms/RemoteLearningHelp).
  - [Téléchargez Teams](https://www.microsoft.com/microsoft-teams/download-app).

- **Gardiens**
  - [Aide sur l’apprentissage à distance](https://aka.ms/RemoteLearningHelp).
  - [Téléchargez Teams](https://www.microsoft.com/microsoft-teams/download-app).

---
