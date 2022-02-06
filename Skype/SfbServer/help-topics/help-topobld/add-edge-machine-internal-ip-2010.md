---
title: "Ajouter l’adresse\_IP\_2010 interne de l’ordinateur Edge"
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour préciser l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.
---

# <a name="add-edge-machine-internal-ip-2010"></a>Ajouter l’adresse IP 2010 interne de l’ordinateur Edge

Utilisez cette page pour préciser l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.

- Dans **l’adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous souhaitez ajouter au pool.

- Dans **le nom de domaine complet interne**, tapez le nom de domaine complet (FQDN) du serveur Edge que vous souhaitez ajouter au pool.

Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet. Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Vous devez donc configurer un suffixe DNS (Domain Name System) sur le nom de l'ordinateur à déployer en tant que serveur Edge non joint à un domaine. Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).