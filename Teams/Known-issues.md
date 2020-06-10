---
title: Support pour Microsoft Teams au sein de votre organisation
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.custom: seo-marvel-mar2020
ms.reviewer: marcl, billkau
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Utilisez ces ressources pour le support de Microsoft Teams au sein de votre organisation, que vous soyez administrateur de Teams ou ingénieur du support technique.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 573e4346e0272a9bc7b11447b4f2de4933caa0da
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665736"
---
# <a name="support-microsoft-teams-in-your-organization"></a>Support pour Microsoft Teams au sein de votre organisation

> [!NOTE]
> Cet article remplace l’article problèmes connus des équipes. 

Utilisez les ressources de cet article pour assurer le support de Teams au sein de votre organisation. 

Commencez par examiner la liste des [problèmes courants et leurs résolutions](#common-issues-and-resolutions) plus bas dans cet article.

Ensuite, si vous ne trouvez pas ce dont vous avez besoin, accédez à [Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) et recherchez votre problème dans la table des matières ou dans la boîte de dialogue **Filtrer par titre**. 
:::image type="content" source="media/known-issues1.png" alt-text="Capture d’écran de la table des matières et de la zone de filtre dans la page Résolution des problèmes de Teams":::

Si vous êtes toujours bloqué, contactez le [Support Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).


## <a name="common-issues-and-resolutions"></a>Problèmes courants et leurs résolutions

> [!NOTE]
> Si vous avez besoin d’aide pour déployer Teams afin de prendre en charge les travailleurs à distance (WFH) en raison du COVID-19, consultez la section [Prise en charge des travailleurs à distance avec Teams](support-remote-work-with-teams.md). De plus, vous pouvez avoir droit à une aide au déploiement dans le cadre du programme Microsoft 365 FastTrack. Visitez le [Centre FastTrack](https://www.microsoft.com/fasttrack) pour envoyer une demande.

### <a name="for-all-teams-customers"></a>Pour tous les clients Teams

| |  |
|---------|---------|
|**Vous débutez avec Teams ?**    |Voir la [Prise en main de Microsoft Teams](get-started-with-teams-quick-start.md).         |
|**Autoriser l’accès invité dans Teams**     |Examinez la [liste de contrôle d’accès invité Teams](guest-access-checklist.md) et vérifiez que toutes les étapes sont effectuées. Consultez les ressources supplémentaires suivantes :<ul><li>[Comprendre l'accès invité dans Microsoft Teams](guest-access.md)</li>[Comment un invité rejoint une équipe](guest-joins.md) <li>[Configuration : liste de contrôle d'accès invité Microsoft Teams](guest-access-checklist.md)</li></ul>|
|**Réunions Teams et la composition de numéros**    |Vous avez besoin d’aide pour activer ou configurer l’audioconférence dans Teams ? Cet utilisateur a-t-il été créé récemment ? Si c’est le cas, vous devez attendre entre 2 et 24 heures **pour que les paramètres prennent effet**.<br>Pour vérifier que l’utilisateur dispose d’une licence pour l’audioconférence et possède un numéro payant par défaut :<br><ol><li>Dans le Centre d’administration Microsoft 365, accédez à **Utilisateurs actifs**, puis sélectionnez l’utilisateur concerné.</li><li> Selon la version du centre d’administration, choisissez **Licences et applications** ou cliquez sur **Modifier** dans les **Licences de produits**.</li><li> Vérifiez que l’utilisateur a sélectionné des licences pour l'Audioconférence, Microsoft Teams et Skype Entreprise Online (plan 2).</li><li>Sous les **Centres d’administration**, cliquez sur **Afficher tout**, puis cliquez sur **Teams**.</li><li>Dans le Centre d’administration Microsoft Teams, cliquez sur **Portail hérité**.</li><li>Dans le Centre d’administration Skype Entreprise, cliquez sur **Audioconférence**, puis sur **Utilisateurs**.</li><li>Sélectionnez l’utilisateur concerné et vérifiez qu'il dispose d’un numéro payant par défaut.</li> </ol> Pour plus d’informations, consultez [Plans d’appels](calling-plans-for-office-365.md) ou appelez l’équipe de facturation Microsoft Commerce pour obtenir de l’aide sur les questions liées à la gestion des licences. <br><br>Ressources supplémentaires :<ul><li>[Réunions et conférences dans Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[Audioconférence](audio-conferencing-in-office-365.md)</li></ul>       |
|**Licence exploratoire Teams**     |L’expérience exploratoire Microsoft Teams permet aux utilisateurs au sein de votre organisation d’Azure Active Directory (AAD) et de ne pas être licenciés pour Teams de lancer une expérience exploratoire de Teams. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation. La précédente [Version d'évaluation dans le cloud commercial Microsoft](iw-trial-teams.md) est désormais remplacée par l'expérience exploratoire Teams. <br><br>Ressources supplémentaires :<ul><li>[Comment les utilisateurs s’inscrivent-ils pour l’expérience exploratoire Teams ?](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gérer l’expérience exploratoire de Teams](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**Canaux privés**    |Les canaux privés dans Microsoft Teams créent des espaces ciblés pour la collaboration au sein de vos équipes. Seuls les utilisateurs de l’équipe qui sont propriétaires ou membres du canal privé peuvent accéder au canal. Tous les utilisateurs, notamment les invités, peuvent être ajoutés en tant que membre d’un canal privé, dès lors qu’ils sont déjà membres de l’équipe.<br><br>Vous souhaiterez peut-être utiliser un canal privé si vous souhaitez limiter la collaboration à ceux qui en ont besoin ou si vous souhaitez faciliter la communication entre un groupe de personnes affectées à un projet spécifique, sans avoir à créer une équipe supplémentaire à gérer.<br><br>Ressources supplémentaires :<ul><li>[Comment les utilisateurs s’inscrivent-ils pour l’expérience exploratoire Teams ?](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gérer l’expérience exploratoire de Teams](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**Stratégies de réunion**|[Stratégies de réunion](meeting-policies-in-teams.md): elles sont utilisées pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par des utilisateurs au sein de votre organisation. Après avoir créé une stratégie et effectué vos modifications, vous pouvez affecter des utilisateurs à la stratégie.         |
||**Modifier ou créer une stratégie de réunion**<br><br>Pour modifier ou créer une stratégie de réunion, accédez au Centre d’administration Microsoft Teams > **Réunions** > **Stratégies de réunion**. Sélectionnez une stratégie dans la liste ou cliquez sur **Ajouter**. Si vous créez une stratégie, ajoutez un nom et une description. Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères. Choisissez les paramètres, puis cliquez sur **Enregistrer**. Par exemple, imaginons que vous avez un grand nombre d’utilisateurs et que vous voulez limiter la quantité de bande passante requise par la réunion. Vous devez créer une stratégie personnalisée nommée « bande passante limitée » et désactiver les paramètres suivants :<br><br>Sous ** Audio & vidéo** :<ul><li>Désactivez l’option Autoriser l’enregistrement Cloud.</li><li>Désactivez Autoriser la vidéo IP.</li></ul>Sous **Partage de contenu** :<ul><li>Désactiver le mode de partage d’écran.</li><li>Désactivez  Autoriser le tableau blanc.</li><li>Désactivez Autoriser les notes partagées.</li></ul>Vous pouvez ensuite attribuer la stratégie aux utilisateurs.         |
| |**Affecter une stratégie de réunion aux utilisateurs**<br><br>Pour affecter une stratégie de réunion à un seul utilisateur :<ol><li>Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</li><li>Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.</li><li>Sous **Stratégie de réunion**, sélectionnez la stratégie que vous souhaitez attribuer, et puis cliquez sur **Appliquer**.</li></ol> Pour affecter une stratégie à plusieurs utilisateurs à la fois : <ol><li>Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.</li><li>Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.</li><li>Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.</li></ol>Vous pouvez effectuer les opérations suivantes :<ol><li>Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **Réunions > Stratégies de réunion**.</li><li>Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.</li><li>Sélectionnez **Gérer les utilisateurs**.</li><li>Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</li><li>Lorsque vous avez terminé l'ajout d'utilisateurs, cliquez sur **Enregistrer**.</li></ol> |
|**Résoudre les problèmes liés à un pavé de numérotation manquant**     |Procédez comme suit : <ul><li>Vérifiez qu’une [licence Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) a été attribuée à l’utilisateur.</li><li>Vérifiez qu’un [Forfait d'appel](calling-plan-landing-page.md) a été attribué à l’utilisateur.</li><li>Activer l'utilisateur pour [Voix Entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail).</li></ul>      |
|**Résoudre les problèmes de connexion de Teams**   |Vérifiez tout d’abord, vérifiez tout d'abord que le [service Microsoft Teams est sain](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth). Recherchez ensuite les codes d’erreur courants et révisez [Pourquoi je rencontre des difficultés pour me connecter à Microsoft Teams ?](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)  Vous pouvez également consulter l’article [Modèles d’identité et authentification dans Microsoft Teams](identify-models-authentication.md).         |

### <a name="for-education-customers"></a>Pour les clients Éducation

|||
|---------|---------|
|Le message « Un élément est manquant ! » s'affiche chez vos clients.   |Veillez à [Activer Microsoft Teams pour votre école](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams). Chez les clients EDU, Teams n’est pas activé par défaut ; vous devrez l’activer au préalable. <br><br>Ensuite, reportez-vous à la section [Enseignement et apprentissage à distance](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4) pour découvrir les derniers conseils sur la configuration de votre établissement scolaire, la planification des leçons, les réunions virtuelles et le partage de contenu avec des étudiants.<br><br>Enfin, n’hésitez pas à consulter les vidéos de formation pour les administrateurs informatiques Microsoft Teams, les decks et bien plus encore sur [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md).        |


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

[Ressources de support pour Teams](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
