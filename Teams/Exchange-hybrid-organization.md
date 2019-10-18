---
title: Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Découvrez comment configurer une organisation Exchange hybride à utiliser avec Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd18381a8d889a1cebad04234e56bf11def9197e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563894"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams
======================================================================

En règle générale, vous n’avez pas besoin de configurer une fonctionnalité Exchange Online à utiliser avec Microsoft Teams. Toutefois, pour les scénarios Exchange hybrides, il existe certaines étapes nécessaires pour garantir la synchronisation des appartenances aux groupes entre Exchange Server (local) et Exchange Online. Pour cela, il est nécessaire d’activer la fonctionnalité d’écriture différée de groupe dans Azure AD Connect avec différents scripts d’initialisation : [configurer les groupes Office 365 avec Exchange hybride local](https://go.microsoft.com/fwlink/?linkid=854389).
