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
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42d15f32cbdf7326ea8daf85860bd451d93ed3f3
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434650"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaction entre Exchange et Microsoft Teams

> [!Tip]
> Regardez la session suivante pour découvrir comment les équipes interagissent avec Azure Active Directory (AAD), les groupes Office 365, Exchange, SharePoint et OneDrive entreprise : [notions de bases de Microsoft teams](https://aka.ms/teams-foundations)

Pour profiter pleinement de Teams, Exchange Online, SharePoint Online et la création de groupes Office 365 doivent être activés pour chaque utilisateur.

Les boîtes aux lettres Exchange des utilisateurs peuvent être hébergées en ligne ou sur site. Toutefois, certaines fonctionnalités nécessitent un déploiement hybride qui est en place avec votre client Office 365.

Les utilisateurs hébergés sur Exchange Online ou Exchange dédié vNext peuvent utiliser toutes les fonctionnalités d’Teams. Ils peuvent créer et rejoindre des équipes et des canaux, créer et afficher des réunions, appeler et discuter, modifier des images de profil utilisateur, et ajouter et configurer des connecteurs, des onglets et des robots.

Les utilisateurs hébergés sur Exchange Online dédié (hérité) doivent être synchronisés avec Azure Active Directory sur Office 365. Ils peuvent créer et rejoindre des équipes et des canaux, ajouter et configurer des onglets et des robots, et utiliser les fonctionnalités de conversation et d’appel. Toutefois, ils ne peuvent pas modifier les images de profil, gérer les réunions, accéder aux contacts Outlook ou gérer les connecteurs.

Les utilisateurs dotés de boîtes aux lettres hébergées sur site doivent être synchronisés avec Azure Active Directory. Ils peuvent utiliser toutes les fonctionnalités du scénario ci-dessus, mais ils peuvent également modifier l’image de profil utilisateur et gérer les réunions, en fournissant Exchange Server 2016 (mise à jour cumulative 3) ou une version ultérieure.

Le tableau suivant fournit une référence rapide utile à la disponibilité des fonctionnalités en fonction de l’environnement Exchange.


**Actions prises en charge :**

| La boîte aux lettres de l'utilisateur est hébergée dans : | eDiscovery| Conservation&nbsp;légale | Rétention| Gestion des équipes et des canaux |Créer et afficher des réunions| Modifier une image de profil utilisateur | Historique des appels | Gérer les contacts | Accéder aux contacts Outlook | Messagerie vocale |Ajouter et configurer des connecteurs|Ajouter et configurer des onglets|Ajouter et configurer des bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Oui <sup>2</sup>|Oui <sup>2</sup>|Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui|
|**vNext Exchange Online dédié**|Oui <sup>2</sup>|Oui <sup>2</sup>|Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui |Oui|
|**Exchange Online dédié– hérité** (Synchronisation avec Azure AD requise)|Oui <sup>2</sup>|Oui <sup>, 3</sup>|Oui <sup>, 4|Oui|Non|Non|Oui|Oui|Non|Oui <sup>, 5|Oui <sup>, 6|Oui |Oui|
|**Exchange sur site** (synchronisation avec Azure ad requise)|Oui <sup>2</sup>| Oui <sup>, 3</sup> |Oui <sup>, 4|Oui|Oui (Exchange 2016 CU3 +)|Oui (Exchange 2016 CU3 +)|Oui |Oui|Non|Oui <sup>, 5|Oui <sup>, 6|Oui |Oui|

<sup>1</sup> Exchange 2016 CU3 et supérieur pris en charge.  

<sup>2</sup> EDiscovery et conservation légale pour la conformité des messages de canal est pris en charge pour toutes les options d’hébergement.

<sup>3</sup> les messages de discussion privée d’équipes ne sont pas encore pris en charge pour cette option d’hébergement.

<sup>4</sup> la rétention utilisera une boîte aux lettres d’ombre pour que l’utilisateur en ligne puisse stocker les messages. [Microsoft teams prend en charge le eDiscovery pour les utilisateurs d’équipes dans un environnement Exchange hybride](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> les utilisateurs teams disposant d’une boîte aux lettres Exchange locale peuvent utiliser la boîte vocale avec teams et recevoir des messages vocaux dans Outlook, mais les messages vocaux ne seront pas disponibles à l’affichage ou à la lecture dans le client Teams.

<sup>6</sup> si l’un des propriétaires d’une équipe peut ajouter des connecteurs, tous les autres membres de cette équipe pourront y parvenir, même si leurs boîtes aux lettres sont hébergées sur site.


Informations complémentaires :

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Configuration requise pour tirer le meilleur parti de Microsoft teams

Microsoft teams fonctionne avec plusieurs services 365 Office pour offrir aux utilisateurs une expérience plus riche. Pour prendre en charge cette fonctionnalité, vous devez activer certains services et fonctionnalités, ainsi qu’affecter des licences.

- SharePoint Online est requis pour le partage et le stockage de fichiers dans les conversations d'équipe. Microsoft Teams ne prend pas en charge SharePoint sur site.

- Une licence SharePoint Online doit être attribuée aux utilisateurs pour pouvoir partager des fichiers dans les conversations. Si les utilisateurs ne sont pas assignés et activés pour les licences SharePoint Online, ils n’ont pas de stockage OneDrive entreprise dans Office 365. Le partage de fichiers continue de fonctionner dans les canaux, mais les utilisateurs ne peuvent pas partager des fichiers dans les conversations sans espace de stockage OneDrive entreprise dans Office 365.

- La création de groupe Office 365 doit être activée pour permettre aux utilisateurs de créer des équipes dans Microsoft Teams.

- Pour permettre à Microsoft teams de fonctionner avec Exchange en local, vous devez configurer le nouveau protocole d’authentification OAuth Exchange comme décrit dans [configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

> [!NOTE]
>Dans le cas d’une intégration Exchange locale ou Teams, la licence requise doit être attribuée à l’utilisateur synchronisé de AAD.

> [!IMPORTANT]
> Si vous désinstallez le client Skype Entreprise après qu'un utilisateur a été déplacé en mode **Teams uniquement**, la présence cesse de fonctionner dans Outlook et les autres applications Office. La présence fonctionne correctement dans Teams. Solution : pour voir la présence dans Outlook (et les autres applications Office), Skype entreprise doit être installé, même si vous exécutez teams en mode **équipes uniquement** . Microsoft est courant du problème et travaille activement au développement d’un correctif.

## <a name="additional-considerations"></a>Autres considérations

Voici quelques éléments supplémentaires à prendre en considération lors de l’implémentation de Microsoft teams au sein de votre organisation.

- Dans Microsoft Teams, les fonctions de sécurité et de conformité, telles que eDiscovery, la recherche de contenu, l'archivage et la conservation légale sont plus efficaces dans les environnements Exchange Online et SharePoint Online. Dans le cas de conversations de canal, les messages sont journalisés dans la boîte aux lettres du groupe dans Exchange Online et peuvent être utilisés par eDiscovery. Si SharePoint Online et OneDrive Entreprise (avec un compte professionnel ou scolaire) sont activés pour les utilisateurs dans l'organisation, ces fonctionnalités de conformité sont également disponibles pour l'ensemble des fichiers dans Teams.

- Contrôle et protection de la configuration des stratégies de conformité dans les équipes et Exchange à l’aide d’un accès conditionnel. Pour plus d’informations, voir [fonctionnement des stratégies d’accès conditionnel pour Microsoft teams ?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Si votre organisation a des exigences en matière de conformité afin de vous assurer que toutes les discussions de réunion soient détectables, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres Exchange locale.

- Dans le cas d’un déploiement hybride Exchange, le contenu des messages instantanés peut être recherché, même si les participants possédant une boîte aux lettres basée sur le Cloud ou une boîte aux lettres locale. Pour en savoir plus, consultez [recherche de boîtes aux lettres dans le Cloud pour les utilisateurs locaux dans Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Pour en savoir plus sur la recherche de contenu dans Microsoft Teams, voir [recherche de contenu dans le centre de sécurité & conformité Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Pour plus d’informations sur l’utilisation d’Azure AD Connect pour synchroniser avec Azure Active Directory, voir [intégration de vos identités locales avec Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
