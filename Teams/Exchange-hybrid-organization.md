---
title: Configurer une organisation Exchange hybride
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Découvrez comment configurer une organisation Exchange hybride pour l’utiliser avec Microsoft Teams pour vous assurer que les appartenances aux groupes sont synchronisées.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551960"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams
======================================================================

En règle générale, vous ne devez configurer aucune fonctionnalité Exchange Online pour une utilisation avec Microsoft Teams. Toutefois, pour les scénarios Exchange hybrides, il existe des étapes nécessaires pour s’assurer que les appartenances aux groupes sont synchronisées entre Exchange Server (local) et Exchange Online. Cela implique l’enablement de la fonctionnalité de écriture de groupe dans Azure AD Connect, ainsi que divers scripts d’initialisation : Configurer des groupes [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)avec un environnement Exchange hybride local.
