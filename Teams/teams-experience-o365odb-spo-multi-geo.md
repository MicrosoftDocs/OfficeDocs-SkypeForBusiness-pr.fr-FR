---
title: Expérience Teams dans un environnement Multi-Geo-enabled Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Dans cet article, vous découvrirez comment utiliser Teams dans un environnement Microsoft 365 multigéogé.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122244"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Expérience Teams dans un client Microsoft 365 Multi-Geo-enabled

Microsoft Teams est un logiciel de conversation de groupe, qui est le hub pour le travail d’équipe dans Microsoft 365 et Office 365. Il est optimisé par le service Groupes Microsoft 365 ainsi que par SharePoint Online et OneDrive Entreprise pour son expérience des fichiers. Dans un client OneDrive Entreprise/SharePoint Online multigéogé, dans lequel le client est étendu à de nombreux emplacements géographiques tels que l’Amérique du Nord, l’Europe et l’Australie, l’expérience des fichiers sous-jacents est géographiquement multigéoyée, de sorte que l’expérience Teams en ce qui a lieu avec la collaboration de fichiers est également géographiquement multiple. Cette fonctionnalité est une fonctionnalité de pointe pour Teams pour surface des fichiers hébergés dans plusieurs régions géographiques dans son expérience de fichiers natifs. Cela inclut également les fichiers OneNote et Wiki.

Par exemple, dans un client Contoso dont l’Europe est une région géographique satellite et l’Amérique  du Nord comme région centrale, un utilisateur satellitaire européen verra ses fichiers OneDrive sous l’onglet Fichiers dans le volet gauche, bien que les fichiers soient hébergés à l’emplacement de données d’Europe et que les États-Unis d’Amérique soient l’emplacement central du locataire. L’utilisateur peut également accéder aux derniers fichiers utilisés sous le lame **d’affichage** Récent. Les fichiers récents peuvent inclure des fichiers partagés par des utilisateurs à d’autres emplacements géographiques. 

Le site SharePoint d’une équipe donnée est également géographiquement géographique. Autrement dit, si un utilisateur satellitaire européen crée une équipe, le site SharePoint correspondant est créé en Europe. Les fichiers associés à cette équipe sont conservés au repos à cet emplacement. Les expériences suivantes, telles que le téléchargement d’un nouveau fichier ou sa modification, seront stockées dans cet emplacement européen, ce qui conserve la promesse de résidence de données pour ces fichiers.

Étant donné qu’un client multigé géographique est un client global unique, durant la mention @ , les utilisateurs satellitaires pourront voir leurs collègues du monde entier, où qu’ils se trouveront.

Les conversations dans les conversations, les messages de canaux et les notes de messagerie instantanée de réunion/conversations au sein de l’expérience Teams ne sont pas géographiquement multiples et sont toutes conservées uniquement à l’intérieur de l’emplacement central du client. En règle générale, les conversations de conversation ne sont pas appliquées aux besoins de résidence de données. Pour plus d’informations, [voir Localisation des données dans Microsoft Teams.](location-of-data-in-teams.md)

Pour plus d’informations sur Multi-Geo, consultez la [page Microsoft Multi-Geo capabilities.](https://aka.ms/multi-geo)
