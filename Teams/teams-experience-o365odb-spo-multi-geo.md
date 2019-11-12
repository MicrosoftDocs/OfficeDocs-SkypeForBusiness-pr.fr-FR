---
title: Expérience Teams dans un client Office 365 OneDrive et SharePoint Online Multi-Géo
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Apprenez-en davantage sur l’utilisation des équipes dans un espace de location Office 365 OneDrive et SharePoint Online avec une fonction de location.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe181e7ef55b386d4a6eb40bb7e383ca89a956d9
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231245"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Expérience Teams dans un client Office 365 OneDrive et SharePoint Online Multi-Géo
===========================================

Microsoft teams est un logiciel de discussion de groupe, concentrateur pour le travail en équipe dans Office 365. Ce service est fourni par le service de groupes Office 365 avec SharePoint Online et OneDrive entreprise pour son utilisation de fichiers. Dans un espace de travail de type My-géo de OneDrive entreprise/SharePoint Online, dans lequel le locataire est étendu à de nombreux emplacements géographiques tels que l’Amérique du Nord, l’Europe et l’Australie, l’interface de fichiers sous-jacente est compatible avec plusieurs géo Il s’agit d’une fonctionnalité de pointe clé pour les équipes de fichiers en surface hébergées sur plusieurs GEOS dans l’interface des fichiers natifs.

Par exemple, dans le cadre d’une location de contoso avec l’Europe comme un satellite et l’Amérique du Nord au lieu de la région centrale de l’entreprise, un utilisateur de satellite européen verra ses fichiers OneDrive dans l’onglet fichiers du volet gauche, bien que les fichiers soient hébergés dans l’emplacement des données Europe et au United stat es est l’emplacement central du client. Par ailleurs, l’utilisateur peut accéder aux derniers fichiers utilisés dans la Blade d’affichage récente. Les fichiers récents peuvent inclure des fichiers partagés avec l’utilisateur d’autres utilisateurs dans d’autres GEOS et peuvent être masterisés dans d’autres emplacements géographiques dans lesquels le locataire est étendu. 

Le site de groupe d’une équipe donné est également compatible avec plusieurs géo. Autrement dit, si un utilisateur de satellite européen crée une équipe, le site des groupes correspondant est créé dans l’emplacement européen et les fichiers associés à ce groupe d’équipe seront conservés à cet emplacement. Toute expérience subséquente, telle que le téléchargement d’un nouveau fichier ou la modification du fichier, sera ciblée vers cet emplacement européen, afin de garantir la conservation des données pour ces fichiers. C’est tout ce qu’il est possible de faire en sorte que les groupes de Foundation 365 de base sous-jacents deviennent multigéo.

Dans la mesure où une location multipoint est un client global unique, au cours des @ mentions, les utilisateurs satellites pourront voir leurs collègues du monde entier, quel que soit l’endroit où ils se trouvent. 

Remarque : les conversations dans les conversations et les notes de messagerie instantanée de réunion au sein de l’interface de Teams ne prennent pas en charge la géolocalisation et ne se trouvent qu’à l’intérieur de l’emplacement central du client. En règle générale, les conversations par messagerie instantanée ne sont pas appliquées aux besoins de résidence des données.

Pour plus d’informations sur Office 365 multi-géo, voir la [page de capacités de Microsoft multi-géo](https://aka.ms/multi-geo).