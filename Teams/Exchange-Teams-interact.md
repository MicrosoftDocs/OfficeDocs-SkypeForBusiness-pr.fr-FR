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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35c020d981fba9827f10753a04b9b5629a9939df
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177204"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaction entre Exchange et Microsoft Teams

> [!Tip]
> Regardez la session suivante pour découvrir comment les équipes interagissent avec Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint et OneDrive entreprise : [notions de bases de Microsoft teams](https://aka.ms/teams-foundations)

Pour une utilisation complète de teams, chaque utilisateur doit être activé pour la création de groupes Exchange Online, SharePoint Online et Microsoft 365.

Les boîtes aux lettres Exchange des utilisateurs peuvent être hébergées en ligne ou sur site.

Les utilisateurs hébergés sur Exchange Online ou Exchange dédié vNext peuvent utiliser toutes les fonctionnalités d’Teams. Ils peuvent créer et rejoindre des équipes et des canaux, créer et afficher des réunions, appeler et discuter, modifier des images de profil utilisateur (si la stratégie de boîte aux lettres Outlook sur le Web le permet) et ajouter et configurer des connecteurs, des onglets et des robots. Pour obtenir la liste complète des fonctionnalités disponibles, consultez le tableau ci-dessous.

Les utilisateurs hébergés sur Exchange Online dédié (hérité) doivent être synchronisés avec Azure Active Directory sur Microsoft 365 ou Office 365. Ils peuvent créer et rejoindre des équipes et des canaux, ajouter et configurer des onglets et des robots, et utiliser les fonctionnalités de conversation et d’appel. Toutefois, ils ne peuvent pas modifier les images de profil, gérer les réunions, accéder aux contacts Outlook ou gérer les connecteurs.

> [!IMPORTANT]
> Dans le cas d’une intégration avec le service local, il est fortement recommandé d’utiliser un déploiement hybride classique Exchange avec Exchange Server 2016 ou une version ultérieure. La prise en charge hybride moderne est limitée à la disponibilité et ne permettra pas de l’intégration du calendrier d’équipes aux boîtes aux lettres locales, par exemple. Pour plus d’informations sur la configuration d’un déploiement hybride, voir [déploiements hybrides Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid).

Les utilisateurs dotés de boîtes aux lettres hébergées sur site doivent être synchronisés avec Azure Active Directory. Ils peuvent utiliser toutes les fonctionnalités du scénario ci-dessus, mais ils peuvent également gérer les réunions si les exigences indiquées dans la section [conditions requises pour les boîtes aux lettres hébergées sur site](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) sont satisfaites.

Le tableau suivant fournit une référence rapide utile à la disponibilité des fonctionnalités en fonction de l’environnement Exchange.

**Actions prises en charge :**

| La boîte aux lettres de l'utilisateur est hébergée dans :                                        | eDiscovery       | &nbsp;Conservation légale    | Rétention  | Gestion des équipes et des canaux | Créer et afficher des réunions dans Microsoft teams | Modifier une image de profil utilisateur | Historique des appels | Gérer les contacts | Accéder aux contacts Outlook | Messagerie vocale  | Ajouter et configurer des connecteurs | Ajouter et configurer des onglets | Ajouter et configurer des bots |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Oui <sup>1</sup> | Oui <sup>1</sup>   | Oui        | Oui                   | Oui                               | Oui,<sup>7</sup>             | Oui          | Oui             | Oui, <sup>6</sup>        | Oui        | Oui                          | Oui                    | Oui                    |
| **vNext Exchange Online dédié**                                 | Oui <sup>1</sup> | Oui <sup>1</sup>   | Oui        | Oui                   | Oui                               | Oui,<sup>7</sup>             | Oui          | Oui             | Oui, <sup>6</sup>        | Oui        | Oui                          | Oui                    | Oui                    |
| **Exchange Online dédié– hérité** (Synchronisation avec Azure AD requise)  | Oui <sup>1</sup> | Oui <sup>, 1, 2</sup> | Oui, <sup> 3 | Oui                   | Non                                | Non                          | Oui          | Oui             | Non                      | Oui, <sup> 4 | Oui, <sup> 5                   | Oui                    | Oui                    |
| **Exchange sur site** (synchronisation avec Azure AD) | Oui <sup>1</sup> | Oui <sup>1</sup>   | Oui, <sup>3</sup> | Oui                   | Oui, <sup>8</sup>         | Non                          | Oui          | Oui             | Non                      | Oui, <sup> 4 | Oui, <sup> 5                   | Oui                    | Oui                    |

<sup>1</sup> EDiscovery et conservation légale pour la conformité des messages de canal est pris en charge pour toutes les options d’hébergement.

<sup>2</sup> les messages de discussion privée d’équipes ne sont pas encore pris en charge pour cette option d’hébergement.

<sup>3</sup> la rétention utilisera une boîte aux lettres d’ombre pour que l’utilisateur en ligne puisse stocker les messages.

<sup>4</sup> les utilisateurs de teams disposant d’une boîte aux lettres Exchange locale peuvent utiliser la boîte vocale avec teams et recevoir des messages vocaux dans Outlook, mais les messages vocaux ne seront pas disponibles à l’affichage ou à la lecture dans le client Teams.

<sup>5</sup> si l’un des propriétaires d’une équipe peut ajouter des connecteurs, tous les autres membres de cette équipe pourront le faire, même si leurs boîtes aux lettres sont hébergées sur site.

<sup>6</sup> uniquement les contacts dans le dossier contacts par défaut. L’accès à d’autres dossiers ou sous-dossiers de contacts n’est pas pris en charge.

<sup>7</sup> teams respecte le paramètre de [stratégie de boîte aux lettres Outlook sur le Web](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) configuré par les administrateurs de clients pour contrôler si les utilisateurs peuvent modifier leur image de profil. Si le paramètre **-SetPhotoEnabled** est désactivé dans la stratégie, les utilisateurs ne peuvent pas ajouter, modifier ou supprimer l’image de mon profil. Par exemple, si un utilisateur charge une image de profil approuvée par le service informatique de votre organisation ou son service de ressources humaines, aucune action n’est requise. Toutefois, si un utilisateur télécharge une image inappropriée, modifiez-la selon les stratégies internes de votre organisation.

<sup>8</sup> vous devez respecter les exigences indiquées dans la section [Configuration requise pour créer et afficher des réunions pour les boîtes aux lettres hébergées sur site](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) .

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Configuration requise pour tirer le meilleur parti de Microsoft teams

Microsoft teams fonctionne avec plusieurs services Microsoft 365 et Office 365 pour offrir aux utilisateurs une expérience plus riche. Pour prendre en charge cette fonctionnalité, vous devez activer certains services et fonctionnalités, ainsi qu’affecter des licences.

- Une licence Exchange Online doit être affectée aux utilisateurs.

- SharePoint Online est requis pour le partage et le stockage de fichiers dans les conversations d'équipe. Microsoft Teams ne prend pas en charge SharePoint sur site.

- Une licence SharePoint Online doit être attribuée aux utilisateurs pour pouvoir partager des fichiers dans les conversations. Si les utilisateurs ne sont pas assignés et activés pour les licences SharePoint Online, ils n’ont pas de stockage OneDrive entreprise dans Microsoft 365 ou Office 365. Le partage de fichiers continue de fonctionner dans les canaux, mais les utilisateurs ne peuvent pas partager des fichiers dans les conversations sans espace de stockage OneDrive entreprise dans Microsoft 365 ou Office 365.

- Pour créer des équipes dans Microsoft Teams, les utilisateurs doivent être activés pour la création de groupes Microsoft 365.

> [!IMPORTANT]
> Si vous désinstallez le client Skype entreprise après le déplacement d’un utilisateur en mode **équipes uniquement** , il est possible que la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams. Pour résoudre ce problème, sélectionnez votre image de profil dans le coin supérieur droit de Microsoft Teams, puis sélectionnez **paramètres**. Sous l’onglet **général** , sous **application**, sélectionnez **inscrire les équipes en tant qu’application de conversation pour Office (nécessite le redémarrage des applications Office)**. Après avoir sélectionné cette option, fermez et rouvrez toutes les applications Office, y compris Outlook. Lorsque vous ouvrez Outlook, les informations de présence sont disponibles.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Conditions requises pour créer et afficher des réunions pour des boîtes aux lettres hébergées sur site

Si les boîtes aux lettres sont hébergées en local, pour créer et afficher des réunions, les conditions suivantes doivent être remplies :

- La licence requise teams doit être attribuée à l’utilisateur de la synchronisation Azure Active Directory.

- Les utilisateurs doivent être synchronisés avec Azure Active Directory. Pour plus d’informations sur l’utilisation d’Azure AD Connect pour synchroniser avec Azure Active Directory, voir [documentation d’identité hybride](https://docs.microsoft.com/azure/active-directory/hybrid/).

- Les boîtes aux lettres sont hébergées dans Exchange Server 2016 cumulative Update 3 ou version ultérieure.

- Les services de découverte automatique et de services Web Exchange sont publiés en externe.

- L’authentification OAuth est configurée de préférence par le biais de l’Assistant Configuration hybride Exchange exécutant une configuration hybride complète (classique ou moderne). Si vous ne pouvez pas utiliser l’Assistant Configuration hybride, configurez OAuth comme décrit dans [configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

 > [!NOTE]
 > Exchange approuve le jeton OAuth du service équipes, connu sous le nom de EvoSTS. L’étape 1 doit être suffisamment grande, mais uniquement le EvoSTS ; ACS est utilisé pour la recherche de disponibilité dans le calendrier.

- La case à cocher de la fonctionnalité déploiement hybride Exchange d’Azure AD Connect est définie.

- Pour le support des applications calendrier et le complément Outlook teams pour Mac, les URL du service Web Exchange doivent être configurées en tant que SPN dans Azure AD du client pour le principal du service Exchange. Cette étape est accomplie avec l’Assistant Configuration hybride ou [les étapes manuelles suivantes pour l’authentification moderne hybride](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Pour activer la délégation de calendrier pour ces utilisateurs :

- Vous devez également suivre les étapes 2-3 comme décrit dans la rubrique [configurer l’intégration et OAuth entre Skype entreprise Online et Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises). ces étapes permettent à l’application de planifier des équipes les autorisations requises pour vérifier les autorisations de délégué.
 
 > [!NOTE]
 > Étape 2 inclut l’attribution de rôles pour ArchiveApplication, qui n’est pas nécessaire pour la délégation.

- Le complément planification teams pour Outlook lors de la planification d’une réunion au nom d’une personne nécessite Exchange 2013 CU19 ou une version ultérieure. Cela permet de prendre en charge la découverte non authentifiée de la boîte aux lettres par notre service pour vérifier les autorisations de délégué par rapport à la boîte aux lettres de délégué. L’emplacement délégué et délégué peut être Exchange 2013 ou version ultérieure, ou Exchange Online, mais la découverte automatique doit résoudre vers Exchange 2013 CU19 ou version ultérieure.

## <a name="additional-considerations"></a>Autres considérations

Voici quelques éléments supplémentaires à prendre en considération lors de l’implémentation de Microsoft teams au sein de votre organisation.

- Dans Microsoft Teams, les fonctions de sécurité et de conformité, telles que eDiscovery, la recherche de contenu, l'archivage et la conservation légale sont plus efficaces dans les environnements Exchange Online et SharePoint Online. Dans le cas de conversations de canal, les messages sont journalisés dans la boîte aux lettres du groupe dans Exchange Online et peuvent être utilisés par eDiscovery. Si SharePoint Online et OneDrive Entreprise (avec un compte professionnel ou scolaire) sont activés pour les utilisateurs dans l'organisation, ces fonctionnalités de conformité sont également disponibles pour l'ensemble des fichiers dans Teams.

- Contrôle et protection de la configuration des stratégies de conformité dans les équipes et Exchange à l’aide d’un accès conditionnel. Pour plus d’informations, voir [fonctionnement des stratégies d’accès conditionnel pour Microsoft teams ?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Si votre organisation a des exigences en matière de conformité afin de vous assurer que toutes les discussions de réunion soient détectables, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres Exchange locale. Pour plus d’informations, reportez-vous à [autoriser la planification de réunions privées](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings).

- Dans le cas d’un déploiement hybride Exchange, le contenu des messages instantanés peut être recherché, même si les participants possédant une boîte aux lettres basée sur le Cloud ou une boîte aux lettres locale. Pour en savoir plus, consultez [recherche de boîtes aux lettres sur le nuage pour les utilisateurs locaux](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Pour en savoir plus sur la recherche de contenu dans Microsoft Teams, voir [recherche de contenu dans le centre de conformité Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

## <a name="troubleshooting"></a>Résolution des problèmes

Pour consulter un guide de résolution des problèmes, consultez la rubrique [résoudre les problèmes d’interaction entre Microsoft teams et Exchange Server](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
