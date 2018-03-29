---
title: Développement de paramètres de Site Lync Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Pour modifier les propriétés d’un site existant, effectuez le des opérations suivantes :'
ms.openlocfilehash: 6ae0154da4e53cffb9d0b6bb02a2eda3cb0cbaa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="lync-server-site-settings-expander"></a>Développement de paramètres de Site Lync Server
 
Pour modifier les propriétés d’un site existant, effectuez le des opérations suivantes :
  
## 

### <a name="site-properties"></a>Propriétés du site

Dans les propriétés du site, vous pouvez modifier ou modifier le site nom (obligatoire), Description (facultative), Ville (facultatif), État/Province (facultative) et le Code de pays/région (facultatif).
  
Pour plus d’informations sur les propriétés du site, consultez [Ajout de Sites à la topologie de votre branche](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).
  
### <a name="federation-route-properties"></a>Propriétés d’itinéraire de fédération

Pour définir une affectation d’itinéraire de fédération site, vous devez avoir activé sur un serveur Edge ou un pool de serveur de transport Edge de fédération. Si la fédération n’est pas activée sur un serveur Edge ou du pool, les paramètres d’affectation de gamme fédération pour le site ne sera pas disponibles pour la modification.
  
Si le paramètre de fédération au niveau du serveur Edge ou du pool a été configuré, sélectionnez **Activer** au niveau du site. Puis sélectionnez une arête ou un directeur à partir de la liste déroulante pour définir que l’itinéraire de fédération.
  
> [!CAUTION]
> Ce paramètre affecte tous les sites. Assurez-vous que le paramètre que vous configurez sur ce site est approprié pour tous les sites. 
  
### 

Pour plus d’informations, consultez [Topologies pour l’accès des utilisateurs externes](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).
  

