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
description: Découvrez comment configurer une organisation Exchange hybride pour l’utiliser avec Microsoft Teams vous assurer que les appartenances aux groupes sont synchronisées.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d1b5cb89f28a334b24aecf982dd3913dfce079ac
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014869"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams

En règle générale, vous ne devez configurer aucune fonctionnalité Exchange Online à utiliser avec Microsoft Teams. Toutefois, pour Exchange scénarios hybrides, il existe des étapes nécessaires pour s’assurer que les appartenances aux groupes sont synchronisées entre Exchange Server (local) et Exchange Online. Cela implique l’enablement de la fonctionnalité de écriture de groupe dans Azure AD Connecter ainsi que divers scripts d’initialisation : configurer des groupes Microsoft 365 avec une solution Exchange hybride en [local.](/exchange/hybrid-deployment/set-up-microsoft-365-groups)