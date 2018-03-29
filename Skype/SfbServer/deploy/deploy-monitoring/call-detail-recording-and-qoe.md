---
title: Configurer l’enregistrement détail des appels et des paramètres de qualité de l’expérience dans Skype pour Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Résumé : Apprenez à configurer des CD-r et QoE dans Skype pour Business Server 2015.'
ms.openlocfilehash: 0b72aa4ca58de934d2d09c599e6e7686e70f8822
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server-2015"></a>Configurer l’enregistrement détail des appels et des paramètres de qualité de l’expérience dans Skype pour Business Server 2015
 
**Résumé :** Apprenez à configurer des CD-r et QoE dans Skype pour Business Server 2015.
  
Configurer les CD-r et surveillance à l’aide de rapports SQL Server Reporting Services pour Skype pour Business Server 2015 QoE.
  
## <a name="configure-cdr-and-qoe"></a>Configurez l’enregistrement des détails des appels et la qualité de l’expérience

Une fois que vous avez associé à une banque de surveillance un pool frontal, définir le magasin de surveillance et ensuite installé et configuré SQL Server Reporting Services et les rapports de surveillance, vous pouvez gérer l’enregistrement de détail appels (CDR) et qualité d’expérience (QoE) surveillance à l’aide de Skype pour Business Server Management Shell. Skype pour les applets de commande Business Server Management Shell permettent d’activer et de désactiver des CD-r et/ou QoE monitoring pour un site particulier ou pour votre ensemble Skype pour le déploiement du serveur de l’entreprise ; Ceci peut se faire avec une commande aussi simple que ceci :
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Lorsque vous installez Skype pour Business Server 2015, vous installerez également un ensemble prédéfini de paramètres de configuration globaux pour les CD-r et QoE. Les valeurs par défaut de certains des paramètres les plus couramment utilisés par l’enregistrement des détails des appels sont indiquées dans le tableau suivant :
  
|**Propriété**|**Description**|**Valeur par défaut**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indique si l’enregistrement des détails des appels est activé ou non. Si la valeur est True, tous les enregistrements CDR sont collectés et enregistrés dans la base de données de surveillance.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données. Si la valeur est définie sur True, les enregistrements sont supprimés après la période spécifiée par les propriétés KeepCallDetailForDays (pour les enregistrements CDR) et KeepErrorReportForDays (pour les erreurs CDR). Si la valeur est définie sur False, les enregistrements CDR sont conservés indéfiniment.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |Indique le nombre de jours durant lesquels les enregistrements CDR sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.  <br/> Vous pouvez définir la propriété KeepCallDetailForDays sur n’importe quel entier entre 1 et 2 562 jours (environ 7 ans).  <br/> |60 jours  <br/> |
|KeepErrorReportForDays  <br/> |Indique le nombre de jours pendant lesquels les rapports d’erreurs CDR sont conservées ; des rapports plus anciens que le nombre de jours spécifié seront automatiquement supprimés. Rapports d’erreur de CD-r sont des rapports de diagnostic chargés par les applications clientes telles que Skype pour Business Server 2015.  <br/> Vous pouvez définir cette propriété sur n’importe quelle valeur entière comprise entre 1 et 2 562.  <br/> |60 jours  <br/> |
   
De même, les valeurs par défaut pour les paramètres de la qualité de l’expérience (QoE) sélectionnés sont indiquées dans ce tableau :
  
|**Propriété**|**Description**|**Valeur par défaut**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indique si la surveillance QoE est activée ou non. Si la valeur est True, tous les enregistrements QoE sont collectés et enregistrés dans la base de données de surveillance.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indique si les enregistrements QoE doivent être périodiquement supprimés de la base de données. Si la valeur est True, les enregistrements sont supprimés après la période spécifiée par la propriété KeepQoEDataForDays. Si la valeur est False, les enregistrements QoE sont conservés indéfiniment.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Indique le nombre de jours durant lesquels les enregistrements QoE sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.  <br/> KeepCallDetailForDays peut être défini sur n’importe quelle valeur entière comprise entre 1 et 2 562 jours.  <br/> |60 jours  <br/> |
   
Si vous devez modifier ces paramètres globaux, vous pouvez pour cela utiliser les applets de commande Set-CsCdrConfiguration et Set-CsQoEConfiguration. Par exemple, cette commande (exécutée à partir de la Skype pour Business Server Management Shell) désactive les CDR de surveillance au niveau de la portée globale ; Cela est fait en définissant la propriété EnableCDR sur False ($False) :
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Notez que le fait de désactiver la surveillance ne dissocie pas le magasin d’analyse du pool frontal, ni ne désinstalle et n’a un impact sur la base de données de surveillance principale. Lorsque vous utilisez Skype pour Business Server Management Shell pour désactiver la surveillance des CD-r ou de QoE vraiment suffit de suspendre le Skype pour Business Server à partir de la collecte et l’archivage des données d’analyse. Pour reprendre la collecte et l’archivage des données de l’enregistrement CDR, il vous suffit de redéfinir la propriété EnableCDR sur True ($True):
  
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

Pour plus d’informations, tapez les commandes suivantes dans le Skype pour Business Server Management Shell :
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```


