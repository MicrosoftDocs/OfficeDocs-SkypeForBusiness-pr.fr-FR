---
title: Teams expérience utilisateur dans un Microsoft 365 multigéoding
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
description: Dans cet article, vous allez découvrir comment utiliser des Teams dans un environnement Microsoft 365 multigéodité.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760537"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams expérience en environnement Microsoft 365 client multigéogé activé

Microsoft Teams est un logiciel de conversation de groupe, la plateforme pour le travail en équipe dans Microsoft 365 et Office 365. Il est optimisé par le service Microsoft 365 Groupes d’utilisateurs, ainsi que par SharePoint Online et OneDrive Entreprise pour son expérience des fichiers. Dans un client OneDrive Entreprise/SharePoint Online multigéographique, dans lequel le client est étendu à de nombreux emplacements géographiques tels que l’Amérique du Nord, l’Europe et l’Australie, l’expérience des fichiers sous-jacents est géographiquement multiple, de sorte que l’expérience Teams avec la collaboration de fichiers est également géographiquement multigéonte. Cette fonctionnalité est une fonctionnalité de pointe pour les Teams à surface qui sont hébergés sur plusieurs geos dans son expérience de fichiers natifs. Cela inclut également les OneNote et Wiki.

Par exemple, dans un client Contoso dont l’Europe est une région géographique satellite et l’Amérique du  Nord comme région géographique centrale, un utilisateur satellitaire européen verra ses fichiers OneDrive sous l’onglet Fichiers dans le volet gauche, bien que les fichiers soient hébergés à l’emplacement de données d’Europe et que les États-Unis d’Amérique soient l’emplacement central du locataire. L’utilisateur peut également accéder aux derniers fichiers utilisés sous le lame **d’affichage** Récent. Les fichiers récents peuvent inclure des fichiers partagés par des utilisateurs à d’autres emplacements géographiques. 

Le site géographique d’SharePoint donné est également géographiquement géographique. Autrement dit, si un utilisateur satellitaire européen crée une équipe, le site SharePoint est créé en Europe. Les fichiers associés à cette équipe sont conservés au repos à cet emplacement. Les expériences suivantes, telles que le téléchargement d’un nouveau fichier ou sa modification, seront stockées dans cet emplacement européen, ce qui conserve la promesse de résidence de données pour ces fichiers.

Étant donné qu’un client multigé géographique est un client global unique, durant la mention @ , les utilisateurs satellitaires pourront voir leurs collègues du monde entier, où qu’ils se trouveront.

Les conversations dans les conversations, les messages de canaux et les notes/conversations de réunion par messagerie instantanée au sein d’une expérience Teams ne sont pas géographiquement multiples et sont toutes conservées uniquement dans l’emplacement central du client. En règle générale, les conversations de conversation ne sont pas appliquées aux besoins de résidence de données. Pour plus d’informations, [voir Emplacement des données dans Microsoft Teams.](location-of-data-in-teams.md)

La prise en charge multigé géographique Teams est sur la feuille [de route Microsoft 365 de l’entreprise.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)

Pour plus d’informations sur Multi-Geo, consultez la [page Microsoft Multi-Geo capabilities.](https://aka.ms/multi-geo)
