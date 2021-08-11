---
title: Ajouter l’adresse IP interne de l’ordinateur Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Utilisez cette page pour préciser l'adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.
ms.openlocfilehash: 72e98165d4c279d1e35e0cb36afc49835e6010f72dfe685bec0e3eb8786d469f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294381"
---
# <a name="add-edge-machine-internal-ip"></a>Ajouter l’adresse IP interne de l’ordinateur Edge

Utilisez cette page pour préciser l’adresse IP interne et le nom de domaine complet (FQDN) interne du serveur Edge.

Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet. Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. Vous devez donc configurer un suffixe DNS (Domain Name System) sur le nom de l'ordinateur à déployer en tant que serveur Edge non joint à un domaine. Pour plus d’informations sur l’ajout d’un suffixe DNS à un nom d’ordinateur, voir [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).