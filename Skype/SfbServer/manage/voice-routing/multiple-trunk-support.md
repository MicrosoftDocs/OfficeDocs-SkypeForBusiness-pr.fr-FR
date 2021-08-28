---
title: Prise en charge de plusieurs Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype Entreprise Server de médiation prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont réalisées en définissant une trunk, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur SBC (Session Border Controller) ou un SYSTÈME IP-PBX. Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (c’est-à-dire, des trunks).
ms.openlocfilehash: 99a549fddab959681f71d8de124793957ec9d445
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635248"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Prise en charge de plusieurs Skype Entreprise Server

Skype Entreprise Server de médiation prend en charge plusieurs associations entre les passerelles et les serveurs de médiation. Ces associations sont réalisées en définissant une trunk, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur SBC (Session Border Controller) ou un SYSTÈME IP-PBX. Utilisez le Générateur de topologie pour associer des passerelles à des serveurs de médiation (c’est-à-dire, des trunks).

- Pour affecter ou supprimer une Skype Entreprise Server, vous devez d’abord définir une trunk dans le Générateur de topologies. Une trunk se compose de l’association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.
- Pour configurer plusieurs trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation. Cela offre une résilience supplémentaire à l’infrastructure Voix Entreprise, ce qui est particulièrement utile dans les scénarios interopérationnels PBX (Private Branch Exchange). 

Lorsqu’une jonction est définie, elle doit être associée à un itinéraire. Pour associer une liaison à un itinéraire, vous définissez un nom simple pour la liaison dans le Générateur de topologies. Ce nom simple est utilisé comme nom de la Skype Entreprise Server panneau de Skype Entreprise Server, où des itinéraires peuvent être associés. Le nom de la simple trunk est utilisé comme nom de passerelle à partir de Skype Entreprise Server Management Shell.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

L’administrateur doit sélectionner une trunk par défaut associée à un serveur de médiation. Dans le Générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés.** Spécifiez la passerelle par défaut pour le serveur de médiation. 

Le diagramme suivant illustre les multiples branches définies pour chaque serveur de médiation et passerelle. 

![Affectations de plusieurs branches](../../media/multiple-trunk-assignments.jpg)
