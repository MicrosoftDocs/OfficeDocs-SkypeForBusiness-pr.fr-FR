---
title: Ajouter IP interne de l’ordinateur de bord 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) pour le serveur de transport Edge.
ms.openlocfilehash: 2fedde361e252d400f4362add4757df3f0c40057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-machine-internal-ip-2010"></a>Ajouter IP interne de l’ordinateur de bord 2010
 
Utilisez cette page pour spécifier l’adresse IP interne et le nom de domaine complet interne (FQDN) pour le serveur de transport Edge.
  
- Dans la zone **adresse IPv4 interne**, tapez l’adresse IP du serveur Edge que vous souhaitez ajouter à la liste.
    
- Dans **Nom de domaine interne complet**, tapez le nom de domaine complet (FQDN) du serveur Edge que vous souhaitez ajouter à la liste.
    
Le nom de domaine complet que vous spécifiez doit être identique au nom de l’ordinateur qui est configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, et non un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. Par conséquent, vous devez configurer un suffixe de nom de domaine (DNS) sur le nom de l’ordinateur pour être déployé comme un serveur de transport Edge qui n’est pas joint à un domaine. Pour plus d’informations sur l’ajout d’un suffixe DNS pour un nom d’ordinateur, voir [Configurer le serveur DNS pour la prise en charge du bord](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)
  

