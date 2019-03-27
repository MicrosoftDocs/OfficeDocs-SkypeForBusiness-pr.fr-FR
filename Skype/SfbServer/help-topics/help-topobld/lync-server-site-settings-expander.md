---
title: Expandeur des paramètres du site du serveur Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Pour modifier les propriétés d’un site existant, procédez comme suit :'
ms.openlocfilehash: 0c6caf08060a94836d0c14169e550634c26e7dc9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883467"
---
# <a name="lync-server-site-settings-expander"></a>Expandeur des paramètres du site du serveur Lync

Pour modifier les propriétés d’un site existant, procédez comme suit :



## <a name="site-properties"></a>Propriétés du site

Dans les propriétés du site, vous pouvez changer ou modifier le nom (obligatoire) du site, Description (facultative), Ville (facultatif), Département/Province (facultative) et le Code de pays/région (facultatif).

Pour plus d’informations sur les propriétés du site, voir [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Propriétés des itinéraires de fédération

Pour définir une attribution itinéraire fédération du site, vous devez au préalable avoir fédération activée sur un serveur Edge ou un pool de serveurs Edge. Si la fédération n’est pas activée sur un serveur Edge ou le pool, les paramètres d’affectation fédération itinéraire pour le site ne sera pas disponibles pour la modification.

Si le paramètre de fédération au pool ou serveur Edge a été configuré, sélectionnez **Activer** au niveau du site. Puis sélectionnez un contour ou un directeur dans la liste déroulante pour définir en tant que l’itinéraire de fédération.

> [!CAUTION]
> Ce paramètre affecte tous les sites. N’oubliez pas que le paramètre que vous configurez sur ce site est approprié pour tous les sites.

## <a name="see-also"></a>Voir aussi

Pour plus d’informations, voir [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


