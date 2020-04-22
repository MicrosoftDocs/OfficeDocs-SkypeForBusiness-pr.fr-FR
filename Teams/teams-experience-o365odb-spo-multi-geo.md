---
title: Accès aux équipes dans une 365 ou Office 365 OneDrive et SharePoint Online avec une location autonome multigéo
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: Apprenez-en davantage sur l’utilisation des équipes dans Microsoft 365 ou Office 365 OneDrive et SharePoint Online avec une location multi-géographiques.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534155d49cda89291e5d8bdfb8da9b8caf0efb5f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780393"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Accès aux équipes dans une 365 ou Office 365 OneDrive et SharePoint Online avec une location autonome multigéo
===========================================

Microsoft teams est un logiciel de discussion de groupe, concentrateur pour le travail en équipe dans Office 365. Ce service est fourni par le service groupes Microsoft 365 avec SharePoint Online et OneDrive entreprise pour son utilisation des fichiers. Dans un espace de travail de type My-géo de OneDrive entreprise/SharePoint Online, dans lequel le locataire est étendu à de nombreux emplacements géographiques tels que l’Amérique du Nord, l’Europe et l’Australie, l’interface de fichiers sous-jacente est compatible avec plusieurs géo Il s’agit d’une fonctionnalité de pointe clé pour les équipes de fichiers en surface hébergées sur plusieurs GEOS dans l’interface des fichiers natifs.

Par exemple, dans le cadre d’une location de contoso avec l’Europe comme un satellite de géo et d’Amérique du Nord au sein de la région centrale, un utilisateur de satellite européen verra ses fichiers OneDrive dans le volet gauche, même si les fichiers sont hébergés dans l’emplacement des données Europe et si les États-Unis sont l’emplacement central du client. Par ailleurs, l’utilisateur peut accéder aux derniers fichiers utilisés dans la Blade d’affichage récente. Les fichiers récents peuvent inclure des fichiers partagés avec l’utilisateur d’autres utilisateurs dans d’autres GEOS et peuvent être masterisés dans d’autres emplacements géographiques dans lesquels le locataire est étendu. 

Le site de groupe d’une équipe donné est également compatible avec plusieurs géo. Autrement dit, si un utilisateur de satellite européen crée une équipe, le site des groupes correspondant est créé dans l’emplacement européen et les fichiers associés à ce groupe d’équipe seront conservés à cet emplacement. Toute expérience subséquente, telle que le téléchargement d’un nouveau fichier ou la modification du fichier, sera ciblée vers cet emplacement européen, afin de garantir la conservation des données pour ces fichiers. C’est tout ce qu’il est possible de faire en sorte que les groupes Microsoft 365 de la Fondation sous-jacente deviennent compatibles avec plusieurs géo.

Dans la mesure où une location multipoint est un client global unique, au cours des @ mentions, les utilisateurs satellites pourront voir leurs collègues du monde entier, quel que soit l’endroit où ils se trouvent. 

Remarque : les conversations dans les conversations et les notes de messagerie instantanée de réunion au sein de l’interface de Teams ne prennent pas en charge la géolocalisation et ne se trouvent qu’à l’intérieur de l’emplacement central du client. En règle générale, les conversations par messagerie instantanée ne sont pas appliquées aux besoins de résidence des données.

Pour plus d’informations sur Office 365 multi-géo, voir la [page de capacités de Microsoft multi-géo](https://aka.ms/multi-geo).