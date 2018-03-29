---
title: Création des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Résumé : Découvrez les paramètres de la qualité d’expérience (QoE) dans Skype pour Business Server 2015.'
ms.openlocfilehash: a6ba2906b54ac5d963b0c8394c1fcf254cffd12d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server-2015"></a>Création des paramètres de configuration de la qualité de l’expérience dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur les paramètres de qualité d’expérience (QoE) dans Skype pour Business Server 2015.
  
Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.
  
Lorsque vous installez Skype pour Business Server 2015, une seule collection globale QoE de paramètres de configuration est créée pour vous. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres d’étendue de site sont utilisés, ils prennent la priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres pour l’étendue du site de Redmond, ces paramètres (au lieu des paramètres globaux) servent alors à gérer QoE à Redmond.
  
QoE les paramètres de configuration peuvent être créés à l’aide soit Skype pour Business Server du Panneau de configuration ou l’applet de commande [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) . Si vous utilisez Skype pour le panneau de configuration de Business Server pour créer de nouveaux paramètres, les options suivantes seront disponibles :
  
|**Définition de l’interface utilisateur**|**Paramètre de PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identity  <br/> |Identificateur unique des paramètres à créer. Les paramètres de configuration QoE peuvent uniquement être créés au niveau de l’étendue du site.  <br/> |
|Activer la surveillance des données de QoE  <br/> |EnableQoE  <br/> |Indique si des enregistrements QoE seront collectés et enregistrés dans la base de données de surveillance.  <br/> |
|Activer le vidage des données de QoE  <br/> |EnablePurging  <br/> |Spécifie si les rapports sont vidés une fois la durée définie dans la propriété **Conserver les données QoE pendant la durée maximale (jours)** écoulée. <br/> |
|Conserver les données QoE pendant la durée maximale (jours)  <br/> |KeepQoEDataForDays  <br/> |Nombre de jours pendant lesquels les données QoE sont enregistrées avant d’être vidées de la base de données. Cette valeur est ignorée si le vidage est désactivé.  <br/> |
   
> [!NOTE]
> L’applet de commande New-CsQoEConfiguration inclut des options supplémentaires n’est pas disponibles dans Skype pour le panneau de configuration de Business Server. Pour plus d’informations, consultez la rubrique d’aide de [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour créer des paramètres de configuration QoE pour le panneau de configuration de Business Server à l’aide de Skype

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **Déléguer les autorisations de configuration**.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.
    
4. Dans la page **Données de qualité de l’expérience**, cliquez sur **Nouveau**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée, puis cliquez sur **OK**.
    
6. Dans **Nouveau paramètre de qualité de l’expérience**, procédez comme suit :
    
   - Sélectionnez **Activer la surveillance des données de QoE** pour activer la surveillance.
    
   - Sélectionnez **Activer le vidage des données de QoE** pour activer le vidage.
    
   - Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximum de jours de rétention des enregistrements QoE.
    
7. Cliquez sur **Valider**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de Configuration QoE à l’aide des applets de commande Windows PowerShell

Vous pouvez créer des paramètres de configuration QoE à l’aide de Windows PowerShell et l’applet de commande New-CsQoEConfiguration. Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Pour créer une collection de paramètres de configuration QoE

 Cette commande crée une collection de paramètres de configuration QoE qui sont appliqués au site Redmond :
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Pour créer une collection de paramètres de configuration QoE dans laquelle la surveillance QoE est désactivée

 Étant donné qu’aucun paramètre (à l’exception du paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés. Pour créer des paramètres qui utilisent des valeurs de propriété différentes, incluez simplement le paramètre approprié et la valeur du paramètre. Par exemple, pour créer une collection de paramètres de configuration de qualité de l’expérience qui, par défaut, permet de désactiver enregistrement de données QoE, utilisez une commande semblable à celle-ci :
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Pour spécifier plusieurs valeurs de propriété lors de création d’une collection de paramètres de configuration QoE

 Vous pouvez spécifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande configure les nouveaux paramètres de manière à conserver les données QoE pendant 30 jours et à vider les anciennes données à 03:00 :
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  

