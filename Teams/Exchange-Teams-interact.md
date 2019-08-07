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
ms.openlocfilehash: 5bedaee766005787bb7b532f4f5561faf91dd35d
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "35614204"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaction entre Exchange et Microsoft Teams

> [!Tip]
> Regardez la session suivante pour découvrir comment les équipes interagissent avec Azure Active Directory (AAD), les groupes Office 365, Exchange, SharePoint et OneDrive entreprise: [notions de bases de Microsoft teams](https://aka.ms/teams-foundations)

Pour profiter pleinement de Teams, Exchange Online, SharePoint Online et la création de groupes Office 365 doivent être activés pour chaque utilisateur.

Les boîtes aux lettres Exchange des utilisateurs peuvent être hébergées en ligne ou sur site. Les utilisateurs hébergés sur Exchange Online ou sur vNext Exchange dédié peuvent utiliser toutes les fonctionnalités de Microsoft Teams. Ils peuvent créer et rejoindre des équipes et des canaux, créer et afficher des réunions, participer à des conversations et des appels, modifier les images de profil utilisateur, ajouter et configurer des connecteurs, des onglets et des bots, et participer à des conversations et des appels.

Les utilisateurs hébergés sur Exchange Online dédié (hérité ou sur Exchange sur site) doivent être synchronisés avec Azure Active Directory pour Office 365. Ils peuvent créer et rejoindre des équipes et des canaux, ajouter et configurer des onglets et des bots, et participer à des conversations et des appels. Toutefois, ils ne peuvent pas modifier les images de profil utilisateur ni ajouter et configurer des connecteurs. Ils peuvent recevoir des messages à partir de connecteurs configurés par d'autres utilisateurs. Concernant la création et l’affichage de réunions, cela dépend : ces fonctionnalités sont prises en charge dans la mise à jour cumulative 3 (CU3) d’Exchange 2016, mais pas dans les versions antérieures à Exchange 2016 CU3.

Le tableau suivant fournit des informations aux utilisateurs pour lesquels Exchange Online est hébergé dans différents environnements.

**Actions prises en charge :**

| La boîte aux lettres de l'utilisateur est hébergée dans : | eDiscovery| Conservation&nbsp;légale | Rétention| Gestion des équipes et des canaux |Créer et afficher des réunions| Modifier une image de profil utilisateur | Historique des appels | Gérer les contacts | Accéder aux contacts Outlook | Messagerie vocale |Ajouter et configurer des connecteurs|Ajouter et configurer des onglets|Ajouter et configurer des bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Oui <sup>2</sup>|Oui <sup>2</sup>|Oui |Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui |Oui|
|**vNext Exchange Online dédié**|Oui <sup>2</sup>|Oui <sup>2</sup>|Oui |Oui |Oui|Oui|Oui |Oui|Oui|Oui|Oui |Oui |Oui|
|**Exchange Online dédié– hérité** (Synchronisation avec Azure AD requise)|Oui <sup>2</sup>|Oui <sup>, 3</sup>|Oui <sup>, 4|Oui|Non|Non|Oui|Oui|Non|Oui <sup>, 5|Oui |Oui |Oui|
|**Exchange sur site** (Synchronisation avec Azure AD requise)|Oui <sup>2</sup>| Oui <sup>, 3</sup> |Oui <sup>, 4|Oui|Oui (Exchange 2016 CU3 +)|Oui (Exchange 2016 CU3 +)|Oui |Oui|Non|Oui <sup>, 5|Oui |Oui |Oui|

<sup>1</sup> Exchange 2016 CU3 et versions ultérieures prises en charge  
<sup>2</sup> EDiscovery et conservation légale pour la conformité des messages de canal est pris en charge pour toutes les options d’hébergement.  
<sup>3</sup> les messages de discussion privée d’équipes ne sont pas encore pris en charge pour cette option d’hébergement.

<sup>4</sup> la rétention utilisera une boîte aux lettres d’ombre pour que l’utilisateur en ligne puisse stocker les messages. [Microsoft teams prend en charge le eDiscovery pour les utilisateurs d’équipes dans un environnement Exchange hybride](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>cinq</sup> les utilisateurs de teams avec une boîte aux lettres Exchange locale peuvent utiliser la boîte vocale avec teams et recevoir des messages vocaux dans Outlook, mais les messages vocaux ne seront pas disponibles à l’affichage ou à la lecture dans le client Teams.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Configuration requise pour tirer le meilleur parti de Microsoft teams

Microsoft teams fonctionne avec plusieurs services 365 Office pour offrir aux utilisateurs une expérience plus riche. Pour prendre en charge cette fonctionnalité, vous devez activer certains services et fonctionnalités, ainsi qu’affecter des licences.

- SharePoint Online est requis pour le partage et le stockage de fichiers dans les conversations d'équipe. Microsoft Teams ne prend pas en charge SharePoint sur site.

- Une licence SharePoint Online doit être attribuée aux utilisateurs pour pouvoir partager des fichiers dans les conversations. Si les utilisateurs ne sont pas assignés et activés pour les licences SharePoint Online, ils n’ont pas de stockage OneDrive entreprise dans Office 365. Le partage de fichiers continue de fonctionner dans les canaux, mais les utilisateurs ne peuvent pas partager des fichiers dans les conversations sans espace de stockage OneDrive entreprise dans Office 365.

- La création de groupe Office 365 doit être activée pour permettre aux utilisateurs de créer des équipes dans Microsoft Teams.

- Pour permettre à Microsoft teams de fonctionner avec Exchange en local, vous devez configurer le nouveau protocole d’authentification OAuth Exchange comme décrit dans [configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

> [!NOTE]
>Dans le cas d’une intégration Exchange locale ou Teams, la licence requise doit être attribuée à l’utilisateur synchronisé de AAD.

## <a name="additional-considerations"></a>Autres considérations

Voici quelques éléments supplémentaires à prendre en considération lors de l’implémentation de Microsoft teams au sein de votre organisation.

- Dans Microsoft Teams, les fonctions de sécurité et de conformité, telles que eDiscovery, la recherche de contenu, l'archivage et la conservation légale sont plus efficaces dans les environnements Exchange Online et SharePoint Online. Dans le cas de conversations de canal, les messages sont journalisés dans la boîte aux lettres du groupe dans Exchange Online et peuvent être utilisés par eDiscovery. Si SharePoint Online et OneDrive Entreprise (avec un compte professionnel ou scolaire) sont activés pour les utilisateurs dans l'organisation, ces fonctionnalités de conformité sont également disponibles pour l'ensemble des fichiers dans Teams.

- Contrôle et protection de la configuration des stratégies de conformité dans les équipes et Exchange à l’aide d’un accès conditionnel. Pour plus d’informations, voir [fonctionnement des stratégies d’accès conditionnel pour Microsoft teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Si votre organisation a des exigences en matière de conformité afin de vous assurer que toutes les discussions de réunion soient détectables, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres Exchange locale.

- Dans le cas d’un déploiement hybride Exchange, le contenu des messages instantanés peut être recherché, même si les participants possédant une boîte aux lettres basée sur le Cloud ou une boîte aux lettres locale. Pour en savoir plus, consultez [recherche de boîtes aux lettres dans le Cloud pour les utilisateurs locaux dans Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Pour en savoir plus sur la recherche de contenu dans Microsoft Teams, voir [recherche de contenu dans le centre de sécurité & conformité Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Pour plus d’informations sur l’utilisation d’Azure AD Connect pour synchroniser avec Azure Active Directory, voir [intégration de vos identités locales avec Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
