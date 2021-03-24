---
title: Créer des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Résumé : Découvrez les paramètres de qualité de l’expérience (QoE) dans Skype Entreprise Server.'
ms.openlocfilehash: 8cce0731112166ae232b6273b556d37d693564e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095348"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Créer des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server
 
**Résumé :** Découvrez les paramètres de qualité de l’expérience (QoE) dans Skype Entreprise Server.
  
Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.
  
Lorsque vous installez Skype Entreprise Server, une collection globale et unique de paramètres de configuration QoE est créée pour vous. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres étendus aux sites sont utilisés, ils ont priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres étendus au site pour le site Redmond, ceux-ci (et non les paramètres globaux) sont utilisés pour gérer la qualité de l’expérience à Redmond.
  
Les paramètres de configuration QoE peuvent être créés à l’aide du Panneau de configuration de Skype Entreprise Server ou de l';cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Si vous utilisez le Panneau de configuration Skype Entreprise Server pour créer de nouveaux paramètres, les options suivantes sont disponibles :
  
|**Paramètre de l’interface utilisateur**|**Paramètre PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identité  <br/> |Identificateur unique des paramètres à créer. Les paramètres de configuration QoE peuvent uniquement être créés au niveau de l’étendue du site.  <br/> |
|Activer la surveillance des données de QoE  <br/> |EnableQoE  <br/> |Spécifie si les enregistrements QoE seront collectés et enregistrés dans la base de données de surveillance.  <br/> |
|Activer le vidage des données de QoE  <br/> |EnablePurging  <br/> |Spécifie si les rapports sont vidés une fois la durée définie dans la propriété **Conserver les données QoE pendant la durée maximale (jours)** écoulée. <br/> |
|Conserver les données QoE pendant la durée maximale (jours)  <br/> |KeepQoEDataForDays  <br/> |Nombre de jours pendant lesquels les données QoE sont enregistrées avant d’être vidées de la base de données. Cette valeur est ignorée si le vidage est désactivé.  <br/> |
   
> [!NOTE]
> La cmdlet New-CsQoEConfiguration inclut des options supplémentaires qui ne sont pas disponibles dans le Panneau de contrôle Skype Entreprise Server. Pour plus d’informations, voir la rubrique [d’aide New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour créer des paramètres de configuration QoE à l’aide du Panneau de configuration de Skype Entreprise Server

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.
    
4. Dans la page **Données de qualité de l’expérience**, cliquez sur **Nouveau**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée, puis cliquez sur **OK**.
    
6. Dans **Nouveau paramètre de qualité de l’expérience**, procédez comme suit :
    
   - Sélectionnez **Activer la surveillance des données de QoE** pour activer la surveillance.
    
   - Sélectionnez **Activer le vidage des données de QoE** pour activer le vidage.
    
   - Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximum de jours de rétention des enregistrements QoE.
    
7. Cliquez sur **Valider**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de configuration QoE à l’aide Windows PowerShell cmdlets

Vous pouvez créer des paramètres de configuration QoE à l’aide de Windows PowerShell et de l'New-CsQoEConfiguration de configuration. Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion [de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ». Le processus est le même dans Skype Entreprise Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Pour créer une collection de paramètres de configuration QoE

 Cette commande crée une collection de paramètres de configuration QoE qui sont appliqués au site Redmond :
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Pour créer une collection de paramètres de configuration QoE dans laquelle la surveillance QoE est désactivée

 Étant donné qu’aucun paramètre (à l’exception du paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui utilisent des valeurs de propriété différentes, incluez simplement le paramètre approprié et la valeur du paramètre. Par exemple, pour créer une collection de paramètres de configuration de qualité de l’expérience qui, par défaut, permet de désactiver enregistrement de données QoE, utilisez une commande semblable à celle-ci :
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Pour spécifier plusieurs valeurs de propriété lors de création d’une collection de paramètres de configuration QoE

 Vous pouvez spécifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres de manière à conserver les données QoE pendant 30 jours et à vider les anciennes données à 03:00 :
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
