---
title: Ajouter l’adresse IP 2010 interne du serveur Edge
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Utilisez cette page pour préciser l'adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.
ms.openlocfilehash: 45a0d731ace90677ade72ddb6a37ae39b7d697c4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776404"
---
# <a name="add-edge-server-internal-ip-2010"></a>Ajouter l’adresse IP 2010 interne du serveur Edge

Utilisez cette page pour préciser l'adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.

Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet. Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Vous devez donc configurer un suffixe DNS (Domain Name System) sur le nom de l'ordinateur à déployer en tant que serveur Edge non joint à un domaine. Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).