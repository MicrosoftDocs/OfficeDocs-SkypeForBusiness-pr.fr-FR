---
title: Configurer une organisation hybride Exchange
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
description: Découvrez comment configurer une organisation hybride Exchange pour une utilisation avec Microsoft Teams afin de garantir la synchronisation des appartenances aux groupes.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb2471a2680218a69daa74d20b27c4b7642fa1d7
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480674"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurer une organisation Exchange hybride à utiliser avec Microsoft Teams

En règle générale, vous ne devez pas avoir à configurer des fonctionnalités Exchange Online à utiliser avec Microsoft Teams. Toutefois, pour les scénarios Exchange Hybrid, des étapes sont nécessaires pour garantir que les appartenances aux groupes sont synchronisées entre Exchange Server (localement) et Exchange Online. Cela implique l’activation de la fonctionnalité d’écriture différée de groupe dans Azure AD Connect, ainsi que divers scripts d’initialisation : [configurer Groupes Microsoft 365 avec exchange hybride local](/exchange/hybrid-deployment/set-up-microsoft-365-groups).