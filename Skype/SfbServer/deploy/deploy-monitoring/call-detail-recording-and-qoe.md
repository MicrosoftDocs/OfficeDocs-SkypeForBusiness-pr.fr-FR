---
title: Configurer les paramètres d’enregistrement des détails des appels et de qualité de l’expertise dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Résumé: Découvrez comment configurer les CDR et QoE dans Skype entreprise Server.'
ms.openlocfilehash: 8a83e5920de60d664e76590d2b5b2a9f36b589ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306639"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurer les paramètres d’enregistrement des détails des appels et de qualité de l’expertise dans Skype entreprise Server
 
**Résumé:** Apprenez à configurer les CDR et QoE dans Skype entreprise Server.
  
Configurez la surveillance des CDR et QoE à l’aide de rapports SQL Server Reporting Services pour Skype entreprise Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurez l’enregistrement des détails des appels et la qualité de l’expérience

Après avoir associé un magasin de surveillance avec un pool frontal, vous pouvez configurer le magasin de surveillance, puis installer et configurer SQL Server Reporting Services et surveiller des rapports pour gérer l’enregistrement des détails des appels (CDR) et la qualité de l’expérimentation. suivi à l’aide de Skype entreprise Server Management Shell. Les applets de contrôle Skype entreprise Server Management Shell vous permettent d’activer et de désactiver la surveillance des CDR et/ou QoE pour un site particulier ou pour l’ensemble de votre déploiement Skype entreprise Server. pour ce faire, vous pouvez utiliser une commande aussi simple que celle-ci:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Lorsque vous installez Skype entreprise Server, vous devez également installer une collection prédéfinie de paramètres de configuration globale pour les éléments CDR et QoE. Les valeurs par défaut de certains des paramètres les plus couramment utilisés par l’enregistrement des détails des appels sont indiquées dans le tableau suivant :
  
|**Propriété**|**Description**|**Valeur par défaut**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indique si l’enregistrement des détails des appels est activé ou non. Si la valeur est True, tous les enregistrements CDR sont collectés et enregistrés dans la base de données de surveillance.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données. Si la valeur est définie sur True, les enregistrements sont supprimés après la période spécifiée par les propriétés KeepCallDetailForDays (pour les enregistrements CDR) et KeepErrorReportForDays (pour les erreurs CDR). Si la valeur est définie sur False, les enregistrements CDR sont conservés indéfiniment.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |Indique le nombre de jours durant lesquels les enregistrements CDR sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.  <br/> Vous pouvez définir la propriété KeepCallDetailForDays sur n’importe quel entier entre 1 et 2 562 jours (environ 7 ans).  <br/> |60 jours  <br/> |
|KeepErrorReportForDays  <br/> |Indique le nombre de jours de conservation des rapports d’erreurs CDR; tout rapport antérieur au nombre de jours spécifié sera automatiquement supprimé. Les rapports d’erreur CDR sont des rapports de diagnostic téléchargés par des applications clientes telles que Skype entreprise Server.  <br/> Vous pouvez définir cette propriété sur n’importe quelle valeur entière comprise entre 1 et 2 562.  <br/> |60 jours  <br/> |
   
De même, les valeurs par défaut pour les paramètres de la qualité de l’expérience (QoE) sélectionnés sont indiquées dans ce tableau :
  
|**Propriété**|**Description**|**Valeur par défaut**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indique si la surveillance QoE est activée ou non. Si la valeur est True, tous les enregistrements QoE sont collectés et enregistrés dans la base de données de surveillance.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indique si les enregistrements QoE doivent être périodiquement supprimés de la base de données. Si la valeur est True, les enregistrements sont supprimés après la période spécifiée par la propriété KeepQoEDataForDays. Si la valeur est False, les enregistrements QoE sont conservés indéfiniment.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Indique le nombre de jours durant lesquels les enregistrements QoE sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.  <br/> KeepCallDetailForDays peut être défini sur n’importe quelle valeur entière comprise entre 1 et 2 562 jours.  <br/> |60 jours  <br/> |
   
Si vous devez modifier ces paramètres globaux, vous pouvez pour cela utiliser les applets de commande Set-CsCdrConfiguration et Set-CsQoEConfiguration. Par exemple, cette commande (exécutée à partir de Skype entreprise Server Management Shell) désactive le contrôle CDR dans l’étendue globale. pour ce faire, définissez la propriété EnableCDR sur false ($False):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Notez que le fait de désactiver la surveillance ne dissocie pas le magasin d’analyse du pool frontal, ni ne désinstalle et n’a un impact sur la base de données de surveillance principale. Lorsque vous utilisez Skype entreprise Server Management Shell pour désactiver le contrôle CDR ou QoE, il vous suffit de désactiver temporairement Skype entreprise Server dans le cadre de la collecte et de l’archivage des données d’analyse. Pour reprendre la collecte et l’archivage des données de l’enregistrement CDR, il vous suffit de redéfinir la propriété EnableCDR sur True ($True):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

De même, cette commande désactive la purge des enregistrements QoE globaux :
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Outre les paramètres globaux, les paramètres de configuration CDR et QoE peuvent être assignés pour un site. Cela offre plus de flexibilité pour la gestion de la surveillance ; par exemple, un administrateur peut activer la surveillance CDR pour le site de Redmond et la désactiver pour le site de Dublin. Pour créer de nouveaux paramètres de configuration CDR pour un site, utilisez une commande similaire à celle-ci :
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Gardez à l’esprit que les paramètres configurés pour un site prévalent sur les paramètres globaux configurés. Supposons, par exemple, que la surveillance CDR soit activée globalement, mais désactivée pour un site (le site de Redmond). Dans ce cas, les informations de l’enregistrement des détails des appels ne seront pas archivées pour les utilisateurs du site de Redmond mais elles le seront pour les utilisateurs des autres sites (c’est-à-dire, les utilisateurs gérés par les paramètres globaux et non par les paramètres du site de Redmond).
  
Pour créer de nouveaux paramètres QoE pour un site, il suffit d’utiliser une commande similaire à la commande suivante :
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Pour plus d’informations, tapez les commandes suivantes dans Skype entreprise Server Management Shell:
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
