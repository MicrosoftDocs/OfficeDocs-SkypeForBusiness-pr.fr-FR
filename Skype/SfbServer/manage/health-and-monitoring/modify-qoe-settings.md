---
title: Modification des paramètres de qualité de l’expérience dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Résumé : Découvrez comment spécifier la rétention de données QoE dans Skype pour Business Server 2015.'
ms.openlocfilehash: 99a85a389b225d57b48b52b3f6f1d5b66e93f122
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server-2015"></a>Modification des paramètres de qualité de l’expérience dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à spécifier la rétention de données QoE dans Skype pour Business Server 2015.
  
Par défaut, les données de qualité de l’expérience (QoE) sont vidées au bout de 60 jours. Vous pouvez utiliser les paramètres de la page **Données de qualité de l’expérience** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez QoE, les données capturées avant que l’activation de QoE seront également purgées.
  
> [!NOTE]
> Vous devez configurer l’enregistrement des détails des appels (CDR) et QoE pour conserver des données pendant le même nombre de jours. Chaque appel des enregistrements des détails des appels disponible à partir de la page d’accueil des rapports de surveillance inclut des informations sur l’enregistrement des détails des appels et sur la qualité de l’expérience. Si la durée du vidage est différente pour les enregistrements des détails des appels (CDR) et la qualité de l’expérience (QoE), certains appels pourront inclure uniquement des données CDR, tandis que d’autres contiendront uniquement des données QoE. 
  
La procédure suivante décrit comment configurer des paramètres de vidage pour des données de qualité de l’expérience (QoE). 
  
### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>Pour spécifier la rétention de données QoE pour le panneau de configuration de Business Server à l’aide de Skype

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **Déléguer les autorisations de configuration**.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.
    
4. Dans la page **Données de qualité de l’expérience**, cliquez sur le site approprié dans le tableau, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Pour activer le vidage, sélectionnez **Activer le vidage des données de qualité de l’expérience**.
    
6. Dans **Conserver les données QoE pendant la durée maximale (jours)**, sélectionnez le nombre maximal de jours pendant lesquels les données de qualité de l’expérience doivent être conservées.
    
7. Cliquez sur **Valider**.
    
## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Spécification QoE rétention à l’aide des applets de commande Windows PowerShell

Vous pouvez créer des paramètres de rétention QoE à l’aide de Windows PowerShell et l’applet de commande **Set-CsQoEConfiguration** . Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-specify-qoe-retention-for-a-specific-location"></a>Pour spécifier la conservation des données QoE pour un emplacement spécifique

- Cette commande active le vidage des données QoE pour le site Redmond et configure le site de façon à conserver les données QoE pendant 20 jours.
    
  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>Pour spécifier la conservation des données QoE pour plusieurs emplacements

- Cette commande configure la conservation des données QoE pour tous les paramètres de configuration QoE utilisés dans une organisation.
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 
  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Voir aussi

#### 

[Déploiement de surveillance](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

