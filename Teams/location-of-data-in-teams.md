---
title: Emplacement des données dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Dans cet article, vous allez découvrir dans quelle région se trouvent les données de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121684"
---
# <a name="location-of-data-in-microsoft-teams"></a>Emplacement des données dans Microsoft Teams

Les données dans Teams se situent dans la région géographique associée à votre organisation Microsoft 365 ou Office 365. Actuellement, Teams prend en charge les régions Australie, Canada, France, Allemagne, Inde, Japon, Afrique du Sud, Corée du Sud, Suisse (y compris le Liechtenstein), Émirats arabes unis, Royaume-Uni, Amériques, APAC et EMEA. 

> [!IMPORTANT]
> Teams propose actuellement la résidence de données en Australie, au Canada, en France, en Allemagne, en Inde, au Japon, aux Émirats arabes unis, au Royaume-Uni, en Corée du Sud, en Afrique du Sud et en Suisse (y compris au Liechtenstein) pour les nouveaux clients uniquement.
> Un nouveau client est défini comme un client dont aucun utilisateur ne s’est encore connecté à Teams. S’agissant des clients existants d’Australie, d’Inde, du Japon et de Corée du Sud, leurs données Teams continueront à être stockées dans la région Asie-Pacifique (APAC). Les clients existants au Canada continueront à conserver les données stockées sur le continent américain. S’agissant des clients existants en France, en Allemagne, au Liechtenstein, aux Émirats arabes unis, au Royaume-Uni, en Afrique du Sud et en Suisse, leurs données continueront à être stockées dans la région Europe, Moyen-Orient et Afrique (EMEA).

## <a name="where-your-teams-data-is-stored"></a>Emplacement de stockage de vos données Teams

Pour savoir quelle région héberge les données de votre client, accédez au [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home) > **Paramètres** > **Profil de l’organisation**. Faites défiler vers le bas jusqu’à **Emplacement des données**.

