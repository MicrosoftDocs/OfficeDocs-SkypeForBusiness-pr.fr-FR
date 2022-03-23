---
title: Interaction entre Exchange et Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Découvrez les fonctionnalités communes entre Microsoft Teams et les différentes configurations d'Exchange, telles que la création et l'adhésion à des équipes, la création de canaux, et plus encore.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1ade306ab1a9dc3c3f716b36d931bcf7a6d0b41
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711498"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaction entre Exchange et Microsoft Teams

> [!Tip]
> Visionnez la session suivante pour découvrir comment Microsoft Teams interagit avec Azure Active Directory (AAD), les groupes Microsoft 365, Exchange, SharePoint and OneDrive Entreprise : [Fondements de Microsoft Teams](https://aka.ms/teams-foundations)

Pour profiter pleinement de Teams, Exchange Online, SharePoint Online et la création de groupes Microsoft 365 doivent être activés pour chaque utilisateur.

Vous pouvez héberger les boîtes aux lettres Exchange des utilisateurs en localement ou en ligne.

Les utilisateurs hébergés sur Exchange Online ou Exchange vNext dédié peuvent utiliser toutes les fonctionnalités de Teams. Ils peuvent créer et rejoindre des équipes et des canaux, créer et afficher des réunions, appeler et converser, modifier des photos de profil utilisateur (si la stratégie de boîte aux lettres d’Outlook sur le web les autorise à le faire), et ajouter et configurer des connecteurs, onglets et bots. Pour une liste plus complète des fonctionnalités disponibles, consultez le tableau ci-dessous.

Les utilisateurs hébergés sur Exchange Online dédié (hérité) doivent être synchronisés avec Azure Active Directory sur Microsoft 365 ou Office 365. Ils peuvent créer et rejoindre des équipes et des canaux, ajouter et configurer des onglets et des bots et utiliser les fonctionnalités d’appel et de conversation. Toutefois, ils ne peuvent pas modifier des photos de profil, gérer des réunions, accéder aux contacts ou gérer des connecteurs.

> [!IMPORTANT]
> Pour l’intégration locale, vous vous recommandons vivement d’effectuer un déploiement Exchange hybride classique complet avec Exchange Server 2016 ou version ultérieure. La prise en charge hybride moderne est limitée à Libre/Occupé et ne fournit pas l’intégration de calendrier de Teams vers des boîtes aux lettres locales, par exemple. Pour plus d'informations sur la configuration d'un déploiement hybride, consultez la rubrique [Déploiements hybrides Exchange Server](/exchange/exchange-hybrid).

Les utilisateurs ayant des boîtes aux lettres hébergées localement doivent être synchronisés avec Azure Active Directory. Ils peuvent utiliser toutes les fonctionnalités indiquées dans le scénario ci-dessus et, en outre, ils peuvent gérer des réunions si les conditions indiquées à la section [Conditions requises pour les boîtes aux lettres hébergées localement](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) sont remplies.

Le tableau suivant fournit un aide-mémoire utile sur la disponibilité de la fonctionnalité dans l’environnement Exchange.

**Actions prises en charge :**

| La boîte aux lettres de l'utilisateur est hébergée dans :                                       | eDiscovery         | Conservation&nbsp;légale    | Rétention        | Gestion des équipes et des canaux | Créer et afficher des réunions dans Teams | Modifier une image de profil utilisateur | Historique des appels | Gestion des contacts | Accès au contacts Outlook | Messagerie vocale        | Ajouter et configurer des connecteurs | Ajouter et configurer des onglets | Ajouter et configurer des bots |
|--------------------------------------------------------------------|--------------------|--------------------|------------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                | Oui <sup>1</sup>   | Oui <sup>1</sup>   | Oui              | Oui                   | Oui                               | Yes<sup>7</sup>             | Oui          | Oui             | Oui <sup>6</sup>        | Oui              | Oui                          | Oui                    | Oui                    |
| **vNext Exchange Online dédié**                                | Oui <sup>1</sup>   | Oui <sup>1</sup>   | Oui              | Oui                   | Oui                               | Yes<sup>7</sup>             | Oui          | Oui             | Oui <sup>6</sup>        | Oui              | Oui                          | Oui                    | Oui                    |
| **Exchange Online dédié– hérité** (Synchronisation avec Azure AD requise) | Oui <sup>1</sup>   | Oui <sup>1,2</sup> | Oui <sup>3</sup> | Oui                   | Non                                | Non                          | Oui          | Oui             | Non                      | Oui<sup>4</sup> | Oui <sup>5</sup>             | Oui                    | Oui                    |
| **Exchange local** (Synchroniser avec Azure AD)                        | Oui <sup>1,9</sup> | Oui <sup>1</sup>   | Oui <sup>3</sup> | Oui                   | Oui <sup>8</sup>                  | <sup>Oui10</sup>            | Oui          | Oui             | Non                      | Oui<sup>4</sup> | Oui <sup>5</sup>             | Oui                    | Oui                    |

<sup>1</sup> eDiscovery et la Conservation légale pour la conformité sur des messages de canal sont pris en charge pour toutes les options d’hébergement.

<sup>2</sup> Les messages de conversation privée Teams ne sont pas encore pris en charge pour la Conservation légale relative à cette option d’hébergement.

<sup>3</sup> La rétention utilise une boîte aux lettres cachée pour l’utilisateur en ligne afin de stocker des messages.

<sup>4</sup> Les utilisateurs Teams ayant une boîte aux lettres Exchange locale peuvent utiliser la messagerie vocale avec Teams et recevoir les messages vocaux dans Outlook, mais les messages vocaux ne seront pas disponibles pour l’affichage ou la lecture dans le client Teams.

<sup>5</sup> Si l’un des propriétaires d’une équipe peut ajouter des connecteurs, les membres de cette équipe pourront également le faire, même si leur boîte aux lettres est hébergée localement.

<sup>6</sup> Seul les contacts dans le dossier des contacts par défaut. L’accès aux autres dossiers et sous-dossiers de contacts n’est pas pris en charge.

<sup>7</sup> Teams respecte le paramètre [Stratégie de boîte aux lettres Outlook sur le web](/powershell/module/exchange/client-access/set-owamailboxpolicy) qui est configuré par les administrateurs de clients pour contrôler si les utilisateurs peuvent modifier leur photo de profil. Si le paramètre **-SetPhotoEnabled** est désactivé dans la stratégie, les utilisateurs ne peuvent pas ajouter, modifier ou supprimer leur image de profil, de sorte que l’image de profil ne sera pas synchronisée avec les équipes si l’administrateur modifie la photo.

<sup>8</sup> Vous devez remplir les conditions énumérées dans la section [Configuration requise pour créer et afficher des réunions pour les boîtes aux lettres hébergées localement](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises).

<sup>9</sup> Au minimum, une licence Exchange Online plan 1 est également requise. Pour plus d’informations, [voir Rechercher des Teams conversation instantanée pour les utilisateurs locaux](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users).

<sup>10</sup> utilisateurs `SetPhotoEnabled` locaux peuvent utiliser des Teams pour mettre à jour leur image de profil, même si la Outlook de la stratégie de boîte aux lettres web est définie sur `false`.
 > [!NOTE]
 > La définition d’absence du Office via le client Teams n’est actuellement pas prise en charge pour les utilisateurs dont les boîtes aux lettres sont hébergées en local. Ces utilisateurs doivent effectuer cette action via le client Outlook client.
## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Configuration requise pour tirer le meilleur parti de Microsoft Teams

Microsoft Teams est compatible avec plusieurs services Microsoft 365 et Office 365 pour enrichir l’expérience des utilisateurs. Pour la prise en charge de cette expérience, vous devez activer certaines fonctionnalités ou services et attribuer des licences.

- Vous devez attribuer une licence Exchange Online aux utilisateurs.

- SharePoint Online est requis pour le partage et le stockage de fichiers dans les conversations d'équipe. Microsoft Teams ne prend pas en charge SharePoint local.

- Une licence SharePoint Online doit être attribuée au utilisateurs qui veulent partager des fichiers dans les Conversations. Si des licences SharePoint Online ne sont pas affectées et activées pour les utilisateurs, ceux-ci ne disposent pas d'un stockage OneDrive Entreprise dans Microsoft 365 ou Office 365. Le partage de fichiers continue à fonctionner dans des canaux, mais les utilisateurs ne peuvent pas partager des fichiers dans les Conversation sans stockage OneDrive Entreprise dans Microsoft 365 ou Office 365.

- La création de groupe Microsoft 365 doit être activée pour permettre aux utilisateurs de créer des équipes dans Microsoft Teams.

  > [!IMPORTANT]
  > Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence peut cesser de fonctionner dans Outlook et d’autres applications Office. La présence fonctionne correctement dans Teams. Pour résoudre ce problème, sélectionnez votre photo de profil dans le coin supérieur droit de Microsoft Teams, puis **Paramètres**. Sur l’onglet **Général** sous **Application**, sélectionnez **Enregistrer Teams comme application de conversation pour Office (redémarrage des applications Office requis)**. Après la section de cette option, fermez puis rouvrez toutes les applications Office, y compris Outlook. Une fois Outlook ouvert, les informations de présence sont disponible.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Conditions préalables pour créer et afficher les réunions pour les boîtes aux lettres hébergées localement

Si les boîtes aux lettres sont hébergées localement, pour créer et afficher les réunions, vous devez respecter les exigences suivantes :

- La licence Teams requise doit être attribuée à l’utilisateur synchronisé Azure Active Directory.

- Les utilisateurs doivent être synchronisés avec Azure Active Directory. Pour obtenir des informations sur l'utilisation d'Azure AD Connect à des fins de synchronisation avec Azure Active Directory, voir [Documentation des identités hybrides](/azure/active-directory/hybrid/).

- Les boîtes aux lettres sont hébergées dans Exchange Server 2016 Mise à jour cumulative 3 ou ultérieure.

- Les services de découverte automatique et web Exchange sont publiés de manière externe.

- L’authentification OAuth est de préférence configurée via l’Assistant de configuration hybride Exchange exécutant une configuration hybride complète (Classique ou Moderne). Si vous ne pouvez pas utiliser l’Assistant de configuration hybride, configurez OAuth tel que décrit dans [Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  > [!NOTE]
  > Exchange fait confiance au jeton OAuth du service Teams qui est appelé EvoSTS. L’étape 1 doit être suffisante, mais seulement l’EvoSTS ; ACS est utilisé pour la recherche Libre/Occupé dans le calendrier.

- La case à cocher dans la fonctionnalité de déploiement hybride Exchange dans Azure AD Connect est configurée. Pour plus d’informations, voir [Exchange écriture hybride](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#exchange-hybrid-writeback).

- Pour la prise en charge de l’application calendrier et du complément Outlook Teams pour Mac, les URL du service web Exchange doivent être configurées en tant que SPN dans le client Azure AD pour le principal de service Exchange. Cette est effectuée avec l’Assistant de configuration hybride ou en suivant [les étapes manuelles pour l’authentification moderne hybride](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Pour activer la délégation de calendrier pour ces utilisateurs :

- Vous devez également effectuer les étapes décrites dans configurer l’intégration et [l’auth entre Skype Entreprise Online et Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) ; ces étapes fournissent à l’application de planification Teams les autorisations requises pour confirmer les autorisations accordées aux délégués.
 
  > [!NOTE]
  > L’étape 2 inclut l’attribution de rôles pour ArchiveApplication, laquelle n’est pas requise pour la délégation.

- Le Teams planification de réunion pour Outlook nécessite Exchange 2013 CU19 ou une date ultérieure lors de la planification d’une réunion au nom d’une autre personne. Cela permet la prise en charge de la découverte d’une boîte aux lettres non authentifiée par notre service pour vérifier les autorisations déléguées par rapport à la boîte aux lettres de délégation. L’emplacement du délégué et de la délégation peut être Exchange 2013 ou version ultérieure, ou Exchange Online, mais la découverte automatique doit correspondre à Exchange 2013 CU19 ou version ultérieure.

## <a name="additional-considerations"></a>Considérations supplémentaires

Voice quelques éléments supplémentaires à considérer lorsque vous implémentez Microsoft Teams dans votre organisation.

- Dans Microsoft Teams, les fonctions de sécurité et de conformité, telles que eDiscovery, la recherche de contenu, l'archivage et la conservation légale sont plus efficaces dans les environnements Exchange Online et SharePoint Online. Dans le cas de conversations de canal, les messages sont journalisés dans la boîte aux lettres du groupe dans Exchange Online et peuvent être utilisés par eDiscovery. Si SharePoint Online et OneDrive Entreprise (avec un compte professionnel ou scolaire) sont activés pour les utilisateurs dans l'organisation, ces fonctionnalités de conformité sont également disponibles pour l'ensemble des fichiers dans Teams.

- Elles contrôlent et protègent la configuration des stratégies de conformité dans Teams et Exchange en utilisant l’accès conditionnel. Pour plus d’informations, voir [Comment fonctionnent les stratégies d’accès conditionnel pour Teams ?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- Si votre organisation a des exigences en matière de conformité pour s’assurer que toutes les discussions en réunion puissent être découvertes, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres Exchange locale. Pour plus d’informations, [voir Private meeting scheduling (Planification de réunion privée](./meeting-policies-in-teams-general.md#private-meeting-scheduling)).

- Dans un déploiement hybride Exchange, le contenu des messages de conversation est interrogeable, que les participants à la conversation aient une boîte aux lettres basée dans le cloud ou une boîte aux lettres locale. Pour en savoir plus, lire [Recherche de boîtes aux lettres sur le cloud des utilisateurs locaux](/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Pour découvrir le recherche de contenu dans Teams, lire [Recherche de contenu dans le Centre de conformité Microsoft 365](/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

- Pour l’état de présence, Microsoft Teams doit vérifier si la boîte aux lettres est hébergée sur Exchange Online ou localement. Le service décide alors de l’emplacement d’accès pour la boîte aux lettres. Pour activer le service Teams afin de vérifier l’emplacement de la boîte aux lettres au moyen d’un appel de l’API REST API au service Exchange Online, vous devez déployer un environnement Exchange hybride en exécutant l’Assistant de configuration Exchange hybride, tel que décrit dans [Créer un déploiement hybride avec l’Assistant de configuration hybride](/exchange/hybrid-deployment/deploy-hybrid).

## <a name="troubleshooting"></a>Résolution des problèmes

Pour obtenir le guide complet de résolution des problèmes sur ce thème, n’oubliez pas de consulter [Résoudre les problèmes d’interaction entre Microsoft Teams et Exchange Server](/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
