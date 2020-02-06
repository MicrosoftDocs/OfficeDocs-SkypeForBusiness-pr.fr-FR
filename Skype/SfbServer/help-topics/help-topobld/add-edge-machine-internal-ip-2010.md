---
title: Ajouter l’adresse IP 2010 interne de l’ordinateur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.
ms.openlocfilehash: 1847362f93c1d1ff67c09fb9f552641b0e770bbc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821136"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Ajouter l’adresse IP 2010 interne de l’ordinateur Edge

Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.

- Dans **adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous voulez ajouter à la liste.

- Dans **FQDN interne**, tapez le nom de domaine complet (FQDN) du serveur de périphérie que vous voulez ajouter au pool.

Le nom de domaine complet (FQDN) que vous spécifiez doit être identique à celui de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Par conséquent, vous devez configurer un suffixe DNS (Domain Name System) sur le nom de l’ordinateur à déployer en tant que serveur Edge qui n’est pas joint à un domaine. Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir [configurer la prise en charge de DNS pour les périphériques](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


