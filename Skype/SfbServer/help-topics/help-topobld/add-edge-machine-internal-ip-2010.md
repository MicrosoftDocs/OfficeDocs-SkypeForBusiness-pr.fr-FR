---
title: Ajouter l’adresse IP 2010 interne de l’ordinateur Edge
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) du serveur de périphérie.
ms.openlocfilehash: b54fae5ce536e1f859c4c05059b18b5e5067af7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873325"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Ajouter l’adresse IP 2010 interne de l’ordinateur Edge

Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) du serveur de périphérie.

- Dans **adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous souhaitez ajouter au pool.

- Dans **Nom de domaine complet interne**, tapez le nom de domaine complet (FQDN) du serveur Edge que vous souhaitez ajouter au pool.

Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur qui est configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Par conséquent, vous devez configurer un suffixe de nom de domaine DNS (Domain Name System) sur le nom de l’ordinateur à déployer en tant qu’un serveur de périphérie qui n’est pas lié à un domaine. Pour plus d’informations sur l’ajout d’un suffixe DNS pour un nom d’ordinateur, voir [Configurer le serveur DNS pour la prise en charge Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


