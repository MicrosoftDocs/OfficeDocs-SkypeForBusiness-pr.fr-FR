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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68b2fee13668db8ba3986302d58bc16b0fa89080
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235202"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams
======================================================================

En règle générale, vous n’avez pas besoin de configurer une fonctionnalité Exchange Online à utiliser avec Microsoft Teams. Toutefois, pour les scénarios Exchange hybrides, il existe certaines étapes nécessaires pour garantir la synchronisation des appartenances aux groupes entre Exchange Server (local) et Exchange Online. Pour cela, il est nécessaire d’activer la fonctionnalité d’écriture différée de groupe dans Azure AD Connect avec différents scripts d’initialisation: [configurer les groupes Office 365 avec Exchange hybride local](https://go.microsoft.com/fwlink/?linkid=854389).
