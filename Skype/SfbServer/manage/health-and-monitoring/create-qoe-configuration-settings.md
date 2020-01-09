---
title: Créer des paramètres de configuration de qualité de l’interface dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Résumé : Obtenez des informations sur les paramètres de qualité de l’interface utilisateur de Skype entreprise Server.'
ms.openlocfilehash: 254e6f1032026f715c30017f984bc2906f46e0df
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992791"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Créer des paramètres de configuration de qualité de l’interface dans Skype entreprise Server
 
**Résumé :** En savoir plus sur les paramètres de qualité de l’expertise dans Skype entreprise Server.
  
Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et le montant de « gigue » (différences de retard des paquets). Ces mesures sont stockées dans une base de données distincte des autres données (telles que les enregistrements des détails des appels), ce qui permet d’activer et de désactiver l’enregistrement QoE indépendamment de l’enregistrement des autres données.
  
Lorsque vous installez Skype entreprise Server, une collection globale unique de paramètres de configuration QoE est créée pour vous. Les administrateurs peuvent aussi créer des paramètres personnalisés sur l’étendue du site. Chaque fois que ces paramètres d’étendue de site sont utilisés, ils prennent la priorité sur les paramètres globaux. Par exemple, si vous créez des paramètres pour l’étendue du site de Redmond, ces paramètres (au lieu des paramètres globaux) servent alors à gérer QoE à Redmond.
  
Les paramètres de configuration QoE peuvent être créés à l’aide du panneau de configuration Skype entreprise Server ou de l’applet [de commande New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) . Si vous utilisez le panneau de configuration Skype entreprise Server pour créer des paramètres, les options suivantes sont disponibles :
  
|**Paramètre de l’interface utilisateur**|**Paramètre PowerShell**|**Description**|
|:-----|:-----|:-----|
|Nom  <br/> |Identity  <br/> |Identificateur unique des paramètres à créer. Les paramètres de configuration QoE peuvent uniquement être créés au niveau de l’étendue du site.  <br/> |
|Activer la surveillance des données de QoE  <br/> |EnableQoE  <br/> |Indique si des enregistrements QoE seront collectés et enregistrés dans la base de données de surveillance.  <br/> |
|Activer le vidage des données de QoE  <br/> |EnablePurging  <br/> |Spécifie si les rapports sont vidés une fois la durée définie dans la propriété **Conserver les données QoE pendant la durée maximale (jours)** écoulée. <br/> |
|Conserver les données QoE pendant la durée maximale (jours)  <br/> |KeepQoEDataForDays  <br/> |Nombre de jours pendant lesquels les données QoE sont enregistrées avant d’être vidées de la base de données. Cette valeur est ignorée si le vidage est désactivé.  <br/> |
   
> [!NOTE]
> L’applet de commande New-CsQoEConfiguration inclut des options supplémentaires qui ne sont pas disponibles dans le panneau de configuration Skype entreprise Server. Pour plus d’informations, reportez-vous à la rubrique d’aide [nouveau-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Pour créer des paramètres de configuration QoE en utilisant le panneau de configuration Skype entreprise Server

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **autorisations de configuration de délégué**.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.
    
4. Dans la page **Données de qualité de l’expérience**, cliquez sur **Nouveau**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée, puis cliquez sur **OK**.
    
6. Dans **Nouveau paramètre de qualité de l’expérience**, procédez comme suit :
    
   - Sélectionnez **Activer la surveillance des données de QoE** pour activer la surveillance.
    
   - Sélectionnez **Activer le vidage des données de QoE** pour activer le vidage.
    
   - Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximum de jours de rétention des enregistrements QoE.
    
7. Cliquez sur **Valider**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de paramètres de configuration QoE à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez créer des paramètres de configuration QoE à l’aide de Windows PowerShell et de l’applet de nouvelle applet de nouveau-CsQoEConfiguration. Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype entreprise Server.
  
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

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  

