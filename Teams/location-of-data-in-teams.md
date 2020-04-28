---
title: Emplacement des données dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Dans cet article, vous allez découvrir où les données résident géographiquement dans Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ebe94c04fcc4d93f636544d54930cf83855deec2
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904816"
---
# <a name="location-of-data-in-microsoft-teams"></a>Emplacement des données dans Microsoft Teams

Les données en équipe résident dans la zone géographique associée à votre organisation 365 Office. Actuellement, teams prend en charge l’Australie, le Canada, la France, l’Inde, le Japon, l’Afrique du Sud, la Corée du Sud, la Suisse (qui comprend le Liechtenstein), les Émirats Arabes Unis, le Royaume-Uni, le continent, l’Asie et la région EMEA. 

> [!IMPORTANT]
> Teams propose actuellement une résidence de données en Australie, au Canada, en France, en Allemagne, en Inde, au Japon, aux Émirats Arabes Unis, au Royaume-Uni, en Corée du Sud, en Afrique du Sud et en Suisse (qui inclut le Liechtenstein) uniquement pour les nouveaux clients.
> Tout client qui ne possédait pas d'utilisateur unique inscrit dans Teams est considéré comme un nouveau client. Les clients existants tirés de l’Australie, de l’Inde, du Japon et de la Corée du Sud continuent d’avoir leurs données en équipe stockées dans la région sud-est. Les clients existants au Canada continuent d’avoir leurs données stockées dans le continent américain. Les clients existants en France, en Allemagne, au Liechtenstein, aux Émirats Arabes Unis, au Royaume-Uni, en Afrique du Sud et en Suisse auront leurs données stockées dans la région EMEA.

## <a name="where-your-teams-data-is-stored"></a>Emplacement de stockage des données de votre équipe

Pour afficher la région qui abrite les données pour votre client, accédez au**profil d’organisation****paramètres** > du centre > d' [administration 365 Microsoft](https://portal.office.com/adminportal/home). Défilez jusqu’à la section **Emplacement des données**.