![Capture d'écran du tableau d’emplacement des données, y compris Teams, dans le Centre d'administration](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Emplacement des données Teams au repos

Vos données Teams sont stockées différemment en fonction du type de contenu. 

![Diagramme montrant les types de contenu Teams et l’emplacement où ils sont stockés au repos](media/location-of-data-storage-at-rest.png)

Pour une discussion approfondie, consultez la [session Ignite Breakout sur l’architecture de Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071).

### <a name="core-teams-customer-data"></a>Données client Teams essentielles

Si votre client est configuré en Australie, au Canada, dans l’Union européenne, en France, en Allemagne, en Inde, au Japon, en Afrique du Sud, en Corée du Sud, en Suisse (y compris au Liechtenstein), aux Émirats arabes unis, au Royaume-Uni et aux États-Unis, Microsoft stocke les données client suivantes au repos uniquement dans cet emplacement :

- Conversations, conversations d’équipe et de canal, images, messages vocaux et contacts Teams
- Contenu du site SharePoint Online et fichiers stockés sur ce site
- Fichiers chargés sur OneDrive Entreprise

#### <a name="chat-channel-messages-team-structure"></a>Conversation, messages de canal, structure d’équipe

Chaque équipe dans Teams possède un groupe Microsoft 365, ainsi que son site SharePoint et sa boîte aux lettres Exchange. Les conversations privées (y compris les conversations de groupe), les messages envoyés dans le cadre d’une conversation dans un canal, de même que la structure des équipes et canaux sont stockés dans un service de conversation exécuté dans Azure. Les données sont également stockées dans un dossier masqué dans les boîtes aux lettres des utilisateurs et des groupes afin d’activer les fonctionnalités de protection des informations.

#### <a name="voicemail-and-contacts"></a>Messages vocaux et contacts

Les messages vocaux sont stockés dans Exchange. Les contacts sont stockés dans un magasin de données sur le cloud et basé sur Exchange. Exchange et le magasin sur le cloud basé sur Exchange offrent déjà la résidence des données dans chacun des centres de données mondiaux. Pour toutes les équipes, les messages vocaux et les contacts sont stockés dans le pays-même pour l’Australie, le Canada, la France, l’Allemagne, l’Inde, le Japon, les Émirats arabes unis, le Royaume-Uni, le Royaume-Uni, l’Afrique du Sud, la Suisse (y compris le Liechtenstein) et les États-Unis. Pour tous les autres pays, les fichiers sont stockés aux États-Unis, en Europe ou en Asie-Pacifique en fonction de l’affinité des clients.

#### <a name="images-and-media"></a>Images et éléments multimédias

Les éléments multimédias utilisés dans les conversations (à l’exception des GIF Giphy qui ne sont pas stockés, mais qui sont des liens de référence vers l’URL de service Giphy d’origine ; Giphy n’est pas un service Microsoft) sont stockés dans un service multimédia Azure déployé aux mêmes emplacements que le service de conversation.

#### <a name="files"></a>Fichiers

Les fichiers (y compris OneNote et Wiki) qu’une personne partage dans un canal sont stockés sur le site SharePoint de l’équipe. Les fichiers partagés dans une conversation, privée ou non, pendant une réunion ou un appel sont téléchargés et stockés dans le compte OneDrive Entreprise de l’utilisateur qui les partage. Exchange, SharePoint et OneDrive offrent déjà la résidence des données dans chacun des centres de données mondiaux. Par conséquent, pour les clients existants, tous les fichiers, les blocs-notes OneNote, les contenus de Wiki Teams et les boîtes aux lettres faisant partie de l’expérience de Teams sont déjà stockés à l’emplacement en fonction de l’affinité de votre client. Les fichiers sont stockés dans le pays-même pour l’Australie, le Canada, la France, l’Allemagne, l’Inde, le Japon, les Émirats arabes unis, le Royaume-Uni, le Royaume-Uni, l’Afrique du Sud et la Suisse (y compris le Liechtenstein). Pour tous les autres pays, les fichiers sont stockés aux États-Unis, en Europe ou en Asie-Pacifique en fonction de l’affinité des clients.

### <a name="datacenter-locations"></a>Emplacements des centres de données

Les services Teams décrits dans cette section stockent les données au repos aux emplacements suivants :

|Pays ou région  |Emplacement du centre de données |
|---------|---------|
|Australie   |Nouvelle-Galles du Sud et Victoria         |
|Canada    |Québec et Toronto         |
|France    |Marseille et Paris         |
|Allemagne    |Berlin et Francfort      |
|Inde   |Chennai et Pune        |
|Japon    |Tokyo (Saitama) et Osaka         |
|Liechtenstein   |Genève et Zurich       |
|Afrique du Sud     |Johannesburg et Le Cap         |
|Corée du Sud     |Séoul et Busan         |
|Suisse    |Genève et Zurich       |
|Émirats arabes unis     |Abu Dhabi et Dubaï         |
|Royaume-Uni     | Cardiff et Londres        |
|Amériques – Nord et Sud (AMER) |Bay, CA et Boydton, VA       |
|Asie-Pacifique (APAC)  |Singapour et Hong Kong        |
|Europe, Moyen-Orient et Afrique (EMEA)   |Dublin et Amsterdam        |

> [!NOTE]
> Pour le Liechtenstein, les données sont stockées au repos dans les centres de données suisses à Genève et Zurich.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Données stockées auprès d’un fournisseur de stockage tiers

Les organisations qui autorisent les utilisateurs à stocker des fichiers auprès d’un fournisseur de stockage tiers dépendent de l’emplacement de stockage de ces services. Par conséquent, il est conseillé de passer en revue l’emplacement des données au repos pour ces services séparément.

- **Onglets** : les onglets permettent aux utilisateurs d’épingler des informations provenant d’applications et de services à un canal. Par conséquent, l’emplacement de stockage des données varie en fonction du type d’onglet. L’onglet proprement dit ne stocke aucune donnée. Par exemple, un onglet SharePoint stocke des données en fonction de l’emplacement de mise en service de la collection de sites SharePoint. Un onglet qui inclut les informations d’un partenaire stocke les données directement dans le système utilisé par le partenaire et ne fait que les afficher.
- **Autres applications partenaires** : Microsoft n’offre aucune prise en charge de la résidence des données pour les applications et services des partenaires que vous pouvez utiliser au sein de l’expérience Teams. Consultez les informations de ces solutions directement pour en savoir plus sur l’emplacement de stockage des données.

## <a name="see-also"></a>Voir aussi

- [Microsoft Teams lance la résidence des données aux Émirats arabes unis](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams lance la résidence des données en Corée du Sud](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams lance la résidence des données en Afrique du Sud](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams lance la résidence des données en France](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams lance la résidence des données en Inde ; d’autres régions seront bientôt disponibles](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams lance la résidence des données en Australie et au Japon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams lance la résidence des données au Canada ; l’Australie et le Japon seront bientôt disponibles](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
