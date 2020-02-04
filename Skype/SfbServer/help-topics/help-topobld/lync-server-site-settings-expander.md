---
title: Expandeur des paramètres du site du serveur Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Pour modifier les propriétés d’un site existant, procédez comme suit :'
ms.openlocfilehash: edbc1df57334e8485d844cfa0ac978d0a5b0e15c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697059"
---
# <a name="lync-server-site-settings-expander"></a>Expandeur des paramètres du site du serveur Lync

Pour modifier les propriétés d’un site existant, procédez comme suit :



## <a name="site-properties"></a>Propriétés du site

Dans les propriétés du site, vous pouvez modifier ou modifier le nom du site (obligatoire), la description (facultatif), la ville (facultatif), l’État ou la province (facultatif) et le code de pays/région (facultatif).

Pour plus d’informations sur les propriétés de site, voir [Ajouter des sites de succursales à votre topologie](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Propriétés d’itinéraire de Fédération

Pour définir une affectation de l’itinéraire de Fédération de site, vous devez d’abord disposer de la Fédération sur un serveur Edge ou un pool de serveurs Edge. Si la Fédération n’est pas activée sur un serveur Edge ou un pool, les paramètres d’attribution de l’itinéraire de Fédération pour le site ne seront pas disponibles à des fins de modification.

Si le paramètre de Fédération sur le serveur Edge ou le pool a été configuré, sélectionnez **activer** au niveau du site. Sélectionnez ensuite une arête ou un réalisateur dans la liste déroulante à définir comme itinéraire de Fédération.

> [!CAUTION]
> Ce paramètre affecte tous les sites. Assurez-vous que le paramètre que vous configurez sur ce site est approprié pour tous les sites.

## <a name="see-also"></a>Voir aussi

Pour plus d’informations, reportez-vous à la rubrique [topologies pour l’accès des utilisateurs externes](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


