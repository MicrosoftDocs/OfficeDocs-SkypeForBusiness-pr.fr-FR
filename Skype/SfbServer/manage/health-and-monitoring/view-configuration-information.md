---
title: Affichage des informations de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Résumé : Apprenez à utiliser l’enregistrement de détail appels (CDR) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 6eacc6c300cfc1faae843a1dc610b17b45ae9c88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a>Affichage des informations de configuration de l’enregistrement des détails des appels dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à utiliser d’enregistrement de détail appels (CDR) dans Skype pour Business Server 2015.
  
L’enregistrement des détails des appels permet d’assurer le suivi des sessions de messagerie instantanée d’égal à égal, des appels téléphoniques VoIP (Voice over Internet Protocol) et des téléconférences. Ces données d’utilisation permettent de savoir qui appelle qui, à quelle heure et la durée de la communication.
  
Lorsque vous installez Skype pour Business Server 2015, une seule collection globale CDR de paramètres de configuration est créée pour vous. Les administrateurs ont également la possibilité de créer des collections de paramètres personnalisées applicables à des sites individuels. Vous pouvez afficher les paramètres de configuration de CD-r en cours d’utilisation dans votre organisation à l’aide de Skype pour Business Server du Panneau de configuration ou l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Pour afficher les informations de configuration de CD-r pour le panneau de configuration de Business Server à l’aide de Skype

1. Dans Skype pour le panneau de configuration de Business Server, cliquez sur **surveillance et archivage**.
    
2. La liste de tous vos paramètres de configuration d’enregistrement des détails des appels s’affiche sous l’onglet **Enregistrement des détails des appels** ; pour chaque collection de paramètres apparaissent la collection **Nom**, l’indication stipulant si l’enregistrement des détails des appels a été activé ou non (propriété **Enregistrement des détails des appels**) et l’indication stipulant si le vidage a été activé (propriété **Vidage de l’enregistrement des détails des appels**). Pour plus d’informations sur une collection, double-cliquez dessus ou sélectionnez la collection appropriée, cliquez sur **Modifier**, puis sur **Afficher les détails**. Notez que vous pouvez uniquement afficher des informations détaillées pour une seule collection de paramètres de configuration d’enregistrement des détails des appels à la fois.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>CD-r de l’affichage des informations de configuration à l’aide des applets de commande Windows PowerShell

Vous pouvez afficher les paramètres de configuration de CD-r à l’aide de Windows PowerShell et l’applet de commande Get-CsCdrConfiguration. Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876). Le processus est le même dans Skype pour Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Pour afficher les informations de configuration d’enregistrement des détails des appels

- Pour afficher des informations sur tous vos paramètres de configuration de CD-r, tapez la commande suivante dans la Skype pour Business Server Management Shell et puis appuyez sur ENTRÉE :
    
  ```
  Get-CsCdrConfiguration
  ```

    Vous obtiendrez des indications semblables à ceci :
    
  ```
  Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2

  ```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

