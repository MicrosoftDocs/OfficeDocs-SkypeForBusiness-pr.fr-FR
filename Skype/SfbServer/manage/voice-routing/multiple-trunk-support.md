---
title: Prise en charge de plusieurs Trunks dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La fonctionnalité Skype entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP. Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816944"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Prise en charge de plusieurs Trunks dans Skype entreprise Server

La fonctionnalité Skype entreprise Server prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP. Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).

- Pour attribuer ou supprimer un Trunk dans Skype entreprise Server, vous devez commencer par définir un Trunk dans le générateur de topologie. Un Trunk est composé de l’Association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.
- Pour configurer plusieurs Trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela fournit une résilience supplémentaire à l’infrastructure voix entreprise, qui est particulièrement utile dans les scénarios d’interopération de PBX (Private Branch Exchange). 

Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer un Trunk à un itinéraire, vous devez définir un nom simple pour le Trunk dans le générateur de topologie. Ce nom simple sert de nom de Trunk dans le panneau de configuration Skype entreprise Server, où les Trunks peuvent être associés à des itinéraires. Le nom simple de Trunk est utilisé comme nom de la passerelle de Skype entreprise Server Management Shell.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

L’administrateur doit sélectionner une Trunk par défaut associée à un serveur de médiation. Dans le générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**. Spécifiez la passerelle par défaut du serveur de médiation. 

Le diagramme suivant illustre les différentes liaisons définies pour chaque serveur et passerelle de médiation. 

![Attributions de plusieurs lignes](../../media/multiple-trunk-assignments.jpg)
