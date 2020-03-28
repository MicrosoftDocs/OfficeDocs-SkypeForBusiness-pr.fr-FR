---
title: Problèmes connus pour Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: marcl
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Liste actuelle des problèmes connus pour l'application client et l'expérience administrateur de Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9023c7a7bfe5a629f3f2fdb9589ee3f9ef9efd68
ms.sourcegitcommit: 0549714f17f9994cf832a303ec9bc58a537c3a51
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951509"
---
# <a name="known-issues-for-microsoft-teams"></a>Problèmes connus pour Microsoft Teams

Cet article répertorie les problèmes connus concernant Microsoft Teams, par fonctionnalité spécifique.

## <a name="common-issues-and-resolutions"></a>Résolutions et problèmes courants

> [!NOTE]
> Si vous avez besoin d’aide pour déployer Teams afin de prendre en charge les travailleurs à distance (WFH) en raison du COVID-19, consultez la section [Prise en charge des travailleurs à distance avec Teams](support-remote-work-with-teams.md). De plus, vous pouvez avoir droit à une aide au déploiement dans le cadre du programme Microsoft 365 FastTrack. Visitez le [Centre FastTrack](https://www.microsoft.com/fasttrack) pour envoyer une demande.

### <a name="for-all-teams-customers"></a>Pour tous les clients Teams

| |  |
|---------|---------|
|**Vous débutez avec Teams ?**    |Voir la [Prise en main de Microsoft Teams](get-started-with-teams-quick-start.md).         |
|**Autoriser l’accès invité dans Teams**     |Examinez la [liste de contrôle d’accès invité Teams](guest-access-checklist.md) et vérifiez que toutes les étapes sont effectuées. Consultez les ressources supplémentaires suivantes :<ul><li>[Comprendre l'accès invité dans Microsoft Teams](guest-access.md)</li>[Comment un invité rejoint une équipe](guest-joins.md) <li>[Configuration : liste de contrôle d'accès invité Microsoft Teams](guest-access-checklist.md)</li></ul>|
|**Réunions Teams et la composition de numéros**    |Vous avez besoin d’aide pour activer ou configurer l’audioconférence dans Teams ? Cet utilisateur a-t-il été créé récemment ? Si c’est le cas, vous devez attendre entre 2 et 24 heures **pour que les paramètres prennent effet**.<br>Pour vérifier que l’utilisateur dispose d’une licence pour l’audioconférence et possède un numéro payant par défaut :<br><ol><li>Dans le Centre d’administration Microsoft 365, accédez à **Utilisateurs actifs**, puis sélectionnez l’utilisateur concerné.</li><li> Selon la version du centre d’administration, choisissez **Licences et applications** ou cliquez sur **Modifier** dans les **Licences de produits**.</li><li> Vérifiez que l’utilisateur a sélectionné des licences pour l'Audioconférence, Microsoft Teams et Skype Entreprise Online (plan 2).</li><li>Sous les **Centres d’administration**, cliquez sur **Afficher tout**, puis cliquez sur **Teams**.</li><li>Dans le Centre d’administration Microsoft Teams, cliquez sur **Portail hérité**.</li><li>Dans le Centre d’administration Skype Entreprise, cliquez sur **Audioconférence**, puis sur **Utilisateurs**.</li><li>Sélectionnez l’utilisateur concerné et vérifiez qu'il dispose d’un numéro payant par défaut.</li> </ol> Pour plus d’informations, consultez les [Forfaits d’appels dans Office 365](calling-plans-for-office-365.md) ou appelez l’équipe de facturation Microsoft Commerce pour obtenir de l’aide sur les questions liées à la gestion des licences. <br><br>Ressources supplémentaires :<ul><li>[Réunions et conférences dans Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[Audioconférence dans Office 365](audio-conferencing-in-office-365.md)</li></ul>       |
|**Licence exploratoire Teams**     |L’expérience exploratoire Microsoft Teams permet aux utilisateurs au sein de votre organisation d’Azure Active Directory (AAD) et de ne pas être licenciés pour Teams de lancer une expérience exploratoire de Teams. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation. La précédente [Version d'évaluation dans le cloud commercial Microsoft](iw-trial-teams.md) est désormais remplacée par l'expérience exploratoire Teams. <br><br>Ressources supplémentaires :<ul><li>[Comment les utilisateurs s’inscrivent-ils pour l’expérience exploratoire Teams ?](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gérer l’expérience exploratoire de Teams](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**Canaux privés**    |Les canaux privés dans Microsoft Teams créent des espaces ciblés pour la collaboration au sein de vos équipes. Seuls les utilisateurs de l’équipe qui sont propriétaires ou membres du canal privé peuvent accéder au canal. Tous les utilisateurs, notamment les invités, peuvent être ajoutés en tant que membre d’un canal privé, dès lors qu’ils sont déjà membres de l’équipe.<br><br>Vous souhaiterez peut-être utiliser un canal privé si vous souhaitez limiter la collaboration à ceux qui en ont besoin ou si vous souhaitez faciliter la communication entre un groupe de personnes affectées à un projet spécifique, sans avoir à créer une équipe supplémentaire à gérer.<br><br>Ressources supplémentaires :<ul><li>[Comment les utilisateurs s’inscrivent-ils pour l’expérience exploratoire Teams ?](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gérer l’expérience exploratoire de Teams](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**Stratégies de réunion**|[Stratégies de réunion](meeting-policies-in-teams.md): elles sont utilisées pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par des utilisateurs au sein de votre organisation. Après avoir créé une stratégie et effectué vos modifications, vous pouvez affecter des utilisateurs à la stratégie.         |
||**Modifier ou créer une stratégie de réunion**<br><br>Pour modifier ou créer une stratégie de réunion, accédez au Centre d’administration Microsoft Teams > **Réunions** > **Stratégies de réunion**. Sélectionnez une stratégie dans la liste ou cliquez sur **Ajouter**. Si vous créez une stratégie, ajoutez un nom et une description. Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères. Choisissez les paramètres, puis cliquez sur **Enregistrer**. Par exemple, imaginons que vous avez un grand nombre d’utilisateurs et que vous voulez limiter la quantité de bande passante requise par la réunion. Vous devez créer une stratégie personnalisée nommée « bande passante limitée » et désactiver les paramètres suivants :<br><br>Sous ** Audio & vidéo** :<ul><li>Désactivez l’option Autoriser l’enregistrement Cloud.</li><li>Désactivez Autoriser la vidéo IP.</li></ul>Sous **Partage de contenu** :<ul><li>Désactiver le mode de partage d’écran.</li><li>Désactivez  Autoriser le tableau blanc.</li><li>Désactivez Autoriser les notes partagées.</li></ul>Vous pouvez ensuite attribuer la stratégie aux utilisateurs.         |
| |**Affecter une stratégie de réunion aux utilisateurs**<br><br><ol><li>Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.</li><li>Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.</li><li>Sous **Stratégie de réunion**, sélectionnez la stratégie que vous souhaitez attribuer, et puis cliquez sur **Appliquer**.</li></ol>Pour attribuer une stratégie à plusieurs utilisateurs à la fois, consultez l’article [Modifier en masse les paramètres utilisateur Teams](edit-user-settings-in-bulk.md). Vous pouvez effectuer les opérations suivantes :<ol><li>Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **Réunions > Stratégies de réunion**.</li><li>Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.</li><li>Sélectionnez **Gérer les utilisateurs**.</li><li>Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.</li><li>Lorsque vous avez terminé l'ajout d'utilisateurs, cliquez sur **Enregistrer**.</li>         |
|**Résoudre les problèmes liés à un pavé de numérotation manquant**     |Procédez comme suit : <ul><li>Vérifiez qu’une [licence Teams](assign-teams-licenses.md) a été attribuée à l’utilisateur.</li><li>Vérifiez qu’un [Forfait d'appel](calling-plan-landing-page.md) a été attribué à l’utilisateur.</li><li>Activer l'utilisateur pour [Voix Entreprise](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail).</li></ul>      |
|**Résoudre les problèmes de connexion de Teams**   |Vérifiez tout d’abord, vérifiez tout d'abord que le [service Microsoft Teams est sain](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth). Recherchez ensuite les codes d’erreur courants et révisez [Pourquoi je rencontre des difficultés pour me connecter à Microsoft Teams ?](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)  Vous pouvez également consulter l’article [Modèles d’identité et authentification dans Microsoft Teams](identify-models-authentication.md).         |

### <a name="for-education-customers"></a>Pour les clients Éducation

|||
|---------|---------|
|Le message « Un élément est manquant ! » s'affiche chez vos clients.   |Veillez à [Activer Microsoft Teams pour votre école](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams). Chez les clients EDU, Teams n’est pas activé par défaut ; vous devrez l’activer au préalable. <br><br>Ensuite, reportez-vous à la section [Enseignement et apprentissage à distance avec Office 365 Éducation](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4) pour découvrir les derniers conseils sur la configuration de votre établissement scolaire, la planification des leçons, les réunions virtuelles et le partage de contenu avec des étudiants.<br><br>Enfin, n’hésitez pas à consulter les vidéos de formation pour les administrateurs informatiques Microsoft Teams, les decks et bien plus encore sur [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md).        |

## <a name="administration"></a>Administration

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La stratégie EAF dans le kit de ressources pour une expérience de migration améliorée (EMET) peut identifier de manière incorrecte les optimisations du sandbox Chromium comme des menaces. <br/> |Un problème a été identifié avec le sandbox Chromium, la stratégie de filtrage de l’accès à la table d’exportation des adresses (EAF) dans le kit de ressources pour une expérience de migration améliorée (EMET) et dans la protection avancée contre les menaces Windows Defender (ATP) pouvant identifier de manière incorrecte les optimisations du sandbox Chromium comme des menaces. Cela entraîne un fonctionnement incorrect de Teams.  <br/> | Pour résoudre ce problème, désactivez EAF pour Teams. Vous trouverez plus d'informations sur le problème dans les [Directives d’atténuation EMET](https://support.microsoft.com/help/2909257/emet-mitigations-guidelines) Pour des informations complémentaires sur Windows Defender ATP et la stratégie EAF, reportez-vous à la rubrique [Activer la protection contre les attaques](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) <br/> |11/10/2018 <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible d’ajouter des membres aux équipes lorsque UsersPermissionToReadOtherUsersEnabled est défini sur false  <br/> |Lorsque cette valeur est définie sur False dans Azure Active Directory, les utilisateurs ne peuvent pas ajouter de membres externes ou internes dans Microsoft Teams, et le message d’erreur suivant s’affiche : « Nous n’avons pas pu ajouter le membre. Désolé... Nous avons rencontré un problème. Veuillez réessayer plus tard. » Toutefois, les membres peuvent être ajoutés directement aux groupes Office 365.    <br/> |Définissez ce paramètre sur true dans AAD.  <br/> |10/04/18  <br/> |

## <a name="apps"></a>Applications

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|80 utilisateurs de la version Chrome ne peuvent pas se connecter à certaines applications sur la plateforme Teams.<br/>|Une fois que les utilisateurs ont correctement entré leurs informations d’identification par mot de passe dans la page de connexion d’une application, un cycle continu est initié lorsque l’utilisateur n’est pas reconnu par l’application et il est redirigé vers la page de connexion de l’application. <br/>|Demandez aux utilisateurs d’utiliser le client de bureau Teams. |15/11/19<br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L’[Accès conditionnel](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) peut ne pas fonctionner lors de l’utilisation de l’onglet « Site web » ou « Azure DevOps » dans l’application de bureau.<br/> |Si un site web, tel qu’un portail intranet, est doté de stratégies d’accès conditionnel (par exemple, un navigateur, des restrictions d’adresse IP ou une conformité appareil), le site web peut ne pas s’afficher sous forme d’onglet dans Teams dans l’application de bureau. <br/> |Utilisez Teams dans un navigateur plutôt que dans l’application de bureau.  <br/> |01/07/18  <br/> |

## <a name="audio-conferencing"></a>Audioconférence

|**Problème**|**Comportement/symptômes**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les appelants RTC ayant le même numéro « De » sont affichés comme le même utilisateur dans la liste de présence de la réunion.  <br/> |Lorsque plusieurs appelants RTC rejoignent une réunion et que leurs identifications de l’appelant sont masquées sous la forme d'un numéro unique, ils s'affichent en tant qu'appelant unique dans la liste de présence de la réunion.  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|Le panneau d'information sur la réunion ne s'affiche pas de façon intermittente.  <br/> |Le panneau d'informations de réunion peut ne pas s'afficher dans le client Teams, lorsque les utilisateurs tentent de rechercher les numéros de téléphone du pont de conférence ou l'ID de conférence.  <br/> |Consultez les détails de la réunion ou le calendrier Outlook pour afficher les numéros de téléphone du pont de conférence ou l'ID de la conférence.  <br/> |25/09/2017  <br/> |
|Les invitations à des réunions à partir du complément Outlook affichent des caractères anormaux dans les coordonnées RTC pour les paramètres régionaux non américains.  <br/> |Lors de la planification de réunions privées à l'aide du complément Outlook pour Microsoft Teams sur un ordinateur avec des paramètres régionaux non américains, les coordonnées RTC peuvent contenir des caractères anormaux.  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|La sortie de numérotation doit utiliser 5 chiffres ou plus.  <br/> |Les utilisateurs qui tentent de composer un numéro à partir d'une réunion doivent taper 5 chiffres ou plus, même si la règle de normalisation du forfait de numérotation est disponible pour normaliser la numérotation des numéros courts à E.164.  <br/> |Appelez en tapant le numéro SDA complet ou le format de numéro local, au lieu du numéro de poste interne.  <br/> |25/09/2017  <br/> |
|Le contrôle d'appel sortant ne s'affiche pas de façon intermittente.  <br/> |Le contrôle d'appel sortant peut ne pas être visible à partir du panneau Informations sur la réunion.  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|L'ID de conférence statique n'est pas pris en charge pour les réunions Microsoft Teams.  <br/> |Si l'administrateur remplace le paramètre par défaut de l'ID de conférence dynamique par l'ID de conférence statique, ce paramètre ne s'applique pas aux réunions Microsoft Teams. Reportez-vous à la rubrique [Utiliser des ID dynamiques d’audioconférence dans votre organisation](/skypeforbusiness/audio-conferencing-in-office-365/using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Aucune solution.  <br/> |25/09/2017  <br/> |
|Les coordonnées de réunion RTC ne sont pas disponibles pour les utilisateurs locaux de Skype Entreprise.  <br/> |Si l'utilisateur est un utilisateur local de Skype Entreprise, à qui on a attribué Skype Entreprise Online, une audioconférence et des licences Teams, toutes les réunions programmées à l'aide de Teams n'incluront pas les coordonnées de réunion RTC. <br/> |Aucune solution.  <br/> |1/2/2018  <br/> |
|Informations sur l’interopérabilité de la vidéo dans le Cloud dans Conférence maintenant  <br/> ||Si vous créez une instance Conférence maintenant d'une réunion dans Microsoft Teams avec une licence CVI existante, les informations CVI ne seront pas renseignées. <br/> ||Il est recommandé de planifier la date de réunion pour que cette information soit complétée.  <br/> |11/06/2019  <br/> |

## <a name="authentication"></a>Authentification

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Teams à besoin d’accéder à Google Gstatic <br/> |Pour l’instant, Teams a besoin d’accéder (port TCP 443) au service Google ssl.gstatic.com pour tous les utilisateurs, c’est vrai même si vous n’utilisez pas Gstatic. Teams supprimera cette exigence prochainement (début 2020). <br/> | Aucune solution. <br/> |30/1/20  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Après la modification le mot de passe du compte utilisateur, un message d’erreur s’affiche : votre mot de passe a été modifié ou le serveur doit de nouveau disposer de vos informations de connexion. Cela se produit de nouveau, même avec le nouveau mot de passe. <br/> | Les équipes résoudront prochainement ce problème dans un correctif déployé. <br/> | Déconnexion et reconnexion avec des informations d’identification incorrectes. Après l’échec, entrez vos correctes informations d’identification. <br/> |09/01/20  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lorsque vous tentez d'ouvrir Teams sur Internet Explorer ou Edge, une boucle se produit ou le programme se bloque et ne se connecte pas.   <br/> | Votre organisation utilises la fonction de sites approuvés dans Internet Explorer et l'application Web Teams n'est pas correctement journalisée car les sites approuvés pour Teams ne sont pas autorisés. <br/>|Dans les paramètres d'IE, effectuez les modifications suivantes en utilisant des droits d'administrateur ou un objet de stratégie de groupe :<br/><ol><li>Sous **Options Internet** &gt; **Confidentialité** &gt; **Avancé**, acceptez les cookies internes et tierce partie et cochez la case **Toujours autoriser les cookies de la session**.</li><li>Cliquez sur **Options Internet** &gt; **Sécurité** &gt; **Sites de confiance** &gt; **Sites** et ajoutez l’adresse suivante :<ul><li>https://login.microsoftonline.com</li><li>https://\*.teams.microsoft.com</li></ul></li></ol><br/><b>REMARQUE</b> : Validez et autorisez toujours les URL approuvées pour Teams et les conditions requises figurant dans le document suivant : [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).   <br/> |01/11/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Microsoft Teams se connectera toujours au compte de l’ordinateur lié à un domaine.   <br/> |Si un utilisateur qui a deux comptes Teams différents et une machine avec la jonction à un domaine activée, Teams utilisera le profil lié à un domaine pour connecter automatiquement l’utilisateur à Teams. Pour basculer sur l’autre compte Teams, l’utilisateur doit se déconnecter manuellement de l’application puis entrer les informations d'identification du second compte pour se connecter. S’il se déconnecte de Teams et redémarre la machine, au démarrage, Teams se connectera automatiquement en utilisant le profil joint au domaine. <br/> | Si les utilisateurs sont connectés à un ordinateur joint à un domaine et que vous ne souhaitez pas que leur nom d’utilisateur soit déjà rempli sur l’écran de connexion à Teams, les administrateurs peuvent définir le registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur (UPN) Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams SkipUpnPrefill\(REG_DWORD) 0X00000001 (1). Le nom d’utilisateur, qui doit être renseigné pour les noms d’utilisateur qui se terminent par « .local » ou « .corp », est activé par défaut, vous n’avez ainsi pas besoin de définir une clé de registre pour le désactiver. Référence https://docs.microsoft.com/microsoftteams/sign-in-teams. <br/> |02/08/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Échec de l’authentification moderne - Authentification par formulaire désactivée  <br/> |Si l'authentification multifacteur échoue, réalisez l'authentification depuis l'application web.  <br/> Pour plus d'informations, voir [Prise en charge du paramètre des services ADFS prompt=login](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-prompt-login).  <br/> |Vérifiez ce paramètre : `Set -MsolDomainFederationSettings -DomainName yourdomainhere -PreferredAuthenticationProtocol WsFed -SupportsMfa $False -PromptLoginBehavior Disabled`.  <br/> |19/06/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Planificateur sur la version d’authentification unique (SSO) <br/> |L'authentification unique (SSO) ne s'applique pas au planificateur. Vous devrez vous reconnecter à la première utilisation du planificateur sur chaque client.  <br/> |Aucune solution. Nous travaillons actuellement sur d'autres améliorations du système d'authentification.  <br/> |28/02/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible d'enregistrer la photo de profil  <br/> |Les utilisateurs ne peuvent pas enregistrer leur photo de profil lorsque la boîte aux lettres Exchange est hébergée sur site sur Exchange 2016 CU2 ou une version inférieure.  <br/> |Aucune solution.  <br/> |28/02/2017  <br/> |

## <a name="browser"></a>Navigateur

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Artéfacts verts dans le rendu vidéo Chrome  <br/> |Des artéfacts verts apparaissent lors du visionnement d'une vidéo ou du partage de l'écran dans un appel ou une réunion dans Chrome.  <br/> |Désactivez le paramètre d'accélération matérielle dans Chrome.  <br/> |03/08/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Prise en charge du client web par Safari  <br/> | Les équipes sont désormais disponibles en mode aperçu sur Safari 11.1 + sur macOS. En mode Aperçu, les utilisateurs peuvent exécuter dans les problèmes liés à la prévention de suivi Safari Intelligent[Problèmes connus Safari](https://go.microsoft.com/fwlink/?linkid=2062082).  <br/> | Tandis que le support des navigateurs Safari est en version préliminaire, accédez à **Préférences > Confidentialité**  et décochez la case du paramètre **Empêcher le suivi intersites**  . Ensuite, fermez votre navigateur et accédez à l’adresse teams.microsoft.com dans Safari. <br/> |02/11/2016  <br/> |


## <a name="channels"></a>Canaux

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Lorsqu'un utilisateur quitte l’entreprise, il apparaît dans Microsoft Teams comme « Utilisateur inconnu »<br/> |Lorsqu'un utilisateur quitte l’entreprise, il apparaît dans Microsoft Teams comme « Utilisateur inconnu ». L'onglet de conversation affiche également : « Un utilisateur inconnu a été ajouté à l’équipe ». <br/> |Aucune solution.  <br/> |12/09/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs ne peuvent pas recréer un nom de canal préexistant.  <br/> |Une fois qu'un nom de canal a été défini, même si le canal est supprimé, le nom ne peut pas être réutilisé. Notre système conserve ces données pour des raisons de protection des informations.  <br/> |Aucune solution.  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Renommer un canal dans Microsoft Teams ne renomme pas le dossier correspondant dans SharePoint Online.  <br/> |Si un canal est renommé dans Microsoft Teams, le dossier dans la bibliothèque de documents SharePoint Online correspondant à l’équipe ne reflète pas la modification. Le nom du dossier SharePoint Online apparaît en haut de l’onglet Fichiers du canal renommé.  <br/> |Aucune solution.  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L’aperçu de l’URL peut ne pas s’afficher pour toutes les URL  <br/> |Certaines URL peuvent ne pas afficher d’aperçu.  Cela dépend de la capacité d’afficher un aperçu de l’URL d’origine. <br/> |Aucune solution. <br/> |01/09/2018 <br/> |

## <a name="chat"></a>Conversation

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les @mentions de message supprimé envoient une notification avec le lien du canal  <br/> |Il existe une restriction connue lorsque vous êtes @mentionné dans un message qui est supprimé ; la notification dans le flux accédera au canal mais pas au message spécifique. <br/> | Par défaut <br/> | 28/03/2017  <br/>|


## <a name="client"></a>Client

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de démarrer Teams pour Surface Hub à partir du Microsoft Store |Microsoft Teams pour Surface Hub ne démarre pas lorsque vous cliquez sur **Lancer** dans le Microsoft Store. | Le lancement de Teams pour l’application Surface Hub à partir de la liste du Microsoft Store n’est pas pris en charge par Windows sur Surface Hub. <br> <br/> Redémarrez le Surface Hub après l’installation de Teams. | 27/02/18 |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Teams ne se met pas à jour automatiquement   <br/> | Lorsque Microsoft Teams est installé dans Program Files à l’aide des scripts d'installation au lieu de l’emplacement par défaut, le client ne se met pas à jour automatiquement lorsque de nouvelles versions sont disponibles.    <br/> | Par défaut. Assurez-vous d'installer l’application dans l’emplacement par défaut : `user\Appdata`.  <br/> | 07/09/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Un lien symbolique ou le mappage d’un lecteur sur C:\utilisateurs lance l’application sur un écran blanc  <br/> | Lorsque Microsoft Teams est installé dans Program Files à l’aide des scripts d'installation au lieu de l’emplacement par défaut, le client ne se met pas à jour automatiquement lorsque de nouvelles versions sont disponibles.   <br/> | Par défaut. Assurez-vous d'installer l’application dans l’emplacement par défaut : `user\Appdata`. Si le mappage doit exister, vous devez utiliser la version web de Microsoft Teams.  <br/> | 07/09/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Un lien symbolique ou le mappage d’un lecteur sur C:\utilisateurs lance l’application sur un écran blanc  <br/> |Si l’emplacement par défaut de `C:\users\<user>\appData` est modifié en déplaçant le dossier `C:\users` ou en utilisant un lien symbolique, l’application se lance avec un écran blanc.   <br/> |Il n’existe pas de solution de contournement. Si le mappage doit exister, vous devez utiliser la version web de Microsoft Teams.   <br/> |13/03/2017  <br/> |

## <a name="environment"></a>Environnement

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L'archivage des boîtes aux lettres de groupe (stockage supplémentaire) n'est pas activé.  <br/> |Dans le Centre de sécurité et conformité Office 365, les administrateurs généraux n'ont pas la possibilité d'activer l'archivage pour les boîtes aux lettres de groupe. Cela est possible uniquement pour les boîtes aux lettres utilisateur.  <br/> |Si la capacité de la boîte aux lettres de groupe est presque atteinte, prenez contact avec le support de Microsoft Office pour augmenter la capacité.  <br/> |01/02/2017  <br/> |

## <a name="guest-access"></a>Accès invité

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les clients des pays de l'UE et de la région APAC reçoivent une erreur lorsqu'ils ajoutent un utilisateur invité à partir d'un autre client.    <br/> | Les clients des pays de l'UE et de la région APAC subissent un retard de réplication entre Microsoft Teams et Azure Active Directory. Lorsqu'un utilisateur d'un client d'un pays de l'UE ou de la région APAC tente d'ajouter un utilisateur invité d'un autre client, il reçoit un message d'erreur indiquant de réessayer.   <br/> |Cliquez sur le bouton Réessayer pour ajouter l'utilisateur invité.  <br/> |08/11/2017  <br/> |

## <a name="linux"></a>Linux

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|AutoStart sur Linux ne fonctionne pas. <br/> |AutoStart sur Linux ne démarre pas l’application Teams. <br/> | <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Écran blanc lors de la reprise à partir de veille/suspension. <br/> |Lorsque votre ordinateur sort de veille ou de mode suspension, il peut y avoir un changement de réseau (en particulier lorsque l’ordinateur est connecté à un réseau privé virtuel avant d’être mis en veille/suspendu) et cela prend du temps pour que l’ordinateur récupère la connexion. La combinaison de ces éléments peut entraîner l’affichage d’un écran blanc pour Teams. <br/> |Redémarrer le client Teams peut aider.  <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Curseur manquant lors du partage de l’écran. <br/> |Pendant le partage de l’écran, l’autre partie ne voit pas le curseur de la personne qui partage l’écran. <br/> | <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Problème d’exécution en parallèle avec VMWare Workstation. <br/> |L’application Teams rencontre des problèmes lors de l’exécution en parallèle de VMWare Workstation. <br/> | <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Notifications KDE créent une nouvelle barre des tâches.<br/> |La notification sur KDE crée une nouvelle fenêtre dans la barre des tâches. <br/> | <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les gestionnaires de package n’affichent pas Modifier la liste. <br/> |Le gestionnaire de package n’affiche pas Modifier la liste. <br/> | <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de démarrer le client Teams en mode hors connexion. <br/> |Impossible de démarrer Teams hors connexion dans le client Linux. <br/> | <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Paramètres des appareils pendant les réunions. <br/> |Lorsque vous vous trouvez dans une réunion et modifiez les paramètres de l’appareil, l’indicateur du microphone n’enregistre aucun élément récupéré. <br/> | <br/> |05/12/19  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de fermer l’application Teams à l’aide du clavier. <br/> |Impossible de fermer l’application Teams à l’aide de la `$mod + shift + q` par défaut ou en cliquant sur le bouton Fermer dans l’application. <br/> | <br/> |05/12/19  <br/>|

## <a name="meetings"></a>Meetings

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs ne peuvent pas accéder aux réunions/connecteurs mais ont des boîtes aux lettres Exchange Online. <br/> |Le client bloque activement EWS des services dans Exchange Online mais MS Teams doit être compatible au sein des stratégies EWS. <br/> |Pour que MS Teams soit compatible, vous devez ajouter les chaînes de l’agent utilisateur suivantes pour MS Teams dans EWSAllowList : `SkypeSpaces/*` et `MicrosoftNinja/*`, astérisques inclus. La commande suivante peut être utilisée : `Set-organizationconfig -EwsAllowList @{Add="MicrosoftNinja/*","SkypeSpaces/*"}`<br/> Pour plus d'informations : https://docs.microsoft.com/powershell/module/exchange/organization/Set-OrganizationConfig?view=exchange-ps. <br/> |30/05/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Skype Entreprise est requis pour certaines réunions.  <br/> |Votre calendrier de rendez-vous s'affiche de manière pratique dans Microsoft Teams. Pour participer à une réunion, cliquez sur le bouton **Rejoindre**. <br/> Nous poursuivons le développement à ce sujet, mais pour le moment, si la réunion était planifiée au moyen de Skype Entreprise et que vous cliquez sur **Rejoindre**, Microsoft Teams lance votre client Skype Entreprise pour finaliser votre accès à la réunion. Les réunions planifiées dans Microsoft Teams s'ouvrent directement dans le produit.  <br/> À l'avenir, nous uniformiserons cette procédure.  <br/> |Cliquez sur **Rejoindre**. Microsoft Teams décidera judicieusement si Skype Entreprise est requis pour qu'un utilisateur rejoigne la réunion en fonction de l'URL mentionnée dans la description de la réunion.  <br/> |13/03/2017  <br/> |


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Nombre maximum de participants pour les réunions  <br/> |Chaque réunion Microsoft Teams peut accueillir jusqu'à 250 participants.  <br/> |Créer des événements en direct dans teams qui peuvent accueillir 10 000 utilisateurs.  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Réunions non disponibles  <br/> |La fonctionnalité de réunion n’est pas disponible lorsque la boîte aux lettres Exchange est hébergée sur site dans une version inférieure à Exchange 2016 CU3.  <br/> |Effectuez une mise à niveau vers Exchange 2016 CU3 ou une version suivante pour le déploiement sur site.  <br/> |28/02/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Aucun son lors du partage de contenu pendant une réunion de diffusion  <br/> |Lors du partage de contenu pendant une réunion de diffusion, le son du contenu partagé (lien YouTube ou fichier vidéo enregistré) ne peut pas être entendu par les participants.  <br/> |Il ne s’agit pas d'un comportement par défaut.  Teams ne prend pas en charge actuellement le son du contenu partagé  <br/> |09/10/2018  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de démarrer la réunion en tant qu’organisateur à partir d’Outlook, car vous risquez d’être bloqué dans la salle d'attente virtuelle  <br/> |Vous pouvez rencontrer ce problème si votre client Outlook est connecté à un autre compte que celui de votre client Teams. <br/> |Lorsque vous rejoignez la réunion, assurez-vous que les clients Outlook et Teams sont connectés au compte à partir duquel la réunion a été planifiée.  <br/> |5/11/18  <br/> |

## <a name="mobile"></a>Mobile

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de voir les canaux ajoutés automatiquement aux favoris  <br/> |Certains membres ne peuvent pas voir les canaux ajoutés automatiquement aux favoris sur l’application mobile.  <br/> |Pour afficher les canaux ajoutés automatiquement aux favoris sur leur application mobile, les membres doivent se connecter au préalable l’application de bureau ou web.  <br/> |30/04/2018  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Il est possible que les utilisateurs ne puissent pas changer de compte sur les appareils mobiles gérés par Intune  <br/> |Il est possible que les utilisateurs ne puissent pas changer de compte sur les appareils mobiles gérés par Intune.  <br/> |Aucune solution.  <br/> |20/09/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Problèmes que vous pouvez rencontrer si vous utilisez iOS 13 bêta  <br/> |1. les notifications Teams ne sont pas activées.  Cela inclut les conversations, les mentions et les appels.  2. L’aperçu des fichiers ne fonctionne pas avec la version bêta.  <br/> |Il n'existe actuellement aucune solution.  Nous travaillons en collaboration avec les développeurs d’Apple pour trouver des correctifs pour ces problèmes.  <br/> | 25/6/19  <br/>|


## <a name="people"></a>Personnes

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Photos de profil des utilisateurs  <br/> | Teams ne comporte pas actuellement de mécanisme permettant d’empêcher les utilisateurs de changer leur photo. L’équipe BTS a rencontré l’équipe de développement qui a consigné le point suivant à prendre en considération : Fonctionnalité 108874 : stratégie IT pour désactiver le chargement de photos de profil   <br/> | Si vous avez des clients qui souhaiteraient avoir la possibilité d’empêcher le chargement de photos de profil dans Teams, veuillez ajouter leur vote et leur script commercial aux commentaires ici : https://microsoftteams.uservoice.com/forums/555103-public/suggestions/18600505-disable-user-ability-to-change-profile-photos <br/> |01/03/2017 <br/> |



## <a name="phone-system"></a>Système téléphonique

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Service de compte de ressource mal configuré <br/> | Les comptes de ressource sur site associés à un standard automatique ou à une file d’attente d’appels créée avant le mois de janvier 2019 risquent de ne pas avoir le paramètre Department correctement défini, ce qui peut entraîner l’échec d’une affectation de numéro de téléphone. Un correctif est en cours pour résoudre ce problème. <br/><br/> Le paramètre Department (service) des comptes de ressources configurés à l’aide de New-CsHybridApplicationEndpoint avec Skype Entreprise Server n’est pas correctement configuré, ce qui entraîne l'échec de la création du compte de ressource dans le centre d'administration Teams. Dans ce cas, vous devez configurer le nom du service dans Active Directory sur site avant de le synchroniser en ligne.|Pour résoudre ce problème, vous pouvez exécuter la cmdlet suivante afin de définir le paramètre Department. Set-MsolUser -ObjectId <Resource Account Object ID> -Department « Instance d’application de communication Microsoft » <br/> Consultez également la [mise à jour du service de surveillance automatique et de files d’attente des appels](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521). |8/5/19 <br/> |


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Retard de synchronisation des comptes de ressource|Vous ne pouvez pas attribuer un numéro de téléphone au compte de ressources ou le message d’erreur « L’instance d’application suivante n’est pas présente dans le Boogie Verification Debugger (BVD) » s'affiche.|Patientez 24 heures pour la synchronisation. Si 24 heures se sont déjà écoulées, supprimez l’affectation du numéro de téléphone, supprimez le compte de ressource, puis recréez-en un sous un autre nom.|18/05/2018|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Vous ne pouvez pas attribuer un numéro de service payant à partir du Centre d’administration Teams|Lorsque vous essayez d’attribuer un numéro de service payant dans le Centre d’administration Teams, l’erreur « Vous avez besoin d’une licence de système téléphonique » s’affiche.|Utilisez plutôt des cmdlets PowerShell pour attribuer un numéro de service payant.|18/05/2018|


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Compte de ressource endommagé|Compte de ressources non fonctionnel|La suppression ou le remplacement de la licence d’un compte de ressource ou la création d’un compte de ressource avec la même URI SIP qu’un compte supprimé précédemment endommage le compte de ressource.|18/05/2018|


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Numéro de téléphone bloqué|Numéro de téléphone bloqué : la suppression du compte de la ressource avant de supprimer le numéro de téléphone bloque le numéro de téléphone.|Contactez le service clientèle Microsoft pour libérer le numéro de téléphone.|18/05/2018|

## <a name="presence"></a>Présence
|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La présence dans Outlook et d'autres applications Office ne s'affiche pas après qu'un utilisateur a été déplacé en mode **Teams uniquement**. <br/> |Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams.  <br/> |Pour voir la présence dans Outlook (et les autres applications Office), Skype Entreprise doit être installé, même si vous exécutez Teams en mode **Teams uniquement**. Microsoft est courant du problème et travaille activement au développement d’un correctif.  <br/> |9/2019  <br/> |



## <a name="provisioning"></a>Mise en service

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Utilisateur SharePoint incorrect créé pour le site SharePoint de Microsoft Teams  <br/> |Le créateur SharePoint d'un groupe Microsoft Teams est un administrateur SharePoint, pas l'utilisateur correct.  <br/> Lors d'un audit depuis la console d'administration SharePoint, le créateur de la page de collection de sites associé au groupe Office 365 créé pour l'équipe dans Microsoft Teams est l'administrateur SharePoint.  <br/> |Aucune solution.  <br/> |21/07/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les utilisateurs n'arrivent pas à créer une équipe.  <br/> |Votre entreprise peut avoir défini une politique limitant les personnes qui peuvent créer des groupes ou des équipes Office 365.  <br/> |Consultez votre administrateur informatique pour comprendre la politique de votre entreprise en matière de création de groupes et d'équipes.  <br/> |13/03/2017  <br/> |

## <a name="skype-for-business-to-teams-upgrade"></a>Mise à niveau de Skype Entreprise vers Microsoft Teams

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|

## <a name="tabs"></a>Onglets

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Onglet de site web source de confusion pour les clients  <br/> |Les onglets de site web ne sont pas équivalents à votre navigateur. Un certain nombre de sites, particulièrement ceux qui requièrent une authentification ou l’utilisation de fenêtres contextuelles, ne fonctionneront pas s’ils sont épinglés en tant qu’onglet de site web.  <br/> |Nous nous efforçons d’améliorer l’interface utilisateur pour que cela soit plus clair pour les clients.  <br/> |02/05/2018  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Onglets qui ne fonctionnent pas depuis l’accès conditionnel a été activé <br/> |Certains onglets peuvent ne plus se charger dans le client de bureau depuis que l’accès conditionnel a été activé sur le client. Les onglets se chargent lorsque le client web est utilisé. Certains onglets pouvant être affectés sont les suivants : PowerBI, VSTS, PowerApps et liste SharePoint.  <br/> |Pour afficher les onglets concernés, vous devez utiliser Teams dans Microsoft Edge, IE ou Chrome avec l’extension de comptes Windows 10 installée. Certains onglets dépendent toujours de l’authentification web, qui ne fonctionne pas dans le client de bureau lorsqu’une autorité de certification est activée. Nous travaillons avec des partenaires pour activer ces scénarios ; nous avons activé jusqu’à présent le Planificateur, OneNote et Stream. <br/> |05/04/2018  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La liste des espaces de travail n'est pas triée par ordre alphabétique.  <br/> |Les utilisateurs qui passent d'un espace de travail à un autre lors de l'ajout d'un onglet PowerBI sont invités à choisir celui qu'ils souhaitent activer parmi une liste non classée par ordre alphabétique.  <br/> |Aucune solution.  <br/> |13/03/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La barre de défilement disparaît quand des rapports sont sélectionnés.  <br/> |Les utilisateurs qui ajoutent des rapports PowerBI ne peuvent pas faire défiler une liste plus longue que la taille d'un écran de rapports sans perdre leur barre de défilement.  <br/> |Utilisez les flèches vers le haut et vers le bas pour faire défiler la liste.  <br/> |13/03/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Intégration du Planificateur Teams avec le Planificateur en ligne <br/> |Les paquets de tâches dans le Planificateur ne s’affichent pas dans l’expérience en ligne du Planificateur.  <br/> |Aucune solution. <br/> |28/02/2017  <br/>|


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Intégration du Planificateur Teams avec le Planificateur en ligne <br/> |Les propriétaires ne peuvent pas créer de plan pour une équipe créée à partir d’un groupe Office 365 existant.  <br/> |Accordez au membre les autorisations d'un propriétaire de groupe. <br/> |14/01/20  <br/>|




|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Onglet OneNote existant  <br/> |Les onglets OneNote existants créés lors de la préversion publique de Microsoft Teams ne peuvent pas être renommés ni supprimés.  <br/> |Aucune solution. <br/> |08/11/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Fonction recherche dans l’onglet liste SharePoint  <br/> |Essayer d’ouvrir un fichier à partir de la fonction recherche de l’onglet liste SharePoint fait afficher une invite « Vous avez besoin d’une nouvelle application pour ouvrir ce fichier » et le fichier ne sera pas ouvert. <br/> |Ouvrir directement à partir de liste plutôt que de la barre de recherche. <br/> |11/2/2019  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Échec du téléchargement d’un fichier <br/> |Toute tentative de téléchargement d’un fichier lorsque le chemin d’accès à un fichier contient une apostrophe se solde en un échec avec affichage du message «Le fichier n’a pas été téléchargé» lors de l’utilisation du client de bureau Microsoft Teams. <br/> |Téléchargez le fichier à partir du client Web ou de SharePoint Online <br/> |10/5/2019  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Impossible de charger ou de télécharger un fichier OneNote <br/> |La tentative de chargement ou de téléchargement d’un fichier ou d’un bloc-notes OneNote échouera en utilisant Microsoft Teams. <br/> |Charger ou télécharger le fichier directement dans SharePoint Online <br/> |7/5/2019  <br/> |

## <a name="teams"></a>Équipes

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les e-mails de messages vocaux Teams sont transmis avec l’échec SPF s’il s’agit d’un appel SIP, s’il s’agit d’un appel PSTN pour un utilisateur, il sont transmis avec l’attribut « de » sans la valeur correcte, si le client a une règle dans laquelle il analyse les messages vocaux SPF, l’action de l’ETR décide. <br/> | <br/> | La solution de contournement du 29/08/2019 ajoute une exception dans la ETR si le message est une messagerie vocale.


|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Le chargement de photos dans Teams n'est pas bloqué dans OWA/Outlook comme le requiert la stratégie   <br/> | Teams permet aux utilisateurs de charger des photos directement dans Office 365, en dépit des paramètres de stratégie définis pour empêcher cette action dans OWA.   <br/> |<br/>  |16/10/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La liste d'équipes publiques n'affiche pas toutes les équipes  <br/> |La liste des équipes publiques repose sur Microsoft Graph.  <br/> |Si une équipe n'est pas affichée, essayez de la rechercher au moyen du champ de recherche situé dans le coin supérieur droit. Les propriétaires d’équipe doivent en outre communiquer les noms des équipes à leurs collègues, plusieurs équipes peuvent s’afficher dans les résultats de recherche. <br/> | 21/07/2017  <br/>|

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Les noms d’équipes contenant des caractères spéciaux peuvent créer des erreurs lors de la création de réunions  <br/> |L’utilisateur recevra le message **Une erreur s’est produite** en rouge s’il tente de créer une réunion pour une équipe dont le nom contient des caractères spéciaux.   <br/> |Renommez ou créez à nouveau l’équipe avec un nom qui ne contient pas le caractère « / ».  <br/> |13/07/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Maximum de 5000 membres par équipe  <br/> |Chaque équipe Microsoft Team peut accueillir un maximum de 5000 membres.  <br/> |Aucune solution.  <br/> |6/2/2019  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|La suppression d'une équipe supprime également le groupe associé à celle-ci  <br/> |Il est possible que les utilisateurs ne réalisent pas que le groupe Office 365 sous-jacent est supprimé lorsque l'équipe est supprimée. En outre, si le groupe Office 365 sous-jacent est supprimé, l'équipe l'est également.  <br/> |Les langues supplémentaire dans Microsoft Teams fournissent cette information à l'utilisateur. Cette information n'est pas disponible dans l'interface Groupes Office 365. Votre service d’assistance peut récupérer un groupe ou une équipe supprimé(e).  <br/> |13/03/2017  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Application de bureau Teams affichant un écran blanc  <br/> | <br/> |Essayez de supprimer ou de réinstaller les pilotes graphiques sur l’ordinateur, ou démarrez Teams depuis une ligne de commande avec un indicateur de désactivation du GPU :<ul><li>Pour Windows : ouvrez l'invite de commande et entrez la commande suivante : `cd %localappdata%\microsoft\teams\current run Teams.exe --disable-gpu`</li><li>Pour Mac : démarrez le Terminal et entrez la commande suivante : `cd \Applications folder Microsoft\ Teams.app/Contents/MacOS/Teams --disable-gpu`</li></ul> <br/> |<br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|L’utilisateur ne reçoit pas d’e-mail de bienvenue lorsqu’il est ajouté par l’administrateur.  <br/> |Lors de l’ajout d’un membre à une équipe à l’aide de PowerShell ou du centre d’administration Teams, le membre ne reçoit pas d’e-mail de bienvenue de Microsoft Teams.  <br/> |L’ajout d’un membre directement à partir de l’interface utilisateur de Teams entraîne l’envoi d’un e-mail. Actuellement, il n’existe aucun contournement permettant de réaliser cette action via l’administration.  <br/> |12/02/19  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Problème d’interopérabilité entre Symantec DLP et Teams <br/> |Les agents Symantec DLP Endpoint peuvent interférer avec le processus Teams, ce qui peut entraîner une défaillance au lancement ou à la sortie.  <br/> |Excluez (mettez en liste verte) Teams.exe à partir des agents Endpoint de Symantec DLP, comme décrit dans cet <a href="https://support.symantec.com/us/en/article.TECH220322.html">article du support technique de Symantec</a>. <br/> |15/07/2019  <br/> |

|**Intitulé du problème**|**Comportement / Symptôme**|**Solution**|**Date de découverte**|
|:-----|:-----|:-----|:-----|
|Le chiffrement Dell peut empêcher le lancement de Teams <br/> |Le chiffrement Dell (précédemment Chiffrement de protection des données Dell) peut altérer l’installation de Teams durant le processus de mise à jour, ce qui entraîne un échec permanent lors du lancement de l’application. <br/> |Exclure le dossier Teams sur %LocalAppData%\Microsoft\Teams à partir de la stratégie de chiffrement. <br/> |21/11/19  <br/> |