![Capture d’écran de la table d’emplacements des données, y compris équipes dans le centre d’administration](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Emplacement des données d’équipe sur REST

Les données de teams sont stockées différemment en fonction du type de contenu. 

![Diagramme indiquant les types de contenu de l’équipe et l’emplacement de stockage des éléments dans Rest](media/location-of-data-storage-at-rest.png)

Pour consulter des informations détaillées, voir la [session d’enflamme dans l’architecture de Microsoft teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) .

### <a name="core-teams-customer-data"></a>Données client principales teams

Si votre client est approvisionné en Australie, au Canada, en Europe, en Allemagne, en Allemagne, en Allemagne, en Allemagne, en Allemagne, en Afrique du Sud, en Corée du Sud, en Suisse (au Liechtenstein), aux Émirats Arabes Unis, au Royaume-Uni et aux États-Unis, Microsoft stocke les données client suivantes dans Rest uniquement dans cet emplacement :

- Discussions d’équipe, équipes et conversations de canal, images, messages vocaux et contacts
- Le contenu du site SharePoint Online et les fichiers stockés dans ce site
- Fichiers téléchargés vers OneDrive entreprise

#### <a name="chat-channel-messages-team-structure"></a>Discussions, messages de canal, structure d’équipe

Chaque équipe dans teams est stockée par un groupe Office 365 et son site SharePoint et sa boîte aux lettres Exchange. Discussions privées (y compris les discussions de groupe), messages envoyés dans le cadre d’une conversation dans un canal et la structure des équipes et des canaux est stockée dans un service de chat qui s’exécute dans Azure. Les données sont également stockées dans un dossier masqué dans les boîtes aux lettres des utilisateurs et des groupes pour activer les fonctionnalités de protection des informations.

#### <a name="voicemail-and-contacts"></a>Boîte vocale et contacts

Les messages vocaux sont stockés dans Exchange. Les contacts sont stockés dans un magasin de données Cloud Exchange. Exchange et le Windows Cloud Store fournissent déjà des informations de résidence sur chacun des GEOS du centre de données mondial. Pour toutes les équipes, la boîte vocale et les contacts sont stockés dans le pays pour l’Australie, le Canada, la France, l’Allemagne, l’Inde, le Japon, les Émirats Arabes Unis, le Royaume-Uni, les États-Unis, le Royaume-Uni, la Suisse (au Liechtenstein) et les États-Unis. Pour tous les autres pays, les fichiers sont stockés aux États-Unis, en Europe ou en Asie-Pacifique en fonction de l’affinité du client.

#### <a name="images-and-media"></a>Images et éléments multimédias

Contenu multimédia utilisé dans les discussions (à l’exception des fichiers GIF Giphy qui ne sont pas stockés, mais qui sont un lien de référence vers l’URL du service Giphy d’origine, Giphy est un service non-Microsoft) est stocké dans un service multimédia basé sur Azure qui est déployé aux mêmes emplacements que le service Chat.

#### <a name="files"></a>Fichiers

Les fichiers (y compris OneNote et wiki) qu’une personne partage dans un canal sont stockés sur le site SharePoint de l’équipe. Les fichiers partagés au cours d’une conversation ou d’une discussion privée lors d’une réunion ou d’un appel sont chargés et stockés dans OneDrive pour le compte professionnel de l’utilisateur qui partage le fichier. Exchange, SharePoint et OneDrive fournissent déjà des informations de résidence sur chacun des GEOS du centre de données mondial. Ainsi, pour les clients existants, tous les fichiers, blocs-notes OneNote, contenu wiki en équipes et boîtes aux lettres qui font partie de l’environnement d’équipe sont déjà stockés dans l’emplacement en fonction de l’affinité de votre client. Les fichiers sont stockés dans le pays en Australie, au Canada, en France, en Allemagne, en Inde, au Japon, aux Émirats Arabes Unis, au Royaume-Uni, en Afrique du Sud, en Corée du Sud et en Suisse (qui comprend le Liechtenstein). Pour tous les autres pays, les fichiers sont stockés aux États-Unis, en Europe ou en Asie du Pacifique en fonction de l’affinité du client.

### <a name="datacenter-locations"></a>Emplacements de centre de passe

Les services d’équipe décrits dans cette section stockent les données sur REST aux emplacements suivants :

|Pays ou région  |Emplacement du datacenter |
|---------|---------|
|Australie   |Nouvelle Galles du Sud et Victoria         |
|Canada    |Québec City et Toronto         |
|France    |Marseille et Paris         |
|Allemagne    |Berlin et Francfort      |
|Inde   |Chennai et Pune        |
|Japon    |Tokyo (Saitama) et Osaka         |
|Liechtenstein   |Genève et Zurich       |
|Afrique du Sud     |Johannesbourg et Cape Town         |
|Corée du Sud     |Séoul et Busan         |
|Suisse    |Genève et Zurich       |
|Émirats arabes unis     |Abu Dhabi et Dubaï         |
|Royaume-Uni     | Cardiff et Londres        |
|Americas-North et South (AMER) |Bay, CA et Boydton, VA       |
|Asie-Pacifique (APAC)  |Singapour et Hong Kong        |
|Europe, Moyen Orient et Asie (EMEA)   |Dublin et Amsterdam        |

> [!NOTE]
> Pour le Liechtenstein, les données sont stockées sur REST dans les centres de données suisses de Genève et Zurich.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Données stockées auprès d’un fournisseur de stockage tiers

Les organisations qui autorisent les utilisateurs à stocker des fichiers auprès d’un fournisseur de stockage tiers dépendent de l’emplacement de stockage de ces services et doivent donc consulter l’emplacement des données sur REST pour ces services séparément.

- **Onglets**: les onglets permettent aux utilisateurs d’épingler les informations d’applications et de services à un canal. Par conséquent, il varie en fonction du type de l’onglet dans lequel les données sont stockées. L’onglet ne stocke pas de données. Par exemple, un onglet SharePoint stockera les données en fonction de la configuration de la collection de sites SharePoint. Un onglet qui inclut des informations d’un partenaire stockera les données directement dans le système utilisé par le partenaire et ne présente qu’un affichage.
- **Autres applications partenaires**: Microsoft ne fournit pas de prise en charge des données pour les applications et services provenant de partenaires que vous utilisez peut-être dans le cadre de l’utilisation de teams. Passez en revue les informations de ces solutions directement pour en savoir plus sur l’emplacement de stockage des données.

## <a name="see-also"></a>Voir aussi

- [Microsoft teams lance les informations de résidence des Émirats Arabes Unis](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft teams lance la résidence des données du sud-coréen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft teams lance la résidence des données du sud-africains](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft teams lance la résidence des données françaises](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft teams lance la résidence des données Inde, d’autres GEOS bientôt disponible](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft teams lance la résidence des données en Australie et au Japon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft teams lance le pays de résidence des données du Canada, l’Australie et le Japon bientôt disponible](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
