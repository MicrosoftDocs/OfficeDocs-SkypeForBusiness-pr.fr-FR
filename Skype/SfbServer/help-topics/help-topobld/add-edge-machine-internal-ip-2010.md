---
title: Ajouter la Machine adresse IP interne Edge 2010
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
ms.openlocfilehash: 1caa3dba0b1b40d7f207b10da2075082face12b0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987711"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Ajouter la Machine adresse IP interne Edge 2010
 
Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) du serveur de périphérie.
  
- Dans **adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous souhaitez ajouter au pool.
    
- Dans **Nom de domaine complet interne**, tapez le nom de domaine complet (FQDN) du serveur Edge que vous souhaitez ajouter au pool.
    
Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur qui est configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Par conséquent, vous devez configurer un suffixe de nom de domaine DNS (Domain Name System) sur le nom de l’ordinateur à déployer en tant qu’un serveur de périphérie qui n’est pas lié à un domaine. Pour plus d’informations sur l’ajout d’un suffixe DNS pour un nom d’ordinateur, voir [Configurer le serveur DNS pour la prise en charge Edge](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)
  

