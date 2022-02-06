---
title: Configurer les paramètres d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Résumé : Découvrez comment configurer l’cdr et la qualité de l’Skype Entreprise Server.'
---

# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurer les paramètres d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server
 
**Résumé :** Découvrez comment configurer l’cdr et la qualité de l’Skype Entreprise Server.
  
Configurez la surveillance cdR et QoE à l’aide SQL Server Reporting Services rapports pour Skype Entreprise Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurer l’cdr et QoE

Une fois que vous avez associé un magasin d’analyse à un pool frontal, configurez le magasin d’analyse, puis installez et configurez SQL Server Reporting Services et les rapports de surveillance, vous pouvez gérer la surveillance de l’enregistrement des détails des appels et de la qualité de l’expérience (QoE) à l’aide de Skype Entreprise Server Management Shell. les cmdlets Skype Entreprise Server Management Shell vous permettent d’activer et de désactiver la surveillance CDR et/ou QoE pour un site particulier ou pour l’ensemble de votre déploiement Skype Entreprise Server ; vous pouvez le faire avec une commande aussi simple que celle-ci :
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Lorsque vous installez Skype Entreprise Server, vous installez également une collection prédéfinie de paramètres de configuration globaux pour cdr et QoE. Les valeurs par défaut de certains des paramètres les plus couramment utilisés par l’enregistrement des détails des appels sont indiquées dans le tableau suivant :
  
|**Propriété**|**Description**|**Valeur par défaut**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indique si l’enregistrement des détails des appels est activé ou non. Si la valeur est True, tous les enregistrements CDR sont collectés et enregistrés dans la base de données de surveillance.  <br/> |Vrai  <br/> |
|EnablePurging  <br/> |Indique si les enregistrements des détails des appels doivent être périodiquement supprimés de la base de données. Si la valeur est définie sur True, les enregistrements sont supprimés après la période spécifiée par les propriétés KeepCallDetailForDays (pour les enregistrements CDR) et KeepErrorReportForDays (pour les erreurs CDR). Si la valeur est définie sur False, les enregistrements CDR sont conservés indéfiniment.  <br/> |Vrai  <br/> |
|KeepCallDetailForDays  <br/> |Indique le nombre de jours durant lesquels les enregistrements CDR sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.  <br/> Vous pouvez définir la propriété KeepCallDetailForDays sur n’importe quelle valeur entière comprise entre 1 et 2562 jours (environ 7 ans).  <br/> |60 jours  <br/> |
|KeepErrorReportForDays  <br/> |Indique le nombre de jours de la tenue des rapports d’erreurs des détails des erreurs ; Tous les rapports plus anciens que le nombre de jours spécifié sont automatiquement supprimés. Les rapports d’erreur d’cdr sont des rapports de diagnostic téléchargés par des applications clientes telles que Skype Entreprise Server.  <br/> Vous pouvez définir cette propriété sur n’importe quelle valeur entière comprise entre 1 et 2562.  <br/> |60 jours  <br/> |
   
De même, les valeurs par défaut pour les paramètres de la qualité de l’expérience (QoE) sélectionnés sont indiquées dans ce tableau :
  
|**Propriété**|**Description**|**Valeur par défaut**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indique si la surveillance QoE est activée ou non. Si la valeur est True, tous les enregistrements QoE sont collectés et enregistrés dans la base de données de surveillance.  <br/> |Vrai  <br/> |
|EnablePurging  <br/> |Indique si les enregistrements QoE doivent être périodiquement supprimés de la base de données. Si la valeur est True, les enregistrements sont supprimés après la période spécifiée par la propriété KeepQoEDataForDays. Si la valeur est False, les enregistrements QoE sont conservés indéfiniment.  <br/> |Vrai  <br/> |
|KeepQoEDataForDays  <br/> |Indique le nombre de jours durant lesquels les enregistrements QoE sont conservés dans la base de données. Tout enregistrement plus ancien que le nombre de jours spécifié est automatiquement supprimé. Mais pour cela, la purge doit être activée.  <br/> KeepCallDetailForDays peut être défini sur n’importe quelle valeur entière comprise entre 1 et 2562 jours.  <br/> |60 jours  <br/> |
   
Si vous devez modifier ces paramètres globaux, vous pouvez pour cela utiliser les applets de commande Set-CsCdrConfiguration et Set-CsQoEConfiguration. Par exemple, cette commande (exécuté à partir de l’environnement de commande Skype Entreprise Server Management Shell) désactive la surveillance cdR au niveau de l’étendue globale ; pour ce faire, la propriété EnableCDR a la valeur False ($False) :
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Notez que le fait de désactiver la surveillance ne dissocie pas le magasin d’analyse du pool frontal, ni ne désinstalle et n’a un impact sur la base de données de surveillance principale. Lorsque vous utilisez Skype Entreprise Server Management Shell pour désactiver la surveillance CDR ou QoE, il vous s agit d’arrêter temporairement la collecte et l’archivage des données d’analyse par Skype Entreprise Server. Pour reprendre la collecte et l’archivage des données de l’enregistrement CDR, il vous suffit de redéfinir la propriété EnableCDR sur True ($True):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

De même, cette commande désactive la purge des enregistrements QoE globaux :
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Outre les paramètres globaux, les paramètres de configuration CDR et QoE peuvent être assignés pour un site. Cela offre plus de flexibilité pour la gestion de la surveillance ; par exemple, un administrateur peut activer la surveillance CDR pour le site de Redmond et la désactiver pour le site de Dublin. Pour créer de nouveaux paramètres de configuration CDR pour un site, utilisez une commande similaire à celle-ci :
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Gardez à l’esprit que les paramètres configurés pour un site prévalent sur les paramètres globaux configurés. Supposons, par exemple, que la surveillance CDR soit activée globalement, mais désactivée pour un site (le site de Redmond). Dans ce cas, les informations de l’enregistrement des détails des appels ne seront pas archivées pour les utilisateurs du site de Redmond mais elles le seront pour les utilisateurs des autres sites (c’est-à-dire, les utilisateurs gérés par les paramètres globaux et non par les paramètres du site de Redmond).
  
Pour créer de nouveaux paramètres QoE pour un site, il suffit d’utiliser une commande similaire à la commande suivante :
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Pour plus d’informations, tapez les commandes suivantes à partir de Skype Entreprise Server Management Shell :
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
