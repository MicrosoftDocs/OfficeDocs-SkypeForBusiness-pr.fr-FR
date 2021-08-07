---
title: Expanseur des paramètres du site du serveur Lync
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Pour modifier les propriétés d’un site existant, procédez comme suit :'
ms.openlocfilehash: 9ace8cc0975e971e7f3c3fe55c89324330816f62d78b0ee5c9b23d16e9ff9689
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305466"
---
# <a name="lync-server-site-settings-expander"></a>Expandeur des paramètres du site du serveur Lync

Pour modifier les propriétés d’un site existant, procédez comme suit :



## <a name="site-properties"></a>Propriétés du site

Dans les propriétés du site, vous pouvez changer ou modifier le nom du site (obligatoire), la description (facultatif), la ville (facultatif), le département/province (facultatif) et le code pays/région (facultatif).

Pour plus d’informations sur les propriétés du site, voir [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).

## <a name="federation-route-properties"></a>Propriétés des itinéraires de fédération

Pour configurer l’itinéraire de fédération d’un site, vous devez d’abord activer la fédération sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur un serveur ou un pool de serveurs Edge, il ne sera pas possible de modifier les paramètres d’affectation de l’itinéraire de fédération du site.

Si le paramètre de fédération du serveur ou pool de serveurs Edge a été configuré, sélectionnez **Activer** au niveau du site. Sélectionnez ensuite un serveur Edge ou un directeur dans la liste déroulante à configurer comme itinéraire de fédération.

> [!CAUTION]
> Ce paramètre affectera tous les sites. Assurez-vous que le paramètre que vous configurez pour ce site s’adapte à tous les sites.

## <a name="see-also"></a>Voir aussi

Pour plus d’informations, voir [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).