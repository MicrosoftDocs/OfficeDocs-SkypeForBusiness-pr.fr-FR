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
description: Apprenez à configurer une organisation Exchange hybride à utiliser avec Microsoft teams pour garantir la synchronisation des appartenances aux groupes.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee558c8c8bfa6c5bd66e001d31ed76a8061df3f4
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902959"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams
======================================================================

En règle générale, vous n’avez pas besoin de configurer une fonctionnalité Exchange Online à utiliser avec Microsoft Teams. Toutefois, pour les scénarios Exchange hybrides, il existe certaines étapes nécessaires pour garantir la synchronisation des appartenances aux groupes entre Exchange Server (local) et Exchange Online. Pour cela, vous devez activer la fonctionnalité d’écriture différée de groupe dans Azure AD Connect avec différents scripts d’initialisation : [configurer des groupes Microsoft 365 avec Exchange hybride local](https://go.microsoft.com/fwlink/?linkid=854389).
