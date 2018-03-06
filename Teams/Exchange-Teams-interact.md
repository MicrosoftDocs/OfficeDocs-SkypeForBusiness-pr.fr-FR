---
title: "Interaction entre Exchange et Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: "Découvrez les fonctionnalités communes entre Microsoft Teams et les différentes configurations d'Exchange, telles que la création et l'adhésion à des équipes, la création de canaux, et plus encore."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7da92ce791349994474c76fe736a06ddcd67999
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Interaction entre Exchange et Microsoft Teams 
=========================================

Pour profiter pleinement de Microsoft Teams, Exchange Online, SharePoint Online et la création de groupes Office 365 doivent être activés pour chaque utilisateur.

Les boîtes aux lettres Exchange des utilisateurs peuvent être hébergées en ligne ou sur site. Les utilisateurs hébergés sur Exchange Online ou sur vNext Exchange dédié peuvent utiliser toutes les fonctionnalités de Microsoft Teams. Ils peuvent créer et rejoindre des équipes et des canaux, créer et afficher des réunions, participer à des conversations et des appels, modifier les images de profil utilisateur, ajouter et configurer des connecteurs, des onglets et des bots, et participer à des conversations et des appels.

Les utilisateurs hébergés sur Exchange Online dédié (hérité ou sur Exchange sur site) doivent être synchronisés avec Azure Active Directory pour Office 365. Ils peuvent créer et rejoindre des équipes et des canaux, ajouter et configurer des onglets et des bots, et participer à des conversations et des appels. Toutefois, ils ne peuvent pas modifier les images de profil utilisateur ni ajouter et configurer des connecteurs. Ils peuvent recevoir des messages à partir de connecteurs configurés par d'autres utilisateurs. Concernant la création et l’affichage de réunions, cela dépend : ces fonctionnalités sont prises en charge dans la mise à jour cumulative 3 (CU3) d’Exchange 2016, mais pas dans les versions antérieures à Exchange 2016 CU3.

Le tableau suivant fournit des informations aux utilisateurs pour lesquels Exchange Online est hébergé dans différents environnements.

**Actions prises en charge :** 

| La boîte aux lettres de l'utilisateur est hébergée dans :   | Créer des équipes   |Rejoindre des équipes|Créer des canaux|Créer et afficher des réunions|Modifier une image de profil utilisateur|Ajouter et configurer des connecteurs|Ajouter et configurer des onglets|Ajouter et configurer des bots|
|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|
|**vNext Exchange Online dédié**|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|
|**Exchange Online dédié– hérité** (Synchronisation avec Azure AD requise)|Oui|Oui|Oui|Non|Non|Non|Oui| Oui|
|**Exchange sur site** (Synchronisation avec Azure AD requise)|Oui|Oui|Oui|Oui*|Non|Non|Oui|Oui|
                                                            
*\*Prise en charge d'Exchange 2016 CU3 et versions ultérieures*

Informations complémentaires :

-   Microsoft Teams ne prend pas en charge SharePoint sur site.

-   SharePoint Online est requis pour le partage et le stockage de fichiers dans les conversations d'équipe.

-   OneDrive Entreprise est requis pour le partage et le stockage de fichiers dans les conversations privées.

-   Si des licences SharePoint Online ne sont pas activées et affectées aux utilisateurs, ils ne disposeront pas du stockage OneDrive Entreprise dans Office 365. Le partage de fichiers continuera de fonctionner dans les canaux, mais les utilisateurs ne seront pas en mesure de partager de fichier dans les conversations sans le stockage OneDrive Entreprise dans Office 365.

-   La création de groupe Office 365 doit être activée pour permettre aux utilisateurs de créer des équipes dans Microsoft Teams.

-   Dans Microsoft Teams, les fonctions de sécurité et de conformité, telles que eDiscovery, la recherche de contenu, l'archivage et la conservation légale sont plus efficaces dans les environnements Exchange Online et SharePoint Online. Dans le cas de conversations de canal, les messages sont journalisés dans la boîte aux lettres du groupe dans Exchange Online et peuvent être utilisés par eDiscovery. Si SharePoint Online et OneDrive Entreprise (avec un compte professionnel ou scolaire) sont activés pour les utilisateurs dans l'organisation, ces fonctionnalités de conformité sont également disponibles pour l'ensemble des fichiers dans Teams.

**Important :**   les utilisateurs participant à des conversations figurant dans la liste de conversations dans Microsoft Teams doivent disposer d'une boîte aux lettres Exchange Online (dans le cloud) pour permettre à l'administrateur de rechercher des conversations. Cela est dû au fait que les conversations figurant dans la liste de conversations sont stockées dans les boîtes aux lettres basées sur le cloud des participants aux conversations. Si un participant à une conversation n'a pas de boîte aux lettres Exchange Online, l'administrateur ne pourra pas rechercher ni placer des conversations en conservation. Par exemple, dans un déploiement hybride Exchange, les utilisateurs disposant de boîtes aux lettres sur site peuvent participer à des conversations figurant dans la liste de conversations dans Microsoft Teams. Toutefois dans ce cas, le contenu de ces conversations ne peut pas faire l'objet de recherche ni être placé en conservation, car les utilisateurs ne disposent pas de boîte aux lettres basée sur le cloud. Pour plus d'informations sur la recherche de contenu et Microsoft Teams, reportez-vous à l'article [Effectuer une recherche de contenu dans le Centre de sécurité et de conformité d’Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

**Conseil :**   Pour obtenir des informations sur l'utilisation d'Azure AD Connect à des fins de synchronisation avec Azure Active Directory, reportez-vous à l'article [*Intégrer des répertoires locaux à Azure Active Directory*](https://go.microsoft.com/fwlink/?linkid=854600).
