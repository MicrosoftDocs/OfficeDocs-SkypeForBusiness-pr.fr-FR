---
title: Expanseur des paramètres du site du serveur Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 69555a04be4125e213ba2eca7afd7255100c0444
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217565"
---
# <a name="lync-server-site-settings-expander"></a>Expanseur des paramètres du site du serveur Lync

Pour modifier les propriétés d’un site existant, procédez comme suit :



## <a name="site-properties"></a>Propriétés du site

Dans les propriétés du site, vous pouvez changer ou modifier le nom du site (obligatoire), la description (facultatif), la ville (facultatif), le département/province (facultatif) et le code pays/région (facultatif).

Pour plus d’informations sur les propriétés du site, voir [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Propriétés des itinéraires de fédération

Pour configurer l’itinéraire de fédération d’un site, vous devez d’abord activer la fédération sur le serveur Edge ou le pool de serveurs Edge. Si la fédération n’est pas activée sur un serveur ou un pool de serveurs Edge, il ne sera pas possible de modifier les paramètres d’affectation de l’itinéraire de fédération du site.

Si le paramètre de fédération du serveur ou pool de serveurs Edge a été configuré, sélectionnez **Activer** au niveau du site. Sélectionnez ensuite un serveur Edge ou un directeur dans la liste déroulante à configurer comme itinéraire de fédération.

> [!CAUTION]
> Ce paramètre affectera tous les sites. Assurez-vous que le paramètre que vous configurez pour ce site s’adapte à tous les sites.

## <a name="see-also"></a>Voir aussi

Pour plus d’informations, voir [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


