---
title: Interaction entre Exchange et Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dstrome
description: Découvrez les fonctionnalités communes entre Microsoft Teams et les différentes configurations d'Exchange, telles que la création et l'adhésion à des équipes, la création de canaux, et plus encore.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcdb6a687875aeab39585b44a8f6a9d3b6652b48
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108643"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Interaction entre Exchange et Microsoft Teams 
=========================================

> [!Tip]
> Regarder la session suivante pour savoir comment les équipes interagit avec Azure Active Directory (DAS), groupes d’Office 365, Exchange, SharePoint et OneDrive for Business : [Notions de base sur les équipes de Microsoft](https://aka.ms/teams-foundations)

Pour profiter pleinement de Teams, Exchange Online, SharePoint Online et la création de groupes Office 365 doivent être activés pour chaque utilisateur.

Les boîtes aux lettres Exchange des utilisateurs peuvent être hébergées en ligne ou sur site. Les utilisateurs hébergés sur Exchange Online ou sur vNext Exchange dédié peuvent utiliser toutes les fonctionnalités de Microsoft Teams. Ils peuvent créer et rejoindre des équipes et des canaux, créer et afficher des réunions, participer à des conversations et des appels, modifier les images de profil utilisateur, ajouter et configurer des connecteurs, des onglets et des bots, et participer à des conversations et des appels.

Les utilisateurs hébergés sur Exchange Online dédié (hérité ou sur Exchange sur site) doivent être synchronisés avec Azure Active Directory pour Office 365. Ils peuvent créer et rejoindre des équipes et des canaux, ajouter et configurer des onglets et des bots, et participer à des conversations et des appels. Toutefois, ils ne peuvent pas modifier les images de profil utilisateur ni ajouter et configurer des connecteurs. Ils peuvent recevoir des messages à partir de connecteurs configurés par d'autres utilisateurs. Concernant la création et l’affichage de réunions, cela dépend : ces fonctionnalités sont prises en charge dans la mise à jour cumulative 3 (CU3) d’Exchange 2016, mais pas dans les versions antérieures à Exchange 2016 CU3.

Le tableau suivant fournit des informations aux utilisateurs pour lesquels Exchange Online est hébergé dans différents environnements.

**Actions prises en charge :** 

| La boîte aux lettres de l'utilisateur est hébergée dans : | eDiscovery| Juridique&nbsp;attente | Rétention| Gestion de l’équipe et de canal |Créer et afficher des réunions| Modifier une image de profil utilisateur | Historique des appels | Gérer des Contacts | Accéder aux contacts Outlook | Messagerie vocale |Ajouter et configurer des connecteurs|Ajouter et configurer des onglets|Ajouter et configurer des bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Oui <sup>2</sup>|Oui <sup>2</sup>|Oui |Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui |Oui|
|**vNext Exchange Online dédié**|Oui <sup>2</sup>|Oui <sup>2</sup>|Oui |Oui |Oui|Oui|Oui |Oui|Oui|Oui|Oui |Oui |Oui|
|**Exchange Online dédié– hérité** (Synchronisation avec Azure AD requise)|Oui <sup>2</sup>|Oui <sup>2,3</sup>|Oui <sup>4|Oui|Non|Non|Oui|Oui|Non|Oui <sup>5|Oui |Oui |Oui|
|**Exchange sur site** (Synchronisation avec Azure AD requise)|Oui <sup>2</sup>| Oui <sup>2,3</sup> |Oui <sup>4|Oui|Oui (Exchange 2016 CU3 +)|Oui (Exchange 2016 CU3 +)|Oui |Oui|Non|Oui <sup>5|Oui |Oui |Oui|

<sup>1</sup> exchange CU3 2016 et ci-dessus pris en charge  
<sup>2</sup> eDiscovery et juridiques pour la conformité des messages de canal est pris en charge pour toutes les options d’hébergement.  
<sup>3</sup> messages de conversation privée d’équipes ne sont pas encore pris en charge pour suspens pour raisons juridiques pour cette option d’hébergement.

<sup>4</sup> rétention utilise une boîte aux lettres de l’ombre pour l’utilisateur en ligne pour stocker des messages. [Prend en charge des équipes Microsoft eDiscovery pour l’utilisateur d’équipes dans un environnement Exchange hybride](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> utilisateurs équipes avec sur site de boîte aux lettres Exchange peut utiliser la messagerie vocale avec des équipes et recevoir des messages de messagerie vocale dans Outlook, mais les messages vocaux ne sera pas disponibles pour afficher ou lire dans le client d’équipes.

Informations complémentaires :

-   Microsoft Teams ne prend pas en charge SharePoint sur site.

-   SharePoint Online est requis pour le partage et le stockage de fichiers dans les conversations d'équipe.

-   OneDrive Entreprise est requis pour le partage et le stockage de fichiers dans les conversations privées.

-   Si des licences SharePoint Online ne sont pas activées et affectées aux utilisateurs, ils ne disposeront pas du stockage OneDrive Entreprise dans Office 365. Le partage de fichiers continuera de fonctionner dans les canaux, mais les utilisateurs ne seront pas en mesure de partager de fichier dans les conversations sans le stockage OneDrive Entreprise dans Office 365.

-   La création de groupe Office 365 doit être activée pour permettre aux utilisateurs de créer des équipes dans Microsoft Teams.

-   Dans Microsoft Teams, les fonctions de sécurité et de conformité, telles que eDiscovery, la recherche de contenu, l'archivage et la conservation légale sont plus efficaces dans les environnements Exchange Online et SharePoint Online. Dans le cas de conversations de canal, les messages sont journalisés dans la boîte aux lettres du groupe dans Exchange Online et peuvent être utilisés par eDiscovery. Si SharePoint Online et OneDrive Entreprise (avec un compte professionnel ou scolaire) sont activés pour les utilisateurs dans l'organisation, ces fonctionnalités de conformité sont également disponibles pour l'ensemble des fichiers dans Teams.

-   Pour Exchange local, vous devez configurer le nouveau protocole d’authentification OAuth Exchange comme décrit dans [l’authentification OAuth configurer entre des organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). 

-  Contrôler et protéger la configuration des stratégies de conformité dans Exchange à l’aide d’accès conditionnel et les équipes. Pour plus d’informations, voir [comment fonctionnent les stratégies d’accès conditionnel pour les équipes ?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

> [!NOTE]
> Actuellement, si votre organisation a des exigences de conformité exigeant que toutes les discussions en réunion puissent être découvertes, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres sur site Exchange.
> 
> [!IMPORTANT]
> Dans un déploiement Exchange hybride, le contenu des messages de conversation est consultable que participants conversation disposent d’une boîte aux lettres en nuage ou une boîte aux lettres locale. Pour plus d’informations, consultez [recherche basée sur le cloud boîtes aux lettres pour les utilisateurs locaux dans Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Pour en savoir plus sur la recherche de contenu dans les équipes, lisez la [Recherche de contenu dans le centre de conformité de & Office 365 sécurité](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).
> 
> [!TIP]
> Pour plus d’informations sur l’utilisation d’Azure AD se connecter à synchroniser avec Azure Active Directory, voir [intégration des identités avec Azure Active Directory local](https://go.microsoft.com/fwlink/?linkid=854600).
